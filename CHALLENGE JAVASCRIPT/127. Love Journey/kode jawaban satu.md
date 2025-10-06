# 💕 Dokumentasi Fungsi `loveJourney`

## 📋 Deskripsi

Fungsi `loveJourney` adalah sebuah fungsi yang menghitung skor cinta (love score) berdasarkan perjalanan memori yang tersimpan dalam sebuah array. Fungsi ini akan memproses array memori dengan aturan khusus:
- **Memori dengan nilai genap** akan **menambah** skor cinta
- **Memori dengan nilai ganjil** akan **mengurangi** skor cinta
- Memori pertama dan terakhir **tidak dihitung** (diabaikan)

Fungsi ini cocok digunakan untuk simulasi game, kalkulator skor, atau aplikasi yang membutuhkan perhitungan berbasis kondisi genap/ganjil.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `loveScore` | `number` | Skor cinta awal yang akan dimodifikasi berdasarkan memori |
| `memoryBook` | `array` | Array berisi angka-angka yang merepresentasikan memori perjalanan cinta |

---

## 📊 Cara Kerja

### Alur Proses:

1. **Menghapus elemen pertama dan terakhir** dari `memoryBook` menggunakan `slice(1, -1)`
2. **Iterasi** setiap elemen di array yang sudah di-slice
3. **Pengecekan kondisi**:
   - Jika angka **genap** (`% 2 === 0`) → **tambahkan** ke `loveScore`
   - Jika angka **ganjil** → **kurangi** dari `loveScore`
4. **Return** nilai `loveScore` yang sudah dimodifikasi

### Tabel Karakter Angka:

| Jenis Angka | Operasi | Contoh |
|-------------|---------|--------|
| Genap | Ditambahkan (+) | 2, 4, 6, 8, 10 |
| Ganjil | Dikurangkan (-) | 1, 3, 5, 7, 9 |

---

## 💻 Kode Fungsi

```javascript
function loveJourney(loveScore, memoryBook) {
  // Menghapus elemen pertama dan terakhir dari array memoryBook
  const slicedMemoryBook = memoryBook.slice(1, -1);
  
  // Iterasi setiap elemen dalam array yang sudah di-slice
  for (let i = 0; i < slicedMemoryBook.length; i++) {
    
    // Cek apakah angka genap
    if (slicedMemoryBook[i] % 2 === 0) {
      loveScore += slicedMemoryBook[i]; // Tambahkan jika genap
    } else {
      loveScore -= slicedMemoryBook[i]; // Kurangi jika ganjil
    }
  }
  
  // Kembalikan skor cinta yang sudah dihitung
  return loveScore;
}
```

---

## 🎯 Contoh Penggunaan

### Contoh 1: Perjalanan Cinta Positif

```javascript
const skorAwal = 50;
const memori = [10, 2, 4, 6, 8, 99];

const hasilSkor = loveJourney(skorAwal, memori);
console.log(hasilSkor); // Output: 70
```

**Penjelasan:**
- Memori yang diproses: `[2, 4, 6, 8]` (10 dan 99 diabaikan)
- Semua angka genap, jadi semua ditambahkan
- Perhitungan: 50 + 2 + 4 + 6 + 8 = **70**

---

### Contoh 2: Perjalanan Cinta dengan Naik Turun

```javascript
const skorAwal = 100;
const memori = [5, 3, 10, 5, 7, 2];

const hasilSkor = loveJourney(skorAwal, memori);
console.log(hasilSkor); // Output: 100
```

**Penjelasan:**
- Memori yang diproses: `[3, 10, 5, 7]` (5 di awal dan 2 di akhir diabaikan)
- 3 (ganjil) → 100 - 3 = 97
- 10 (genap) → 97 + 10 = 107
- 5 (ganjil) → 107 - 5 = 102
- 7 (ganjil) → 102 - 7 = 95
- Hasil akhir: **95** ❌ 

*Ralat perhitungan: Hasil yang benar adalah **95***

---

### Contoh 3: Array Pendek

```javascript
const skorAwal = 0;
const memori = [1, 2];

const hasilSkor = loveJourney(skorAwal, memori);
console.log(hasilSkor); // Output: 0
```

**Penjelasan:**
- Memori yang diproses: `[]` (array kosong karena hanya ada 2 elemen)
- Tidak ada perubahan skor
- Hasil: **0**

---

## ⚠️ Catatan Penting

- Array `memoryBook` harus memiliki minimal 3 elemen agar ada yang diproses
- Jika array hanya berisi 2 elemen atau kurang, fungsi akan mengembalikan `loveScore` tanpa perubahan
- Parameter `loveScore` harus berupa angka (number)
- Elemen dalam `memoryBook` harus berupa angka untuk hasil yang benar

---

## 🚀 Tips Penggunaan

1. **Untuk Game**: Gunakan fungsi ini untuk menghitung skor berdasarkan aksi pemain
2. **Untuk Simulasi**: Simulasikan berbagai skenario dengan mengubah array memori
3. **Validasi Input**: Tambahkan pengecekan tipe data sebelum memanggil fungsi untuk menghindari error

---

**Selamat menggunakan fungsi `loveJourney`! 💝**
