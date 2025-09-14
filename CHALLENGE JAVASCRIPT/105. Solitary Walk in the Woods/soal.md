# 🌲 Solitary Walk in the Woods

## 📋 Deskripsi Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan jalan santai melalui hutan, di mana setiap langkah dapat memindahkan Anda maju atau mundur di jalur.

---

## 🎯 Deskripsi Masalah

Anda perlu mengimplementasikan function bernama `solitary_walk` yang menerima array berisi angka-angka yang merepresentasikan langkah-langkah yang diambil selama berjalan di hutan.

### Function Signature
```javascript
function solitary_walk(steps)
```

### 🚶‍♂️ Mekanisme Jalan

- **Angka positif** → Langkah maju
- **Angka negatif** → Langkah mundur
- **Aturan Keamanan**: Jika langkah berikutnya akan menghasilkan total negatif (mundur dari titik awal), **berhenti segera**
- **Tujuan**: Return total jumlah langkah yang diambil selama berjalan

---

## 📝 Requirements

### Input
- `steps`: Array angka yang merepresentasikan langkah individual
  - Berisi minimal satu elemen
  - Dapat mencakup nilai positif dan negatif

### Output
- Sebuah **number** yang merepresentasikan total langkah yang diambil selama berjalan

### Constraints
- ✅ Jalan berhenti jika langkah berikutnya akan membuat total menjadi negatif
- ✅ Jika tidak, selesaikan seluruh perjalanan
- ✅ Selalu return langkah kumulatif yang diambil

---

## 💡 Contoh

### Contoh 1: Jalan Lengkap
```javascript
solitary_walk([2, 3, -1, 4])
// Langkah: 0 → 2 → 5 → 4 → 8
// Hasil: 8
```

### Contoh 2: Berhenti Lebih Awal
```javascript
solitary_walk([3, -2, -4, 1])
// Langkah: 0 → 3 → 1 → (akan jadi -3, jadi berhenti)
// Hasil: 1
```

### Contoh 3: Satu Langkah
```javascript
solitary_walk([5])
// Langkah: 0 → 5
// Hasil: 5
```

---

## 🤔 Catatan Implementasi

1. **Track Posisi Saat Ini**: Simpan total berjalan dari posisi saat ini
2. **Lihat ke Depan**: Sebelum mengambil setiap langkah, periksa apakah akan menghasilkan posisi negatif
3. **Exit Lebih Awal**: Berhenti segera ketika langkah akan membuat Anda mundur ke negatif
4. **Return Total**: Selalu return posisi akhir (total langkah yang diambil)

---

## 🏃‍♂️ Pendekatan Algorithm

1. Inisialisasi posisi saat ini ke `0`
2. Untuk setiap langkah dalam array:
   - Hitung berapa posisi baru yang akan dicapai
   - Jika posisi baru akan negatif, return posisi saat ini
   - Jika tidak, update posisi saat ini
3. Return posisi akhir

---

## ⚠️ Edge Cases yang Perlu Dipertimbangkan

- Array dengan hanya angka negatif
- Array dimulai dengan angka negatif besar
- Campuran langkah positif dan negatif
- Array dengan satu elemen

---

**Selamat Coding! 🌟**
