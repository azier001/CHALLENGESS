# 🔓 Dokumentasi Fungsi `decodeMessage`

## 📋 Deskripsi Fungsi

Fungsi `decodeMessage` adalah sebuah fungsi JavaScript yang digunakan untuk mengubah sebuah pesan dengan cara membalik urutan karakter dalam string, kemudian menggabungkannya dengan string asli. Fungsi ini menciptakan pola enkripsi sederhana yang dapat digunakan untuk menyandikan pesan.

## 🎯 Tujuan Penggunaan

- Membuat enkripsi sederhana untuk pesan
- Mengubah format string dengan pola tertentu
- Pembelajaran algoritma manipulasi string
- Proteksi data sederhana

## 📝 Struktur Fungsi

```javascript
function decodeMessage(message) {
    // Langkah 1: Membalik urutan karakter dalam string pesan
    const reversedMessage = message.split('').reverse().join('');
    
    // Langkah 2: Menggabungkan pesan yang sudah dibalik dengan pesan asli
    const decodedMessage = reversedMessage + message;
    
    // Langkah 3: Mengembalikan string hasil gabungan
    return decodedMessage;
}
```

## 🔧 Parameter

| Parameter | Tipe Data | Wajib | Deskripsi |
|-----------|-----------|-------|-----------|
| `message` | String | ✅ Ya | Pesan atau teks yang akan diproses dan diubah formatnya |

### 📖 Penjelasan Parameter

**`message`** - Parameter ini menerima input berupa string (teks) yang akan diproses. String ini bisa berupa kata, kalimat, atau karakter apapun yang valid dalam JavaScript.

## ⚙️ Cara Kerja Fungsi

1. **Membalik String**: Fungsi menggunakan method `split('')` untuk memecah string menjadi array karakter, kemudian `reverse()` untuk membalik urutan, dan `join('')` untuk menggabungkan kembali
2. **Menggabungkan**: String yang sudah dibalik digabungkan dengan string asli menggunakan operator `+`
3. **Mengembalikan Hasil**: Fungsi mengembalikan string baru yang merupakan gabungan dari kedua string

## 🎨 Contoh Penggunaan

### Contoh 1: Kata Sederhana
```javascript
const hasil1 = decodeMessage("HELLO");
console.log(hasil1); // Output: "OLLEHELLO"
```

### Contoh 2: Kalimat
```javascript
const hasil2 = decodeMessage("JavaScript");
console.log(hasil2); // Output: "tpircSavaJJavaScript"
```

### Contoh 3: Angka
```javascript
const hasil3 = decodeMessage("12345");
console.log(hasil3); // Output: "5432112345"
```

### Contoh 4: Teks dengan Spasi
```javascript
const hasil4 = decodeMessage("Hello World");
console.log(hasil4); // Output: "dlroW olleHHello World"
```

## 📊 Tabel Contoh Output

| Input | Proses Pembalikan | Output Akhir |
|-------|-------------------|--------------|
| `"ABC"` | `"CBA"` | `"CBAABC"` |
| `"123"` | `"321"` | `"321123"` |
| `"Hi"` | `"iH"` | `"iHHi"` |
| `"Test"` | `"tseT"` | `"tseTTest"` |

## 🔍 Analisis Kompleksitas

- **Time Complexity**: O(n) - dimana n adalah panjang string
- **Space Complexity**: O(n) - untuk menyimpan string hasil

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** string asli (immutable)
- Hasil output akan selalu **2 kali lipat** panjang input asli
- Fungsi bekerja dengan semua karakter Unicode yang valid
- Spasi dan karakter khusus akan diproses sama seperti huruf biasa

## 🧪 Tips Penggunaan

1. **Validasi Input**: Pastikan parameter yang diberikan adalah string
2. **Handling Empty String**: Fungsi akan mengembalikan string kosong jika input kosong
3. **Case Sensitivity**: Fungsi mempertahankan huruf besar/kecil dari input asli

## 🔄 Fungsi Kebalikan

Jika ingin mendapatkan kembali pesan asli, Anda dapat menggunakan:

```javascript
function getOriginalMessage(encodedMessage) {
    const length = encodedMessage.length;
    return encodedMessage.substring(length / 2);
}
```

## 📚 Referensi Method yang Digunakan

- `split('')`: Memecah string menjadi array karakter
- `reverse()`: Membalik urutan elemen dalam array
- `join('')`: Menggabungkan elemen array menjadi string
- Operator `+`: Menggabungkan dua string
