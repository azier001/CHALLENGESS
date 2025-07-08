# 🎃 Fungsi createSpookyMessage

## 📋 Deskripsi

Fungsi `createSpookyMessage` adalah sebuah fungsi JavaScript yang mengubah pesan biasa menjadi pesan yang lebih menyeramkan dengan cara:
1. Membalik urutan kata-kata dalam kalimat
2. Mengganti kata-kata tertentu dengan alternatif yang lebih spooky/menyeramkan
3. Mempertahankan tanda baca pada posisi yang tepat

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `message` | String | Pesan atau kalimat yang akan diubah menjadi versi spooky |

## 🎯 Return Value

**Tipe:** `String`

**Deskripsi:** Mengembalikan pesan yang telah dimodifikasi dengan urutan kata terbalik dan kata-kata tertentu diganti dengan alternatif spooky.

## 🔄 Tabel Penggantian Kata

| Kata Asli | Kata Spooky | Arti |
|-----------|-------------|------|
| `happy` | `haunted` | senang → berhantu |
| `love` | `fear` | cinta → takut |
| `together` | `trapped` | bersama → terjebak |
| `forever` | `nevermore` | selamanya → tidak pernah lagi |

## 💻 Kode Fungsi

```javascript
function createSpookyMessage(message) {
    // Langkah 1: Memisahkan string input menjadi array kata-kata
    const words = message.split(' ');
    
    // Langkah 2: Membalik urutan kata-kata
    const reversedWords = words.reverse();
    
    // Langkah 3: Mengganti kata-kata dengan alternatif spooky
    const spookyWords = reversedWords.map(word => {
        // Mengekstrak tanda baca dari akhir kata
        const punctuationMatch = word.match(/[.,!?;:]+$/);
        const punctuation = punctuationMatch ? punctuationMatch[0] : '';
        const cleanWord = word.replace(/[.,!?;:]+$/, '');
        
        let replacedWord;
        switch(cleanWord.toLowerCase()) {
            case 'happy':
                replacedWord = 'haunted';
                break;
            case 'love':
                replacedWord = 'fear';
                break;
            case 'together':
                replacedWord = 'trapped';
                break;
            case 'forever':
                replacedWord = 'nevermore';
                break;
            default:
                replacedWord = cleanWord;
        }
        
        return replacedWord + punctuation;
    });
    
    // Langkah 4: Menggabungkan kata-kata yang telah dimodifikasi kembali menjadi string tunggal
    return spookyWords.join(' ');
}
```

## 📝 Contoh Penggunaan

### Contoh 1: Kalimat Sederhana
```javascript
const input = "I am happy today";
const output = createSpookyMessage(input);
console.log(output);
// Output: "today haunted am I"
```

### Contoh 2: Kalimat dengan Tanda Baca
```javascript
const input = "We love being together forever!";
const output = createSpookyMessage(input);
console.log(output);
// Output: "nevermore! trapped being fear We"
```

### Contoh 3: Kalimat Tanpa Kata Spooky
```javascript
const input = "The cat is sleeping";
const output = createSpookyMessage(input);
console.log(output);
// Output: "sleeping is cat The"
```

### Contoh 4: Kalimat dengan Beberapa Tanda Baca
```javascript
const input = "Are you happy, my love?";
const output = createSpookyMessage(input);
console.log(output);
// Output: "fear? my haunted, you Are"
```

## 🔍 Cara Kerja Fungsi

1. **Pemisahan Kata**: Fungsi memisahkan string input menggunakan spasi sebagai delimiter
2. **Pembalikan Urutan**: Array kata-kata dibalik menggunakan method `reverse()`
3. **Penanganan Tanda Baca**: Menggunakan regex untuk memisahkan tanda baca dari kata
4. **Penggantian Kata**: Menggunakan `switch case` untuk mengganti kata spesifik dengan alternatif spooky
5. **Penggabungan**: Menggabungkan semua kata yang telah dimodifikasi kembali menjadi string

## ⚠️ Catatan Penting

- Fungsi ini **case-insensitive** untuk pencocokan kata (menggunakan `.toLowerCase()`)
- Tanda baca akan dipertahankan dan tetap berada di posisi yang benar
- Kata yang tidak ada dalam daftar penggantian akan tetap sama
- Fungsi ini mengubah urutan kata, sehingga struktur kalimat akan berubah

## 🎨 Tips Penggunaan

- Cocok untuk membuat efek spooky pada teks Halloween
- Dapat digunakan untuk game atau aplikasi tema horror
- Mudah diperluas dengan menambahkan lebih banyak kata pengganti dalam `switch case`
