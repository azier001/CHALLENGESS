# 🍿 Tantangan Movie Night Snack Organizer

## 🎯 Overview Challenge

**Tingkat Kesulitan:** `Easy`

Ciptakan pengalaman movie night yang nyaman dengan mengorganisir pilihan snack yang sempurna! Tugas Anda adalah membangun sebuah function yang mengurutkan sebagian snack secara alfabetis untuk movie night yang ultimate di ruang tamu yang furnished.

---

## 📋 Requirements Function

### Function Signature
```javascript
function arrangeMovieNight(snacks, start, end)
```

### 🎬 Apa yang Dilakukan
Function `arrangeMovieNight` mengambil koleksi snack movie dan mengembalikan pilihan yang terorganisir dengan sempurna, diurutkan secara alfabetis berdasarkan index yang ditentukan.

---

## 🔧 Langkah-langkah Implementation

Ikuti langkah-langkah berikut untuk menyelesaikan challenge:

1. **Extract Selection** 
   - Gunakan index `start` dan `end` untuk mengekstrak sebagian dari array `snacks`
   
2. **Sort Alphabetically**
   - Urutkan bagian yang diekstrak dalam urutan alfabetis
   
3. **Return Result**
   - Kembalikan selection yang sudah diurutkan sebagai array

---

## 📊 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `snacks` | `array` | Array string yang mewakili berbagai snack dan minuman untuk movie night |
| `start` | `number` | Index awal untuk selection (**inclusive**) |
| `end` | `number` | Index akhir untuk selection (**exclusive**) |

---

## 🎯 Return Value

**Type:** `Array<string>`

**Description:** Selection snack yang diurutkan berdasarkan index start dan end yang diberikan.

---

## ⚠️ Catatan Penting

> **Boundary Handling:** Pastikan untuk menangani kasus di mana `start` dan `end` mungkin berada di luar bounds array `snacks`. Jika ya, sesuaikan agar sesuai dengan bounds array.

### Edge Cases yang Perlu Dipertimbangkan:
- Index `start` bernilai negatif
- Index `end` melebihi panjang array
- `start` lebih besar dari `end`
- Input array kosong

---

## 💡 Contoh Penggunaan

```javascript
// Contoh array snacks
const movieSnacks = [
  "Popcorn", "Soda", "Candy", "Chips", "Nachos", 
  "Ice Cream", "Cookies", "Pretzels"
];

// Extract dan sort snacks dari index 2 sampai 5
const result = arrangeMovieNight(movieSnacks, 2, 5);
// Expected output: ["Candy", "Chips", "Nachos"] (diurutkan secara alfabetis)
```

---

## 🏆 Kriteria Sukses

- ✅ Function mengekstrak bagian array yang benar
- ✅ Bagian yang diekstrak diurutkan secara alfabetis
- ✅ Menangani index out-of-bounds dengan baik
- ✅ Mengembalikan format array yang tepat

---

*Siap untuk menciptakan lineup snack movie night yang sempurna? Mari kita coding! 🎬*
