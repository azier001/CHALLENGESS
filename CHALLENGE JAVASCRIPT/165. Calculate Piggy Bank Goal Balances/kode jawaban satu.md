# 📊 Dokumentasi Fungsi `calculateGoalBalances`

## 🎯 Deskripsi

Fungsi `calculateGoalBalances` digunakan untuk menghitung total saldo dari setiap tujuan (goal) berdasarkan transaksi-transaksi yang ada. Fungsi ini akan memproses array yang berisi kumpulan transaksi untuk setiap tujuan, kemudian menghitung jumlah total dari semua transaksi di setiap tujuan tersebut.

**Kegunaan:**
- Menghitung saldo akhir dari berbagai tujuan keuangan
- Meringkas total transaksi per kategori/tujuan
- Mengubah data transaksi menjadi informasi saldo yang mudah dibaca

---

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `transactions` | `Array<Array<Number>>` | Array 2 dimensi yang berisi kumpulan transaksi. Setiap elemen adalah array berisi angka-angka yang merepresentasikan nilai transaksi untuk satu tujuan. |

**Penjelasan Detail:**
- Parameter `transactions` adalah array yang berisi array lainnya (nested array)
- Setiap sub-array merepresentasikan satu tujuan/goal
- Angka-angka di dalam sub-array adalah nilai transaksi (bisa positif atau negatif)

---

## 🔧 Kode Fungsi

```javascript
function calculateGoalBalances(transactions) {
    // Melakukan iterasi pada setiap goal dalam array transactions
    return transactions.map(goal => {
        
        // Menghitung total saldo dengan menjumlahkan semua transaksi
        // Dimulai dari nilai awal 0, kemudian ditambahkan dengan setiap amount
        return goal.reduce((sum, amount) => sum + amount, 0);
    });
}
```

---

## 📖 Cara Kerja

1. **Map**: Fungsi menggunakan `.map()` untuk mengiterasi setiap goal dalam array `transactions`
2. **Reduce**: Untuk setiap goal, fungsi menggunakan `.reduce()` untuk menjumlahkan semua nilai transaksi
3. **Akumulasi**: 
   - `sum` = nilai akumulasi (dimulai dari 0)
   - `amount` = setiap nilai transaksi yang ditambahkan ke sum
4. **Return**: Mengembalikan array baru berisi total saldo untuk setiap goal

---

## 💡 Contoh Penggunaan

### Contoh 1: Tujuan Tabungan Sederhana

```javascript
const transaksiTabungan = [
  [100000, 50000, 25000],      // Goal 1: Tabungan Liburan
  [200000, -50000, 100000],    // Goal 2: Dana Darurat
  [500000, 250000, 150000]     // Goal 3: Beli Gadget
];

const hasilSaldo = calculateGoalBalances(transaksiTabungan);
console.log(hasilSaldo);
```

**Output:**
```javascript
[175000, 250000, 900000]
```

**Penjelasan:**
- Goal 1 (Tabungan Liburan): 100.000 + 50.000 + 25.000 = **175.000**
- Goal 2 (Dana Darurat): 200.000 - 50.000 + 100.000 = **250.000**
- Goal 3 (Beli Gadget): 500.000 + 250.000 + 150.000 = **900.000**

---

### Contoh 2: Dengan Transaksi Negatif (Penarikan)

```javascript
const transaksiHarian = [
  [50000, 30000, -10000],      // Saldo Harian
  [100000, -25000, -25000, 50000]  // Saldo Mingguan
];

const saldo = calculateGoalBalances(transaksiHarian);
console.log(saldo);
```

**Output:**
```javascript
[70000, 100000]
```

**Penjelasan:**
- Saldo Harian: 50.000 + 30.000 - 10.000 = **70.000**
- Saldo Mingguan: 100.000 - 25.000 - 25.000 + 50.000 = **100.000**

---

## ⚠️ Catatan Penting

- Pastikan setiap elemen dalam array `transactions` adalah array yang berisi angka
- Transaksi negatif akan mengurangi saldo total
- Jika array goal kosong `[]`, hasilnya akan `0`
- Fungsi tidak mengubah array asli (non-destructive)

---

## 🎓 Tips untuk Pemula

1. **Array 2 Dimensi**: Bayangkan seperti tabel, di mana setiap baris adalah satu tujuan, dan setiap kolom adalah transaksi
2. **Map vs Reduce**: 
   - `map()` = untuk mengubah setiap elemen array
   - `reduce()` = untuk menggabungkan semua elemen menjadi satu nilai
3. **Arrow Function**: `=>` adalah cara singkat menulis fungsi di JavaScript modern
4. **Return Eksplisit**: Fungsi ini menggunakan `return` eksplisit di dalam map untuk kejelasan

---

## 📚 Referensi Metode

- [Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

---

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
