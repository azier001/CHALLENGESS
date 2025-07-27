# 📝 Dokumentasi Fungsi `findStopWord`

## 🎯 Deskripsi Fungsi

Fungsi `findStopWord` adalah sebuah fungsi JavaScript yang digunakan untuk mencari kata kunci tertentu dalam sebuah array kalimat. Fungsi ini akan mengembalikan semua kalimat dari awal array hingga menemukan kalimat yang mengandung kata kunci yang dicari, termasuk kalimat yang mengandung kata kunci tersebut. Fungsi ini menggunakan pendekatan yang lebih efisien dengan langsung mengembalikan hasil menggunakan `slice()`.

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `sentences` | Array | Array yang berisi kumpulan kalimat (string) yang akan dicari |
| `stopWord` | String | Kata kunci yang ingin dicari dalam kalimat-kalimat |

## 💻 Kode Fungsi

```javascript
function findStopWord(sentences, stopWord) {
    // Looping melalui setiap kalimat dalam array
    for (let i = 0; i < sentences.length; i++) {
        
        // Cek apakah kalimat saat ini mengandung stopWord
        if (sentences[i].includes(stopWord)) {
            // Jika ditemukan, kembalikan array dari index 0 hingga i+1 (termasuk kalimat yang mengandung stopWord)
            return sentences.slice(0, i + 1);
        }
    }
    
    // Jika stopWord tidak ditemukan, kembalikan seluruh array sentences
    return sentences;
}
```

## 🔍 Cara Kerja

1. **Iterasi**: Fungsi melakukan loop melalui setiap kalimat dalam array `sentences`
2. **Pengecekan**: Pada setiap iterasi, fungsi mengecek apakah kalimat saat ini mengandung `stopWord` menggunakan method `includes()`
3. **Return Langsung**: Jika `stopWord` ditemukan, fungsi langsung mengembalikan potongan array dari index 0 hingga index kalimat yang mengandung `stopWord` (i+1) menggunakan `slice()`
4. **Fallback**: Jika loop selesai tanpa menemukan `stopWord`, fungsi mengembalikan seluruh array `sentences`

## 📊 Contoh Penggunaan

### Contoh 1: Pencarian Kata dalam Cerita
```javascript
const kalimat = [
    "Hari ini cuaca sangat cerah",
    "Saya pergi ke pasar pagi",
    "Di pasar saya bertemu teman lama",
    "Kami mengobrol tentang masa lalu",
    "Tiba-tiba hujan turun dengan deras",
    "Kami berlari mencari tempat berteduh"
];

const hasil = findStopWord(kalimat, "hujan");
console.log(hasil);
```

**Output:**
```javascript
[
    "Hari ini cuaca sangat cerah",
    "Saya pergi ke pasar pagi", 
    "Di pasar saya bertemu teman lama",
    "Kami mengobrol tentang masa lalu",
    "Tiba-tiba hujan turun dengan deras"
]
```

### Contoh 2: Kata Tidak Ditemukan
```javascript
const kalimat = [
    "Belajar programming itu menyenangkan",
    "JavaScript adalah bahasa yang powerful",
    "Dengan latihan rutin akan mahir"
];

const hasil = findStopWord(kalimat, "python");
console.log(hasil);
```

**Output:**
```javascript
[
    "Belajar programming itu menyenangkan",
    "JavaScript adalah bahasa yang powerful", 
    "Dengan latihan rutin akan mahir"
]
```

### Contoh 3: Kata Ditemukan di Kalimat Pertama
```javascript
const kalimat = [
    "Selamat pagi semua",
    "Hari ini kita akan belajar",
    "Tentang fungsi JavaScript"
];

const hasil = findStopWord(kalimat, "pagi");
console.log(hasil);
```

**Output:**
```javascript
[
    "Selamat pagi semua"
]
```

### Contoh 4: Pencarian Kata di Tengah Array
```javascript
const instruksi = [
    "Buka aplikasi",
    "Pilih menu utama",
    "Klik tombol STOP untuk berhenti",
    "Tutup aplikasi",
    "Restart komputer"
];

const hasil = findStopWord(instruksi, "STOP");
console.log(hasil);
```

**Output:**
```javascript
[
    "Buka aplikasi",
    "Pilih menu utama",
    "Klik tombol STOP untuk berhenti"
]
```

## ⚠️ Catatan Penting

- Fungsi ini melakukan pencarian **case-sensitive**, artinya "Hujan" dan "hujan" dianggap berbeda
- Jika `stopWord` tidak ditemukan, fungsi akan mengembalikan seluruh array `sentences`
- Fungsi menggunakan method `includes()` yang akan mencocokkan substring, jadi "hujan" akan cocok dengan "kehujanan"
- Fungsi berhenti dan langsung return saat menemukan kalimat pertama yang mengandung `stopWord`
- Method `slice(0, i + 1)` mengambil elemen dari index 0 hingga i (inklusif), sehingga kalimat yang mengandung `stopWord` ikut disertakan

## 🚀 Use Case

Fungsi ini berguna untuk:
- **Parsing teks**: Memotong teks pada kata kunci tertentu
- **Analisis konten**: Mengambil bagian awal dari konten hingga kata kunci tertentu
- **Preprocessing data**: Memfilter data teks berdasarkan kata kunci
- **Chatbot/NLP**: Mengidentifikasi konteks percakapan hingga kata kunci tertentu
- **Log analysis**: Mengambil log hingga error atau event tertentu
- **Instruction parsing**: Memproses instruksi hingga command tertentu

## 🔧 Kelebihan Versi Ini

- **Lebih efisien**: Menggunakan `slice()` alih-alih loop tambahan untuk membangun array hasil
- **Kode lebih ringkas**: Mengurangi jumlah baris kode tanpa mengurangi fungsionalitas
- **Memory efficient**: Tidak membuat array tambahan, langsung menggunakan `slice()`
- **Early return**: Berhenti segera setelah menemukan hasil

## 💡 Modifikasi yang Bisa Dilakukan

- Tambahkan parameter `caseSensitive` untuk mengatur sensitivitas huruf:
  ```javascript
  if (caseSensitive ? sentences[i].includes(stopWord) : sentences[i].toLowerCase().includes(stopWord.toLowerCase()))
  ```
- Gunakan regex untuk pencarian yang lebih kompleks
- Tambahkan parameter `includeStopWord` untuk menentukan apakah kalimat yang mengandung stopWord ikut disertakan atau tidak
- Tambahkan validasi input untuk memastikan `sentences` adalah array dan `stopWord` adalah string
