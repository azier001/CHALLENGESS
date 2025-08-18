# 🌾 Sort Crops Array dengan Angka Keberuntungan 13

## 📋 Gambaran Challenge

**Level Kesulitan:** `Easy` 🟢

Buat sebuah function yang mengurutkan array angka crops, namun dengan twist khusus yang melibatkan angka keberuntungan 13!

---

## 🎯 Tujuan

Buat sebuah function bernama `sortCrops` yang:
- Menerima sebuah array angka yang disebut `cropsArray`
- Mengurutkan array dalam **urutan ascending** (naik)
- **Aturan Khusus:** Jika angka `13` muncul dalam array, hentikan proses sorting pada posisi tersebut dan return array yang sudah diurutkan sebagian

---

## 📝 Spesifikasi Function

```javascript
function sortCrops(cropsArray) {
    // Implementasi Anda di sini
}
```

### Parameter
- `cropsArray` (Array): Sebuah array angka yang merepresentasikan crops

### Return
- Array: `cropsArray` yang sudah diurutkan (atau diurutkan sebagian)

---

## 💡 Contoh

### Contoh 1: Sorting Normal
```javascript
Input:  [4, 2, 7, 1]
Output: [1, 2, 4, 7]
```
*Tidak ada angka 13 - sorting ascending lengkap*

### Contoh 2: Menemukan 13 di Awal
```javascript
Input:  [9, 13, 5, 2, 8]
Output: [9, 13, 5, 2, 8]
```
*13 di index 1 - tidak ada sorting yang dilakukan*

### Contoh 3: Menemukan 13 di Tengah Array
```javascript
Input:  [6, 3, 13, 10, 2, 5]
Output: [3, 6, 13, 10, 2, 5]
```
*13 di index 2 - elemen sebelum index 2 diurutkan*

---

## 🔍 Aturan Utama

1. **Urutan Ascending**: Urutkan angka dari yang terkecil ke terbesar
2. **Angka Keberuntungan 13**: Ketika ditemukan, hentikan sorting segera
3. **Sorting Sebagian**: Hanya urutkan elemen **sebelum** posisi angka 13
4. **Return Original**: Jika 13 berada di awal, return array tanpa perubahan

---

## 🧠 Hint Algorithm

- Cari index angka 13 terlebih dahulu
- Jika 13 ada, hanya urutkan subarray sebelum index tersebut
- Jika 13 tidak ada, urutkan seluruh array
- Gabungkan bagian yang sudah diurutkan dengan bagian yang belum diurutkan

---

## ✅ Kriteria Sukses

Function Anda harus:
- ✓ Menangani array tanpa angka 13 (sorting lengkap)
- ✓ Menangani array dengan angka 13 di posisi mana pun (sorting sebagian)
- ✓ Mempertahankan urutan original setelah posisi 13
- ✓ Me-return `cropsArray` yang sudah dimodifikasi

---

*Selamat coding! 🚀*
