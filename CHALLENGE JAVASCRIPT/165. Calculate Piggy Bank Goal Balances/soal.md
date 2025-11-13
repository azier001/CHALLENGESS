# 🐷 Calculate Piggy Bank Goal Balances

## Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Tulis sebuah function yang menghitung saldo akhir untuk beberapa savings goals dengan memproses data transaksi.

---

## 📋 Deskripsi Masalah

Buat function `calculateGoalBalances` yang memproses transaksi keuangan di berbagai savings goals dan mengembalikan saldo akhir untuk setiap goal.

Function menerima 2D array dimana:
- Setiap **inner array** merepresentasikan semua transaksi untuk savings goal tertentu
- **Angka positif** merepresentasikan deposit (uang yang ditambahkan)
- **Angka negatif** merepresentasikan withdrawal (uang yang ditarik)

---

## 🔧 Function Signature

```javascript
function calculateGoalBalances(transactions)
```

### Parameters

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `transactions` | `Array<Array<number>>` | 2D array yang berisi jumlah transaksi untuk setiap savings goal |

### Returns

| Tipe | Deskripsi | Format |
|------|-------------|--------|
| `Array<number>` | Array saldo akhir untuk setiap goal | `[balance1, balance2, balance3]` |

---

## 💡 Contoh

### Contoh 1: Transaksi Dasar

```javascript
const transactions = [
  [100, 50, -20],     // Goal 1: deposit $100, deposit $50, withdraw $20
  [200, -50, 100],    // Goal 2: deposit $200, withdraw $50, deposit $100
  [75, 25]            // Goal 3: deposit $75, deposit $25
];

calculateGoalBalances(transactions);
// Returns: [130, 250, 100]
```

### Contoh 2: Satu Transaksi Per Goal

```javascript
const transactions = [
  [500],
  [-100],
  [250]
];

calculateGoalBalances(transactions);
// Returns: [500, -100, 250]
```

---

## ✅ Requirements

- ✓ Proses semua transaksi untuk setiap savings goal
- ✓ Handle angka positif sebagai deposit
- ✓ Handle angka negatif sebagai withdrawal
- ✓ Return saldo akhir untuk setiap goal dengan urutan yang sama
- ✓ Support jumlah goals dan transaksi yang tidak terbatas

---

## 🎯 Konsep Utama

Challenge ini menguji pemahaman Anda tentang:

- **Array manipulation** - Bekerja dengan 2D arrays
- **Iteration** - Looping melalui struktur nested
- **Accumulation** - Menjumlahkan nilai untuk menghitung total
- **Data transformation** - Mengubah format input menjadi format output

---

## 💭 Hints

<details>
<summary>Klik untuk melihat hints</summary>

1. Anda perlu melakukan iterasi melalui setiap transaction array dari goal
2. Untuk setiap goal, jumlahkan semua transaction amounts
3. Method `reduce()` mungkin berguna di sini
4. Pertimbangkan menggunakan `map()` untuk mengubah 2D array menjadi array of balances

</details>

---

Semangat! 🚀
