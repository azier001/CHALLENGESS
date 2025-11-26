# 🥪 Sandwich Shop Order and Table Management

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Medium`

Toko sandwich di lingkungan Anda perlu melacak pesanan yang tertunda dan mengelola tempat duduk secara efisien selama jam makan siang yang sibuk. Bantu mereka menyederhanakan operasi dengan membuat sistem manajemen!

---

## 🎯 Tujuan

Tulis sebuah function `processShopOrders` yang menerima `orders` dan `tableStatuses` sebagai input dan mengembalikan object yang berisi:
- Jumlah sandwich untuk semua pesanan yang tertunda
- Meja yang tersedia untuk pelanggan baru

---

## 🧠 Persyaratan Logika

Solusi Anda harus mencapai hal-hal berikut:

1. **Menghitung Pesanan Sandwich**  
   Hitung berapa kali setiap jenis sandwich muncul dalam daftar pesanan yang tertunda

2. **Mengidentifikasi Meja yang Tersedia**  
   Tentukan meja mana yang saat ini tersedia untuk pelanggan baru

3. **Membuat Ringkasan Manajemen**  
   Gabungkan kedua informasi tersebut menjadi satu laporan yang mudah dibaca

---

## ⚙️ Kondisi & Aturan

- ✅ Hanya hitung meja dengan status `"available"` sebagai yang kosong
- 📊 Status meja dapat berupa salah satu dari tiga nilai:
  - `"available"` - Siap untuk pelanggan baru
  - `"occupied"` - Sedang digunakan
  - `"reserved"` - Dipesan untuk pelanggan di masa depan
- 🔢 Sertakan jenis sandwich dalam perhitungan meskipun jumlahnya `0`

---

## 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `orders` | `array` | Array nama sandwich yang sedang disiapkan |
| `tableStatuses` | `array` | Array string status meja |

---

## 📤 Return Value

**Type:** `Object`

**Format:**
```json
{
  "sandwichCounts": {
    "BLT": 2,
    "Club": 1
  },
  "availableTables": [1, 3]
}
```

### Rincian Struktur:

- **`sandwichCounts`** (Object)  
  Pasangan key-value dimana key adalah nama sandwich dan value adalah jumlahnya

- **`availableTables`** (Array)  
  Daftar indeks meja (berbasis 0) yang memiliki status `"available"`

---

## 💡 Contoh Penggunaan

```javascript
const orders = ["BLT", "Club", "BLT", "Veggie"];
const tableStatuses = ["occupied", "available", "reserved", "available"];

const result = processShopOrders(orders, tableStatuses);
console.log(result);
// Output:
// {
//   sandwichCounts: { BLT: 2, Club: 1, Veggie: 1 },
//   availableTables: [1, 3]
// }
```

---

## 🚀 Memulai

Siap untuk menyelesaikan challenge ini? Mulai dengan:

1. Menyiapkan signature function Anda
2. Membuat struktur untuk menghitung sandwich
3. Memfilter status meja untuk menemukan yang tersedia
4. Menggabungkan hasil ke dalam format yang diperlukan

Semangat! 🎉
