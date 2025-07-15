# 🍿 Dokumentasi Fungsi `arrangeMovieNight`

## 📋 Deskripsi Fungsi

Fungsi `arrangeMovieNight` adalah sebuah fungsi JavaScript yang digunakan untuk mengatur camilan (snacks) untuk malam menonton film. Fungsi ini mengambil sebagian camilan dari array berdasarkan indeks yang ditentukan, kemudian mengurutkannya secara alfabetis.

## 🔧 Kode Fungsi

```javascript
function arrangeMovieNight(snacks, start, end) {
    // Memastikan start dan end berada dalam batas array
    start = Math.max(0, Math.min(start, snacks.length));
    end = Math.max(start, Math.min(end, snacks.length));
    
    // Mengekstrak dan mengurutkan sebagian dari array snacks
    const selectedSnacks = snacks.slice(start, end);
    selectedSnacks.sort();
    
    return selectedSnacks;
}
```

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `snacks` | Array | Array berisi daftar camilan (string) yang akan diatur |
| `start` | Number | Indeks awal untuk memilih camilan (inclusive) |
| `end` | Number | Indeks akhir untuk memilih camilan (exclusive) |

### 📌 Penjelasan Parameter

- **`snacks`**: Array yang berisi nama-nama camilan dalam bentuk string
- **`start`**: Posisi mulai pengambilan camilan (dimulai dari 0)
- **`end`**: Posisi akhir pengambilan camilan (tidak termasuk indeks ini)

## 🎯 Nilai Kembalian

Fungsi ini mengembalikan array baru yang berisi camilan yang telah diurutkan secara alfabetis dari bagian yang dipilih.

## 🔄 Cara Kerja Fungsi

1. **Penyesuaian Indeks**: Memastikan `start` dan `end` berada dalam rentang yang valid (0 hingga panjang array)
2. **Ekstraksi Data**: Mengambil sebagian array menggunakan method `slice(start, end)`
3. **Pengurutan**: Mengurutkan camilan secara alfabetis menggunakan method `sort()`
4. **Mengembalikan Hasil**: Mengembalikan array yang sudah diurutkan

## 📊 Contoh Penggunaan

### Contoh 1: Penggunaan Normal
```javascript
const snacks = ["Popcorn", "Nachos", "Candy", "Soda", "Chips"];
const result = arrangeMovieNight(snacks, 1, 4);
console.log(result);
// Output: ["Candy", "Nachos", "Soda"]
```

### Contoh 2: Menggunakan Seluruh Array
```javascript
const snacks = ["Pizza", "Ice Cream", "Cookies"];
const result = arrangeMovieNight(snacks, 0, 3);
console.log(result);
// Output: ["Cookies", "Ice Cream", "Pizza"]
```

### Contoh 3: Indeks Melebihi Batas
```javascript
const snacks = ["Chocolate", "Pretzels"];
const result = arrangeMovieNight(snacks, 0, 10);
console.log(result);
// Output: ["Chocolate", "Pretzels"]
```

### Contoh 4: Indeks Start Negatif
```javascript
const snacks = ["Apple", "Banana", "Cherry", "Donut"];
const result = arrangeMovieNight(snacks, -2, 3);
console.log(result);
// Output: ["Apple", "Banana", "Cherry"]
```

### Contoh 5: Start dan End Sama
```javascript
const snacks = ["Watermelon", "Grapes", "Orange"];
const result = arrangeMovieNight(snacks, 1, 1);
console.log(result);
// Output: []
```

## 📋 Tabel Contoh Input/Output

| Input Snacks | Start | End | Output |
|--------------|-------|-----|--------|
| `["Popcorn", "Nachos", "Candy"]` | 0 | 2 | `["Nachos", "Popcorn"]` |
| `["Soda", "Chips", "Pizza", "Cookies"]` | 1 | 3 | `["Chips", "Pizza"]` |
| `["Apple", "Banana", "Cherry"]` | 0 | 3 | `["Apple", "Banana", "Cherry"]` |
| `["Mango", "Kiwi", "Pear"]` | 2 | 2 | `[]` |
| `["Nuts", "Crackers"]` | -1 | 5 | `["Crackers", "Nuts"]` |

## ⚠️ Catatan Penting

- Fungsi ini tidak mengubah array asli (`snacks`), melainkan membuat array baru
- Jika `start` atau `end` melebihi panjang array, fungsi akan otomatis menyesuaikan ke batas yang valid
- Indeks negatif pada `start` akan diubah menjadi 0
- Pengurutan dilakukan secara alfabetis (case-sensitive)
- Jika `start` sama dengan `end`, fungsi akan mengembalikan array kosong

## 🚀 Tips Penggunaan

1. Pastikan array `snacks` berisi string untuk hasil pengurutan yang optimal
2. Gunakan indeks yang valid untuk menghindari hasil yang tidak diinginkan
3. Fungsi ini sangat berguna untuk mengatur daftar camilan berdasarkan preferensi urutan tertentu
4. Untuk mendapatkan semua elemen, gunakan `start = 0` dan `end = snacks.length`

## 🔍 Perbedaan dengan Versi Sebelumnya

Versi ini lebih sederhana dan tidak melakukan pengecekan untuk array kosong atau null. Pastikan untuk selalu memasukkan array yang valid sebagai parameter pertama.
