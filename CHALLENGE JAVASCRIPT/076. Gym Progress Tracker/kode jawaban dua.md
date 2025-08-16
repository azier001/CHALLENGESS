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
  // Cek apakah array memiliki panjang yang sama dan elemen yang sama dalam urutan yang sama
  if (day1Exercises.length === day2Exercises.length &&
      day1Exercises.every((exercise, index) => exercise === day2Exercises[index])) {
    return "You did the same workout on both days!";
  } else {
    return "You mixed it up today!";
  }
}
```

## 🎯 Cara Kerja

1. **Pengecekan Panjang Array**: Fungsi pertama-tama membandingkan panjang kedua array
2. **Perbandingan Elemen**: Jika panjangnya sama, fungsi menggunakan `every()` method untuk membandingkan setiap elemen pada index yang sama
3. **Return Result**: Berdasarkan hasil perbandingan, fungsi mengembalikan pesan yang sesuai

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

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive**, artinya "Push-up" dan "push-up" dianggap berbeda
- Urutan latihan sangat penting - array `["A", "B"]` dan `["B", "A"]` dianggap berbeda
- Fungsi tidak memeriksa validitas nama latihan, hanya membandingkan string

## 🚀 Tips Penggunaan

1. **Konsistensi Penamaan**: Gunakan format penamaan latihan yang konsisten (misalnya selalu lowercase)
2. **Tracking Variasi**: Gunakan hasil fungsi untuk memastikan Anda memvariasikan latihan
3. **Integrasi**: Dapat diintegrasikan dengan aplikasi fitness tracking yang lebih besar

## 🔍 Kemungkinan Pengembangan

- Menambahkan toleransi untuk case-insensitive comparison
- Menambahkan fitur untuk mengabaikan urutan latihan
- Menambahkan tracking untuk intensitas atau repetisi latihan
