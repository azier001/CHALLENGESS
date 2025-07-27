# 📝 Dokumentasi Fungsi `findStopWord`

## 🎯 Deskripsi Fungsi

Fungsi `findStopWord` adalah sebuah fungsi JavaScript yang digunakan untuk mencari kata kunci tertentu dalam sebuah array kalimat. Fungsi ini akan mengembalikan semua kalimat dari awal array hingga menemukan kalimat yang mengandung kata kunci yang dicari, termasuk kalimat yang mengandung kata kunci tersebut.

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `sentences` | Array | Array yang berisi kumpulan kalimat (string) yang akan dicari |
| `stopWord` | String | Kata kunci yang ingin dicari dalam kalimat-kalimat |

## 💻 Kode Fungsi

```javascript
function findStopWord(sentences, stopWord) {
    // Inisialisasi array kosong untuk menyimpan hasil
    const result = [];
    
    // Looping melalui setiap kalimat dalam array
    for (let i = 0; i < sentences.length; i++) {
        // Tambahkan kalimat saat ini ke dalam result
        result.push(sentences[i]);
        
        // Cek apakah kalimat saat ini mengandung stopWord
        if (sentences[i].includes(stopWord)) {
            // Jika ditemukan, hentikan pencarian
            break;
        }
    }
    
    // Kembalikan array result yang berisi kalimat-kalimat
    return result;
}
```

## 🔍 Cara Kerja

1. **Inisialisasi**: Fungsi membuat array kosong bernama `result` untuk menyimpan kalimat-kalimat
2. **Iterasi**: Fungsi melakukan loop through setiap kalimat dalam array `sentences`
3. **Penambahan**: Setiap kalimat ditambahkan ke dalam array `result`
4. **Pengecekan**: Fungsi mengecek apakah kalimat saat ini mengandung `stopWord` menggunakan method `includes()`
5. **Penghentian**: Jika `stopWord` ditemukan, loop dihentikan dengan `break`
6. **Return**: Fungsi mengembalikan array `result` yang berisi semua kalimat dari awal hingga kalimat yang mengandung `stopWord`

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

## ⚠️ Catatan Penting

- Fungsi ini melakukan pencarian **case-sensitive**, artinya "Hujan" dan "hujan" dianggap berbeda
- Jika `stopWord` tidak ditemukan, fungsi akan mengembalikan seluruh array `sentences`
- Fungsi menggunakan method `includes()` yang akan mencocokkan substring, jadi "hujan" akan cocok dengan "kehujanan"
- Pencarian dihentikan segera setelah menemukan kalimat pertama yang mengandung `stopWord`

## 🚀 Use Case

Fungsi ini berguna untuk:
- **Parsing teks**: Memotong teks pada kata kunci tertentu
- **Analisis konten**: Mengambil bagian awal dari konten hingga kata kunci tertentu
- **Preprocessing data**: Memfilter data teks berdasarkan kata kunci
- **Chatbot/NLP**: Mengidentifikasi konteks percakapan hingga kata kunci tertentu

## 🔧 Modifikasi yang Bisa Dilakukan

- Tambahkan parameter `caseSensitive` untuk mengatur sensitivitas huruf
- Gunakan regex untuk pencarian yang lebih kompleks
- Tambahkan parameter `includeStopWord` untuk menentukan apakah kalimat yang mengandung stopWord ikut disertakan atau tidak
