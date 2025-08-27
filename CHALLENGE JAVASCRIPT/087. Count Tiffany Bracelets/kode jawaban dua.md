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
3. **Iterasi Digit**: Melakukan perulangan pada setiap digit dalam string biner
4. **Penghitungan**: Menambah counter setiap kali menemukan digit '1'
5. **Return Hasil**: Mengembalikan total jumlah bit '1'

## 💻 Kode Fungsi

```javascript
function countTiffanyBracelets(num) {
    // Konversi angka ke representasi biner
    const binary = num.toString(2);
    
    // Inisialisasi penghitung
    let counter = 0;
    
    // Melakukan perulangan untuk setiap digit dalam biner
    for (let digit of binary) {
        // Jika digit adalah '1', tambah counter
        if (digit === '1') {
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
// Penjelasan: 5 dalam biner = "101" → ada 2 bit '1'
```

### Contoh 2: Angka yang Lebih Besar
```javascript
console.log(countTiffanyBracelets(15));
// Output: 4
// Penjelasan: 15 dalam biner = "1111" → ada 4 bit '1'
```

### Contoh 3: Angka dengan Pola Biner Kompleks
```javascript
console.log(countTiffanyBracelets(42));
// Output: 3
// Penjelasan: 42 dalam biner = "101010" → ada 3 bit '1'
```

## 📈 Tabel Contoh Input-Output

| Input | Representasi Biner | Jumlah Bit '1' | Output |
|-------|-------------------|----------------|--------|
| 0 | "0" | 0 | 0 |
| 1 | "1" | 1 | 1 |
| 3 | "11" | 2 | 2 |
| 7 | "111" | 3 | 3 |
| 8 | "1000" | 1 | 1 |
| 10 | "1010" | 2 | 2 |
| 31 | "11111" | 5 | 5 |

## ⚡ Kompleksitas

- **Time Complexity**: O(log n) - dimana n adalah nilai input, karena jumlah digit biner adalah log₂(n)
- **Space Complexity**: O(log n) - untuk menyimpan string representasi biner

## 🔍 Catatan Penting

- Fungsi ini hanya bekerja dengan bilangan bulat positif
- Untuk angka 0, fungsi akan mengembalikan 0
- Fungsi menggunakan metode `toString(2)` untuk konversi ke biner
- Sangat berguna dalam algoritma bit manipulation dan operasi bitwise

## 🛠️ Penggunaan Alternatif

Fungsi ini dapat digunakan untuk:
- Menghitung populasi bit dalam pemrograman sistem
- Algoritma optimasi yang melibatkan operasi bit
- Perhitungan dalam teori bilangan
- Analisis pola biner dalam data

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi penghitung bit '1' dalam representasi biner.*
