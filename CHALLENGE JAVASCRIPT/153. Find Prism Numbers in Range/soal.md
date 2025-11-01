# 🔢 Find Prism Numbers in Range

## Level Challenge
**Easy** ⭐

---

## 📋 Deskripsi

Buat sebuah function bernama `findPrismNumbers` yang menerima dua angka, `start` dan `end`. Function ini akan menemukan semua **prism numbers** antara `start` dan `end` (inklusif) dan mengembalikannya sebagai array.

---

## 🎯 Apa itu Prism Number?

**Prism number** adalah angka yang merupakan hasil perkalian dari dua angka berurutan.

### Definisi Matematis

Sebuah angka `n` adalah prism number jika:
```
n = k × (k + 1)
```
dimana `k` adalah bilangan bulat positif.

---

## 💡 Contoh

Berikut adalah beberapa contoh prism numbers:

| Prism Number | Perhitungan | Angka Berurutan |
|--------------|-------------|-----------------|
| 2            | 1 × 2       | 1 dan 2         |
| 6            | 2 × 3       | 2 dan 3         |
| 12           | 3 × 4       | 3 dan 4         |
| 20           | 4 × 5       | 4 dan 5         |
| 30           | 5 × 6       | 5 dan 6         |
| 42           | 6 × 7       | 6 dan 7         |
| 56           | 7 × 8       | 7 dan 8         |

### Contoh Detail

✅ **6 adalah prism number** karena merupakan hasil perkalian dari 2 dan 3.

✅ **30 adalah prism number** karena merupakan hasil perkalian dari 5 dan 6.

---

## 📝 Function Signature

```javascript
function findPrismNumbers(start, end) {
    // Implementasi Anda di sini
}
```

### Parameter

- **`start`** (Number): Angka awal dari range (inklusif)
- **`end`** (Number): Angka akhir dari range (inklusif)

### Return Value

- **Array**: Sebuah array yang berisi semua prism numbers yang ditemukan dalam range yang ditentukan

---

## 🧪 Test Cases

```javascript
// Contoh 1
findPrismNumbers(1, 10);
// Expected Output: [2, 6]

// Contoh 2
findPrismNumbers(5, 30);
// Expected Output: [6, 12, 20, 30]

// Contoh 3
findPrismNumbers(10, 50);
// Expected Output: [12, 20, 30, 42]
```

---

## 💭 Petunjuk

1. Pertimbangkan untuk melakukan iterasi melalui pasangan angka berurutan
2. Periksa apakah hasil perkaliannya berada dalam range yang diberikan
3. Anda dapat menghitung nilai maksimum `k` yang diperlukan berdasarkan nilai `end`
4. Ingat untuk menyertakan `start` dan `end` dalam pengecekan range Anda

---

## ⚡ Tantangan

Coba implementasikan function ini dengan efisien! Pikirkan tentang:
- Bagaimana meminimalkan perhitungan yang tidak perlu
- Bagaimana menangani edge cases (misalnya, ketika `start` > `end`)
- Pendekatan berbeda untuk menyelesaikan masalah ini

---

**Semangat! Selamat coding! 🚀**
