# 🫐 Counting Brierberries

## Level Challenge
**Easy** ⭐

---

## 📋 Deskripsi Masalah

Buat sebuah function bernama `countBrierberries` yang menerima sebuah array berisi angka-angka dengan nama `bushes`. Setiap angka merepresentasikan jumlah brierberries pada sebuah semak.

### 🎯 Tujuan

Hitung **total jumlah brierberries** yang dipetik dari semak-semak tersebut.

### ⚠️ Aturan Khusus

**Jika sebuah semak memiliki lebih dari 10 brierberries, hentikan pemetikan segera dan return total yang sudah terkumpul.**

---

## 📝 Function Signature

```javascript
function countBrierberries(bushes)
```

### Parameters

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `bushes` | `Array<number>` | Sebuah array dimana setiap elemen merepresentasikan jumlah brierberries pada sebuah semak |

### Returns

- **Tipe:** `number`
- **Deskripsi:** Total jumlah brierberries yang dipetik sebelum menemukan semak dengan lebih dari 10 buah berry

---

## 🔒 Constraints

- ✅ Input array akan **selalu berisi minimal satu elemen**
- ✅ Semua elemen dalam input array adalah **bilangan bulat non-negatif**

---

## 💡 Contoh

### Contoh 1: Kasus Normal
```javascript
countBrierberries([3, 5, 2, 7])
// Output: 17
// Penjelasan: 3 + 5 + 2 + 7 = 17 (semua semak memiliki ≤ 10 berries)
```

### Contoh 2: Berhenti Lebih Awal
```javascript
countBrierberries([4, 6, 15, 3, 2])
// Output: 10
// Penjelasan: 4 + 6 = 10, lalu berhenti (semak berikutnya memiliki 15 > 10)
```

### Contoh 3: Semak Pertama Melebihi Batas
```javascript
countBrierberries([12, 5, 3])
// Output: 0
// Penjelasan: Semak pertama memiliki 12 > 10, jadi berhenti segera
```

### Contoh 4: Tepat 10 Berries
```javascript
countBrierberries([10, 5, 3])
// Output: 18
// Penjelasan: 10 + 5 + 3 = 18 (10 tidak lebih besar dari 10, jadi lanjutkan)
```

---

## 🎓 Konsep Utama

Challenge ini menguji pemahaman Anda tentang:

- 🔄 **Iterasi array** dengan terminasi dini
- 🔢 **Pola accumulator** untuk menjumlahkan nilai
- ✋ **Logika kondisional** untuk menghentikan loop
- 📊 **Penanganan edge case**

---

## 💭 Petunjuk

<details>
<summary>Klik untuk melihat petunjuk</summary>

1. Anda perlu melakukan iterasi melalui array secara berurutan
2. Simpan total running dari berries yang terkumpul
3. Periksa jumlah berry pada setiap semak sebelum menambahkannya ke total
4. Ingat: jika sebuah semak memiliki **lebih dari 10** (bukan sama dengan 10), hentikan segera
5. Pertimbangkan menggunakan loop `for` dengan statement `break`, atau loop `while`

</details>

---

**Selamat Coding!** 🚀
