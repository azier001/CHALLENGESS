# 🏖️ Sunny Beach Day Seashell Arrangement

## 🌟 Overview Challenge

**Level Kesulitan:** `Easy` 🟢

Buat sebuah function bernama `sunnyBeachDay` yang mentransformasi koleksi seashells berdasarkan posisi matahari dan keajaiban hari pantai!

## 🎯 Skenario

Bayangkan diri Anda sedang menikmati hari pantai yang sempurna di bawah sinar matahari, dengan hati-hati menyusun seashells cantik di atas handuk pantai berwarna-warni. Saat matahari bergerak melintasi langit, ia mempengaruhi koleksi seashells Anda dengan cara yang misterius, dan Anda perlu menyusun ulang mengikuti aturan alam.

## 📋 Spesifikasi Function

### Function Signature
```javascript
function sunnyBeachDay(seashells, sunPosition)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `seashells` | `Array<number>` | Array integer (1-5) yang merepresentasikan berbagai jenis seashells |
| `sunPosition` | `number` | Index di mana matahari bersinar paling terang (0 ≤ sunPosition < seashells.length) |

### Return Value
- **Type:** `Array<number>`
- **Deskripsi:** Seashells yang telah disusun ulang setelah menerapkan semua aturan transformasi

## 🔄 Aturan Transformasi

Ikuti langkah-langkah ini secara berurutan untuk membuat susunan pantai yang sempurna:

### 1. ↩️ Reverse Berdasarkan Posisi Matahari
- **Sisi Kiri:** Reverse semua seashells di sebelah **kiri** posisi matahari
- **Sisi Kanan:** Reverse semua seashells di sebelah **kanan** posisi matahari
- **Posisi Matahari:** Seashell di posisi matahari tetap tidak berubah pada awalnya

### 2. ☀️ Efek Pemutihan Matahari
- Ganti semua seashells **tipe 3** dengan seashells **tipe 2**
- *Alasan:* Sinar matahari yang intens memutihkan kerang tipe 3, mengubah bentuknya

### 3. ✨ Penempatan Premium
- Pindahkan semua seashells **tipe 5** ke **awal** array
- *Alasan:* Ini adalah kerang terindah dan layak mendapat tempat teratas di handuk Anda
- Pertahankan urutan relatif mereka saat memindahkan

## 💡 Contoh Walkthrough

```
Initial: [1, 3, 2, 4, 5]  sunPosition: 2
Step 1:  [3, 1, 2, 4, 5]  (reverse kiri: [1,3] → [3,1], reverse kanan: [4,5] → [5,4])
Step 2:  [2, 1, 2, 5, 4]  (ganti 3→2)
Step 3:  [5, 2, 1, 2, 4]  (pindahkan tipe 5 ke depan)
```

## 🏁 Expected Output

Function Anda harus mengembalikan array yang tersusun dengan indah yang merepresentasikan layout akhir seashells di handuk pantai Anda, mengikuti semua aturan transformasi yang terkena sinar matahari.

---

*Happy coding, dan nikmati hari pantai virtual Anda! 🌊🐚*
