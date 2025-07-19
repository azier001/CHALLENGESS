# 🔐 Dokumentasi Function `decodeSecretMessage`

## 📋 Deskripsi

Function `decodeSecretMessage` adalah sebuah fungsi JavaScript yang digunakan untuk mendekode pesan rahasia berdasarkan buku kode (codebook). Fungsi ini bekerja dengan cara:

1. **Membalik urutan karakter** dalam pesan yang dikodekan
2. **Memisahkan kata-kata** dari pesan yang sudah dibalik
3. **Memeriksa setiap kata** dengan buku kode yang diberikan
4. **Mengganti kata yang tidak ada** dalam buku kode dengan "REDACTED"
5. **Menggabungkan kembali** semua kata menjadi pesan final

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `encodedMessage` | `string` | Pesan yang sudah dikodekan (dibalik urutannya) |
| `codebook` | `array` | Array berisi kata-kata yang diizinkan/valid |

### 📝 Detail Parameter:

- **encodedMessage**: String yang berisi pesan rahasia dalam urutan terbalik
- **codebook**: Array string yang berisi daftar kata-kata yang diizinkan. Kata-kata dalam codebook harus dalam huruf kecil

## 📤 Return Value

**Tipe**: `string`

**Deskripsi**: Mengembalikan pesan yang sudah didekode. Kata-kata yang tidak ada dalam codebook akan diganti dengan "REDACTED".

## 💻 Source Code

```javascript
function decodeSecretMessage(encodedMessage, codebook) {
    // Langkah 1: Membalik urutan karakter dalam pesan yang dikodekan
    const reversedMessage = encodedMessage.split('').reverse().join('');
    
    // Langkah 2: Memisahkan pesan yang sudah dibalik menjadi kata-kata
    const words = reversedMessage.split(' ');
    
    // Langkah 3-5: Membandingkan setiap kata dengan buku kode dan mengganti jika diperlukan
    const decodedWords = words.map(word => {
        // Menghilangkan tanda baca untuk perbandingan (hanya menyimpan huruf)
        const cleanWord = word.replace(/[^a-zA-Z]/g, '');
        
        // Memeriksa apakah kata ada dalam buku kode
        if (codebook.includes(cleanWord.toLowerCase())) {
            return word; // Menyimpan kata asli beserta tanda bacanya
        } else {
            return 'REDACTED'; // Mengganti kata yang tidak diizinkan
        }
    });
    
    // Langkah 6: Menggabungkan kembali kata-kata hasil decode menjadi string
    return decodedWords.join(' ');
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Pesan Valid
```javascript
const encodedMessage = "dlrow olleh";
const codebook = ["hello", "world"];

const result = decodeSecretMessage(encodedMessage, codebook);
console.log(result);
// Output: "hello world"
```

### Contoh 2: Pesan dengan Kata Tidak Valid
```javascript
const encodedMessage = "yrtnuoc ym evol i";
const codebook = ["i", "love"];

const result = decodeSecretMessage(encodedMessage, codebook);
console.log(result);
// Output: "i love REDACTED"
```

### Contoh 3: Pesan dengan Tanda Baca
```javascript
const encodedMessage = "!gnissim era skcus yht";
const codebook = ["thy", "socks", "are", "missing"];

const result = decodeSecretMessage(encodedMessage, codebook);
console.log(result);
// Output: "thy socks are missing!"
```

## 🔍 Cara Kerja Detail

### Langkah-langkah Proses:

1. **Reverse String**: `"dlrow olleh"` → `"hello world"`
2. **Split Words**: `["hello", "world"]`
3. **Check Codebook**: 
   - `"hello"` ✅ ada dalam codebook → tetap `"hello"`
   - `"world"` ✅ ada dalam codebook → tetap `"world"`
4. **Join Result**: `"hello world"`

## ⚠️ Catatan Penting

- **Case Insensitive**: Function ini tidak membedakan huruf besar dan kecil saat membandingkan dengan codebook
- **Punctuation Handling**: Tanda baca akan dipertahankan dalam hasil akhir, tetapi diabaikan saat pengecekan codebook
- **Codebook Format**: Pastikan semua kata dalam codebook menggunakan huruf kecil untuk hasil yang konsisten

## 🚀 Tips Penggunaan

- Gunakan codebook yang lengkap untuk menghindari terlalu banyak kata "REDACTED"
- Pastikan pesan input sudah dalam format yang benar (sudah dikodekan/dibalik)
- Function ini cocok untuk sistem filtering pesan atau dekripsi sederhana
