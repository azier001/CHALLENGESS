# 📿 Dokumentasi Fungsi `countTiffanyBracelets`

## 🎯 Deskripsi Fungsi

Fungsi `countTiffanyBracelets` adalah sebuah fungsi JavaScript yang menghitung jumlah bit bernilai '1' dalam representasi biner dari suatu angka. Fungsi ini berguna untuk menentukan berapa banyak posisi bit yang aktif (bernilai 1) dalam suatu bilangan bulat.

## 📋 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `num` | `number` | Bilangan bulat yang akan dihitung jumlah bit '1'-nya |

## 🔧 Cara Kerja

1. **Konversi ke Biner**: Fungsi mengubah angka desimal menjadi string representasi biner
2. **Inisialisasi Counter**: Membuat variabel penghitung dimulai dari 0
3. **Iterasi dengan Index**: Melakukan perulangan menggunakan indeks untuk setiap karakter dalam string biner
4. **Penghitungan**: Menambah counter setiap kali menemukan karakter '1'
5. **Return Hasil**: Mengembalikan total jumlah bit '1'

## 💻 Kode Fungsi

```javascript
function countTiffanyBracelets(num) {
  // Konversi angka ke representasi biner
  const binary = num.toString(2);
  
  // Inisialisasi penghitung
  let counter = 0;
  
  // Melakukan perulangan dengan indeks untuk setiap karakter dalam string biner
  for (let i = 0; i < binary.length; i++) {
    // Jika karakter pada indeks i adalah '1', tambah counter
    if (binary[i] === '1') {
      counter++;
    }
  }
  
  // Mengembalikan jumlah total bit '1'
  return counter;
}
```

## 📊 Contoh Penggunaan dan Output

### Contoh 1: Angka Sederhana
```javascript
console.log(countTiffanyBracelets(5));
// Output: 2
// Penjelasan: 5 dalam biner = "101" → ada 2 bit '1' (pada indeks 0 dan 2)
```

### Contoh 2: Angka yang Lebih Besar
```javascript
console.log(countTiffanyBracelets(15));
// Output: 4
// Penjelasan: 15 dalam biner = "1111" → ada 4 bit '1' (pada semua indeks)
```

### Contoh 3: Angka dengan Pola Biner Kompleks
```javascript
console.log(countTiffanyBracelets(42));
// Output: 3
// Penjelasan: 42 dalam biner = "101010" → ada 3 bit '1' (pada indeks 0, 2, dan 4)
```

## 📈 Tabel Contoh Input-Output

| Input | Representasi Biner | Indeks dengan '1' | Jumlah Bit '1' | Output |
|-------|-------------------|-------------------|----------------|--------|
| 0 | "0" | - | 0 | 0 |
| 1 | "1" | 0 | 1 | 1 |
| 3 | "11" | 0, 1 | 2 | 2 |
| 7 | "111" | 0, 1, 2 | 3 | 3 |
| 8 | "1000" | 0 | 1 | 1 |
| 10 | "1010" | 0, 2 | 2 | 2 |
| 31 | "11111" | 0, 1, 2, 3, 4 | 5 | 5 |

## ⚡ Kompleksitas

- **Time Complexity**: O(log n) - dimana n adalah nilai input, karena jumlah iterasi sama dengan jumlah digit biner yaitu log₂(n)
- **Space Complexity**: O(log n) - untuk menyimpan string representasi biner

## 🔍 Catatan Penting

- Fungsi ini hanya bekerja dengan bilangan bulat positif
- Untuk angka 0, fungsi akan mengembalikan 0
- Fungsi menggunakan metode `toString(2)` untuk konversi ke biner
- Perulangan menggunakan indeks tradisional (`for` loop) yang memungkinkan akses posisi karakter
- Sangat berguna dalam algoritma bit manipulation dan operasi bitwise

## 🛠️ Penggunaan Alternatif

Fungsi ini dapat digunakan untuk:
- Menghitung populasi bit dalam pemrograman sistem
- Algoritma optimasi yang melibatkan operasi bit
- Perhitungan dalam teori bilangan
- Analisis pola biner dalam data
- Implementasi algoritma Hamming weight

## 🔄 Variasi Implementasi

### Menggunakan For...of Loop
```javascript
function countTiffanyBracelets(num) {
  const binary = num.toString(2);
  let counter = 0;
  
  for (let digit of binary) {
    if (digit === '1') {
      counter++;
    }
  }
  
  return counter;
}
```

### Menggunakan Built-in Methods
```javascript
function countTiffanyBracelets(num) {
  return num.toString(2).split('1').length - 1;
}
```

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi penghitung bit '1' dalam representasi biner menggunakan iterasi dengan indeks.*
