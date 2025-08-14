# 🌲 Dokumentasi Fungsi forestStroll

## 📖 Deskripsi

Fungsi `forestStroll` adalah sebuah fungsi JavaScript yang menghasilkan pola karakter berdasarkan aturan matematika tertentu. Fungsi ini mensimulasikan perjalanan di hutan dengan menghasilkan jalur (path) yang terdiri dari karakter-karakter khusus berdasarkan posisi langkah dalam perjalanan.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `n` | `number` | Jumlah langkah dalam perjalanan hutan (bilangan bulat positif) |

## 🗺️ Tabel Karakter Jalur

| Kondisi | Karakter | Arti |
|---------|----------|------|
| Angka habis dibagi 3 DAN 5 | `b` | **Branch** - Cabang pohon (kelipatan 15) |
| Angka habis dibagi 3 saja | `d` | **Dense** - Area lebat (kelipatan 3) |
| Angka habis dibagi 5 saja | `r` | **Rock** - Batu di jalur (kelipatan 5) |
| Kondisi lainnya | `*` | **Star** - Jalur biasa |

## 💻 Kode Fungsi

```javascript
function forestStroll(n) {
  let path = ''; // Inisialisasi string kosong untuk menyimpan jalur
  
  // Perulangan dari 1 sampai n untuk setiap langkah
  for (let i = 1; i <= n; i++) {
    
    // Cek apakah angka habis dibagi 3 DAN 5 (kelipatan 15)
    if (i % 3 === 0 && i % 5 === 0) {
      path += 'b'; // Tambahkan karakter 'b' untuk cabang
    } 
    // Cek apakah angka habis dibagi 3 saja
    else if (i % 3 === 0) {
      path += 'd'; // Tambahkan karakter 'd' untuk area lebat
    } 
    // Cek apakah angka habis dibagi 5 saja
    else if (i % 5 === 0) {
      path += 'r'; // Tambahkan karakter 'r' untuk batu
    } 
    // Untuk kondisi lainnya
    else {
      path += '*'; // Tambahkan karakter '*' untuk jalur biasa
    }
  }
  
  return path; // Kembalikan string jalur yang telah dibentuk
}
```

## 📋 Contoh Penggunaan dan Output

### Contoh 1: Perjalanan Pendek (n = 5)
```javascript
console.log(forestStroll(5));
// Output: "**d*r"
```

**Penjelasan langkah demi langkah:**
- Langkah 1: `*` (1 tidak habis dibagi 3 atau 5)
- Langkah 2: `*` (2 tidak habis dibagi 3 atau 5)
- Langkah 3: `d` (3 habis dibagi 3)
- Langkah 4: `*` (4 tidak habis dibagi 3 atau 5)
- Langkah 5: `r` (5 habis dibagi 5)

### Contoh 2: Perjalanan Sedang (n = 15)
```javascript
console.log(forestStroll(15));
// Output: "**d*rd*d**rd*db"
```

### Contoh 3: Perjalanan Panjang (n = 30)
```javascript
console.log(forestStroll(30));
// Output: "**d*rd*d**rd*db**d*rd*d**rd*db"
```

## 🧠 Cara Kerja Algoritma

1. **Inisialisasi**: Membuat string kosong `path` untuk menyimpan hasil
2. **Perulangan**: Melakukan iterasi dari 1 hingga `n`
3. **Pengecekan Kondisi**:
   - **Prioritas Tertinggi**: Cek kelipatan 15 (habis dibagi 3 DAN 5) → karakter `b`
   - **Prioritas Kedua**: Cek kelipatan 3 saja → karakter `d`
   - **Prioritas Ketiga**: Cek kelipatan 5 saja → karakter `r`
   - **Default**: Semua kondisi lain → karakter `*`
4. **Penggabungan**: Setiap karakter ditambahkan ke string `path`
5. **Return**: Mengembalikan string jalur lengkap

## ⚠️ Catatan Penting

- Fungsi ini menggunakan **1-based indexing** (mulai dari 1, bukan 0)
- Urutan pengecekan kondisi sangat penting karena menggunakan `else if`
- Kelipatan 15 (3×5) akan selalu menghasilkan karakter `b`, bukan `d` atau `r`
- Parameter `n` harus berupa bilangan bulat positif untuk hasil yang optimal

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- Membuat pola karakter berdasarkan aturan matematika
- Simulasi game atau visualisasi jalur
- Pembelajaran konsep modulo dan conditional logic
- Generating pattern untuk keperluan algoritma lainnya
