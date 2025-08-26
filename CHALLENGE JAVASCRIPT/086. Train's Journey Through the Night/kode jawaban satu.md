# 🚂 Dokumentasi Fungsi trainJourney

## 📝 Deskripsi

Fungsi `trainJourney` adalah fungsi JavaScript yang mengubah sebuah string dengan cara yang unik dan menyenangkan! Fungsi ini melakukan tiga langkah transformasi:

1. **Membalik urutan kata-kata** dalam string
2. **Mengkapitalisasi setiap karakter pada posisi ke-1, 4, 7, 10, dst.** (pola setiap 3 karakter dimulai dari posisi 1)
3. **Menambahkan " choo choo!"** di akhir string

Fungsi ini cocok digunakan untuk membuat efek teks yang lucu atau sebagai latihan manipulasi string.

## 🔧 Parameter

| Parameter | Tipe   | Wajib | Deskripsi |
|-----------|--------|-------|-----------|
| `str`     | String | Ya    | Teks yang akan diproses dan ditransformasi |

## 💻 Kode Fungsi

```javascript
function trainJourney(str) {
    // Langkah 1: Membalik urutan kata-kata dalam string
    let reversed = str.split(' ').reverse().join(' ');
    
    // Langkah 2: Mengkapitalisasi karakter pada posisi tertentu
    // (setiap 3 karakter dimulai dari posisi ke-1: posisi 1, 4, 7, 10, ...)
    let capitalized = '';
    
    for (let i = 0; i < reversed.length; i++) {
        if ((i + 1) % 3 === 1) {
            // Jika (indeks + 1) habis dibagi 3 dengan sisa 1, 
            // ubah menjadi huruf kapital
            capitalized += reversed[i].toUpperCase();
        } else {
            // Jika tidak, tetap gunakan karakter asli
            capitalized += reversed[i];
        }
    }
    
    // Langkah 3: Menambahkan " choo choo!" di akhir hasil
    return capitalized + ' choo choo!';
}
```

## 🎯 Cara Kerja Detail

### Langkah 1: Membalik Urutan Kata
- String dipecah menjadi array kata-kata menggunakan `split(' ')`
- Array dibalik menggunakan `reverse()`
- Array digabung kembali menjadi string menggunakan `join(' ')`

### Langkah 2: Kapitalisasi dengan Pola Khusus
- Fungsi melakukan loop melalui setiap karakter
- Menggunakan rumus `(i + 1) % 3 === 1` untuk menentukan posisi yang akan dikapitalisasi
- Karakter pada posisi 0, 3, 6, 9, dst. (indeks array) akan diubah menjadi huruf kapital
- Karakter lainnya tetap tidak berubah

### Langkah 3: Menambahkan Suara Kereta
- String " choo choo!" ditambahkan di akhir hasil

## 📊 Tabel Contoh Kapitalisasi

| Indeks Array | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10| 11|
|--------------|---|---|---|---|---|---|---|---|---|---|---|---|
| Posisi       | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |10 |11 |12 |
| (i+1) % 3    | 1 | 2 | 0 | 1 | 2 | 0 | 1 | 2 | 0 | 1 | 2 | 0 |
| Aksi         | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ |

*✅ = Dikapitalisasi, ❌ = Tetap sama*

## 🚀 Contoh Penggunaan

```javascript
// Contoh 1: Kalimat sederhana
console.log(trainJourney("hello world"));
// Output: "World Hello choo choo!"

// Contoh 2: Kalimat lebih panjang
console.log(trainJourney("i love programming"));
// Output: "Programming Love I choo choo!"

// Contoh 3: Satu kata
console.log(trainJourney("javascript"));
// Output: "Javascript choo choo!"
```

## 📈 Contoh Output Detail

### Input: `"hello world"`

1. **Setelah langkah 1** (balik kata): `"world hello"`
2. **Setelah langkah 2** (kapitalisasi): `"World Hello"`
   - Indeks 0: `w` → `W` (posisi 1, (0+1)%3=1 ✅)
   - Indeks 3: `l` → `L` (posisi 4, (3+1)%3=1 ✅)  
   - Indeks 6: `h` → `H` (posisi 7, (6+1)%3=1 ✅)
   - Indeks 9: `l` → `L` (posisi 10, (9+1)%3=1 ✅)
3. **Setelah langkah 3** (tambah suara): `"World Hello choo choo!"`

### Input: `"belajar coding"`

1. **Setelah langkah 1**: `"coding belajar"`
2. **Setelah langkah 2**: `"Coding Belajar"`
   - Indeks 0: `c` → `C`
   - Indeks 3: `i` → `I`
   - Indeks 6: ` ` (spasi tetap spasi)
   - Indeks 7: `b` → `B`
   - Indeks 10: `l` → `L`
   - Indeks 13: `j` → `J`
3. **Setelah langkah 3**: `"Coding Belajar choo choo!"`

### Input: `"test"`

1. **Setelah langkah 1**: `"test"`
2. **Setelah langkah 2**: `"Test"`
   - Indeks 0: `t` → `T` (posisi 1)
   - Indeks 3: `t` → `T` (posisi 4)
3. **Setelah langkah 3**: `"Test choo choo!"`

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** - huruf kapital dan kecil diperlakukan berbeda
- Spasi dihitung sebagai karakter dalam proses kapitalisasi
- Pola kapitalisasi menggunakan rumus `(i + 1) % 3 === 1` yang berarti:
  - Posisi 1, 4, 7, 10, ... akan dikapitalisasi
  - Indeks array 0, 3, 6, 9, ... akan dikapitalisasi
- Jika input kosong, output akan menjadi `" choo choo!"`
- Fungsi tidak melakukan validasi input, pastikan parameter berupa string

## 🔍 Perbedaan dengan Versi Lain

Versi ini menggunakan pola kapitalisasi yang berbeda:
- **Versi ini**: `(i + 1) % 3 === 1` → karakter pada indeks 0, 3, 6, 9...
- **Versi umum**: `i % 3 === 0` → karakter pada indeks 0, 3, 6, 9...

Hasilnya sama secara posisi, tetapi logika penghitungannya sedikit berbeda.

## 🎨 Kustomisasi

Anda bisa memodifikasi fungsi ini dengan:
- Mengganti `" choo choo!"` dengan suara lain
- Mengubah pola kapitalisasi dengan memodifikasi rumus `(i + 1) % 3 === 1`
- Menambahkan validasi input untuk memastikan parameter berupa string
- Menggunakan parameter nama yang lebih deskriptif seperti `inputString` alih-alih `str`

---

*Selamat bermain dengan fungsi trainJourney! 🚂💨*
