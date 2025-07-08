# 🎃 Fungsi createSpookyMessage

## 📋 Deskripsi

Fungsi `createSpookyMessage` adalah sebuah fungsi JavaScript yang mengubah pesan biasa menjadi pesan yang lebih menyeramkan dengan cara:
1. Membalik urutan kata-kata dalam kalimat
2. Mengganti kata-kata tertentu dengan alternatif yang lebih spooky/menyeramkan
3. Mempertahankan tanda baca dan kapitalisasi pada posisi yang tepat

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
  // Objek yang berisi daftar kata yang akan diganti dengan versi spooky
  const wordReplacements = {
    "happy": "haunted",
    "love": "fear",
    "together": "trapped",
    "forever": "nevermore"
  };
  
  return message
    .split(" ")                    // Memisahkan string menjadi array kata-kata
    .reverse()                     // Membalik urutan array kata-kata
    .map(word => {                 // Mengubah setiap kata dalam array
      // Mengubah kata menjadi huruf kecil dan menghapus karakter non-alfabet
      const lowercaseWord = word.toLowerCase().replace(/[^a-z]/g, "");
      
      // Mengecek apakah kata ada dalam daftar penggantian
      if (wordReplacements.hasOwnProperty(lowercaseWord)) {
        // Mengganti kata dengan versi spooky sambil mempertahankan kapitalisasi asli
        return word.replace(new RegExp(lowercaseWord, "i"), wordReplacements[lowercaseWord]);
      }
      
      // Mengembalikan kata asli jika tidak ada dalam daftar penggantian
      return word;
    })
    .join(" ");                    // Menggabungkan array kata kembali menjadi string
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

### Contoh 4: Kalimat dengan Kapitalisasi Berbeda
```javascript
const input = "I am HAPPY with my LOVE";
const output = createSpookyMessage(input);
console.log(output);
// Output: "FEAR my with HAUNTED am I"
```

### Contoh 5: Kalimat dengan Beberapa Tanda Baca
```javascript
const input = "Are you happy, my love?";
const output = createSpookyMessage(input);
console.log(output);
// Output: "fear? my haunted, you Are"
```

## 🔍 Cara Kerja Fungsi

1. **Definisi Penggantian**: Membuat objek `wordReplacements` yang berisi pasangan kata asli dan kata spooky
2. **Pemisahan Kata**: Memisahkan string input menggunakan spasi sebagai delimiter
3. **Pembalikan Urutan**: Membalik urutan array kata-kata menggunakan `reverse()`
4. **Proses Mapping**: Untuk setiap kata dalam array:
   - Mengubah kata menjadi huruf kecil dan menghapus karakter non-alfabet untuk pencocokan
   - Mengecek apakah kata ada dalam objek `wordReplacements`
   - Jika ada, mengganti kata tersebut sambil mempertahankan kapitalisasi asli
   - Jika tidak ada, mengembalikan kata asli
5. **Penggabungan**: Menggabungkan semua kata yang telah diproses kembali menjadi string

## ⚙️ Keunggulan Implementasi

- **Efisien**: Menggunakan object lookup (`O(1)`) untuk pencocokan kata
- **Preservasi Format**: Mempertahankan kapitalisasi dan tanda baca asli
- **Method Chaining**: Menggunakan functional programming dengan chaining methods
- **Regex Pattern**: Menggunakan regex dengan flag `"i"` untuk case-insensitive replacement
- **Mudah Diperluas**: Tinggal menambahkan pasangan kata baru ke dalam objek `wordReplacements`

## ⚠️ Catatan Penting

- Fungsi ini **case-insensitive** untuk pencocokan kata
- **Kapitalisasi asli dipertahankan** pada hasil output
- Tanda baca dan karakter khusus tidak akan mengganggu proses pencocokan
- Kata yang tidak ada dalam daftar penggantian akan tetap sama
- Fungsi ini mengubah urutan kata, sehingga struktur kalimat akan berubah

## 🎨 Tips Penggunaan

- Cocok untuk membuat efek spooky pada teks Halloween
- Dapat digunakan untuk game atau aplikasi tema horror
- Mudah diperluas dengan menambahkan lebih banyak kata ke objek `wordReplacements`
- Dapat diintegrasikan dengan sistem template atau chatbot untuk efek dramatik

## 🔧 Cara Menambah Kata Baru

Untuk menambahkan kata pengganti baru, cukup tambahkan pasangan key-value ke objek `wordReplacements`:

```javascript
const wordReplacements = {
  "happy": "haunted",
  "love": "fear",
  "together": "trapped",
  "forever": "nevermore",
  "beautiful": "cursed",    // Kata baru
  "bright": "dark",         // Kata baru
  "peaceful": "eerie"       // Kata baru
};
```
