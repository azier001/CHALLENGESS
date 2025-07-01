# 🏞️ Hiker's Trail Marker Challenge

> **Difficulty**: 🟢 Easy  
> **Category**: JavaScript / Function Logic

---

## 🎯 **Challenge Overview**

Sebagai seorang pendaki yang berhati-hati, kamu sedang menjelajahi kaki pegunungan yang dikelilingi oleh ladang gandum emas. Untuk **menandai jejakmu**, kamu ingin membuat tanda balik jalan yang bisa dibaca dengan mudah.

---

## 🧠 **Tugas Utama**

Buatlah sebuah fungsi bernama `trailMarker` yang menerima dua parameter:

```js
trailMarker(steps, capitalize)
```

### 🧩 Parameter

| Parameter    | Tipe      | Deskripsi                                                                 |
|--------------|-----------|---------------------------------------------------------------------------|
| `steps`      | `array`   | Daftar string yang merepresentasikan langkah-langkah pendakianmu.         |
| `capitalize` | `boolean` | Menentukan apakah tiap langkah harus dikapitalisasi (uppercase) atau tidak.|

---

## 🔧 **Langkah-langkah yang Harus Dilakukan**

Fungsi `trailMarker` harus melakukan hal-hal berikut:

1. 🔁 **Balik urutan** dari langkah (`steps`) untuk menandai **jalur pulang**.
2. 🔠 Jika `capitalize` bernilai `true`, ubah semua langkah menjadi **huruf kapital**.
3. 🔗 Gabungkan langkah-langkah menggunakan tanda panah `' -> '` sebagai pemisah.
4. 🏔️ Tambahkan **emoji gunung** di **awal** dan **emoji sepatu pendaki** di **akhir** dari string.

---

## 📥 Contoh Input

```js
trailMarker(
  ["Uphill", "Through_Wheat", "Around_Rock", "Cross_Stream"],
  true
)
```

## 📤 Output yang Diharapkan

```
🏔️ CROSS_STREAM -> AROUND_ROCK -> THROUGH_WHEAT -> UPHILL 🥾
```

---

## ✅ Contoh Lain

```js
trailMarker(["Valley", "Bridge", "Forest"], false)
```

**Output:**

```
🏔️ Forest -> Bridge -> Valley 🥾
```

---

## 🧪 Tips

- Gunakan `.reverse()`, `.map()`, dan `.join()` untuk menyelesaikan tantangan ini.
- Jangan lupa tambahkan emoji di awal dan akhir string!

---
