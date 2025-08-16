# 💪 Gym Progress Tracker

Fungsi JavaScript untuk melacak dan membandingkan latihan gym antara dua hari berbeda. Fungsi ini membantu Anda memantau apakah Anda melakukan latihan yang sama atau berbeda di hari yang berbeda.

## 📋 Deskripsi Fungsi

`gymProgressTracker` adalah fungsi yang membandingkan dua array latihan dari hari yang berbeda untuk menentukan apakah latihan yang dilakukan sama persis atau berbeda. Fungsi ini berguna untuk tracking rutinitas gym dan memberikan feedback tentang variasi latihan.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `day1Exercises` | Array | Array berisi daftar latihan yang dilakukan di hari pertama |
| `day2Exercises` | Array | Array berisi daftar latihan yang dilakukan di hari kedua |

## 📤 Return Value

Fungsi ini mengembalikan string dengan dua kemungkinan:
- `"You did the same workout on both days!"` - Jika latihan di kedua hari sama persis
- `"You mixed it up today!"` - Jika latihan di kedua hari berbeda

## 💻 Source Code

```javascript
function gymProgressTracker(day1Exercises, day2Exercises) {
  // Cek apakah panjang array berbeda
  if (day1Exercises.length !== day2Exercises.length) {
    return "You mixed it up today!";
  }
  
  // Loop untuk membandingkan setiap elemen pada index yang sama
  for (let i = 0; i < day1Exercises.length; i++) {
    // Jika ada elemen yang berbeda pada index yang sama
    if (day1Exercises[i] !== day2Exercises[i]) {
      return "You mixed it up today!";
    }
  }
  
  // Jika semua elemen sama, return pesan latihan sama
  return "You did the same workout on both days!";
}
```

## 🎯 Cara Kerja

1. **Pengecekan Panjang Array**: Fungsi pertama-tama membandingkan panjang kedua array. Jika berbeda, langsung return "You mixed it up today!"
2. **Perbandingan Elemen dengan Loop**: Menggunakan for loop untuk membandingkan setiap elemen pada index yang sama
3. **Early Return**: Jika ditemukan perbedaan pada elemen manapun, langsung return "You mixed it up today!"
4. **Return Default**: Jika semua elemen sama, return "You did the same workout on both days!"

## 📊 Contoh Penggunaan

### Contoh 1: Latihan yang Sama
```javascript
const hari1 = ["push-up", "pull-up", "squat"];
const hari2 = ["push-up", "pull-up", "squat"];

console.log(gymProgressTracker(hari1, hari2));
// Output: "You did the same workout on both days!"
```

### Contoh 2: Latihan yang Berbeda (Urutan Berbeda)
```javascript
const hari1 = ["push-up", "pull-up", "squat"];
const hari2 = ["squat", "push-up", "pull-up"];

console.log(gymProgressTracker(hari1, hari2));
// Output: "You mixed it up today!"
```

### Contoh 3: Jumlah Latihan Berbeda
```javascript
const hari1 = ["push-up", "pull-up"];
const hari2 = ["push-up", "pull-up", "squat"];

console.log(gymProgressTracker(hari1, hari2));
// Output: "You mixed it up today!"
```

### Contoh 4: Latihan Berbeda
```javascript
const hari1 = ["bench-press", "deadlift", "squat"];
const hari2 = ["push-up", "pull-up", "burpee"];

console.log(gymProgressTracker(hari1, hari2));
// Output: "You mixed it up today!"
```

### Contoh 5: Array Kosong
```javascript
const hari1 = [];
const hari2 = [];

console.log(gymProgressTracker(hari1, hari2));
// Output: "You did the same workout on both days!"
```

## ⚡ Keunggulan Implementasi

- **Efisien**: Menggunakan early return untuk menghentikan proses segera setelah menemukan perbedaan
- **Readable**: Kode mudah dibaca dan dipahami dengan struktur yang jelas
- **Performance**: Loop berhenti segera setelah menemukan perbedaan pertama, tidak perlu memeriksa seluruh array

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive**, artinya "Push-up" dan "push-up" dianggap berbeda
- Urutan latihan sangat penting - array `["A", "B"]` dan `["B", "A"]` dianggap berbeda
- Fungsi tidak memeriksa validitas nama latihan, hanya membandingkan string
- Array kosong dianggap sama (kedua array kosong akan return "same workout")

## 🚀 Tips Penggunaan

1. **Konsistensi Penamaan**: Gunakan format penamaan latihan yang konsisten (misalnya selalu lowercase)
2. **Tracking Variasi**: Gunakan hasil fungsi untuk memastikan Anda memvariasikan latihan
3. **Integrasi**: Dapat diintegrasikan dengan aplikasi fitness tracking yang lebih besar
4. **Validasi Input**: Pertimbangkan untuk menambahkan validasi bahwa parameter adalah array

## 🔍 Kemungkinan Pengembangan

- Menambahkan toleransi untuk case-insensitive comparison
- Menambahkan fitur untuk mengabaikan urutan latihan
- Menambahkan tracking untuk intensitas atau repetisi latihan
- Menambahkan validasi input untuk memastikan parameter adalah array
- Menambahkan opsi untuk partial matching (misalnya 80% sama dianggap sama)
