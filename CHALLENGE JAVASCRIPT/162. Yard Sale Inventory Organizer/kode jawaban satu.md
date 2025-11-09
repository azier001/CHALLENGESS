# 📦 Dokumentasi Fungsi `organizeYardSale`

## 📝 Deskripsi

Fungsi `organizeYardSale` adalah fungsi untuk mengorganisir dan menghitung ringkasan barang-barang yang dijual dalam acara yard sale (garasi sale). Fungsi ini akan mengelompokkan barang berdasarkan kategori, menghitung jumlah item per kategori, dan menghitung total harga per kategori dengan pembulatan langsung setiap kali penambahan.

## ✨ Fitur Utama

- ✅ Mengelompokkan barang berdasarkan kategori
- ✅ Menghitung jumlah item per kategori
- ✅ Menghitung total harga per kategori
- ✅ Pembulatan otomatis setiap penambahan harga (mencegah error floating point)

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `items` | `Array<string>` | Array berisi string dengan format `"kategori:nama:harga"` |

### Format Input

Setiap item dalam array harus mengikuti format:
```
"kategori:nama_barang:harga"
```

**Contoh:**
- `"Electronics:Laptop:500"`
- `"Furniture:Chair:25.50"`
- `"Books:Novel:5"`

## 📤 Return Value

Fungsi mengembalikan objek dengan struktur:

| Property | Tipe | Deskripsi |
|----------|------|-----------|
| `[kategori]` | `Object` | Objek untuk setiap kategori |
| `[kategori].count` | `Number` | Jumlah item dalam kategori |
| `[kategori].total` | `Number` | Total harga dalam kategori (2 desimal) |

## 💻 Kode Fungsi

```javascript
function organizeYardSale(items) {
    // Objek untuk menyimpan inventori per kategori
    const inventory = {};
    
    // Loop melalui setiap item dalam array
    for (const item of items) {
        // Memisahkan string berdasarkan titik dua (:)
        const [category, name, priceStr] = item.split(':');
        
        // Konversi string harga menjadi angka desimal
        const price = parseFloat(priceStr);
        
        // Jika kategori belum ada, buat objek baru dengan count dan total
        if (!inventory[category]) {
            inventory[category] = {
                count: 0,
                total: 0
            };
        }
        
        // Tambahkan jumlah item
        inventory[category].count++;
        
        // Tambahkan harga ke total
        inventory[category].total += price;
        
        // Bulatkan total ke 2 angka desimal (mencegah error floating point)
        inventory[category].total = Math.round(inventory[category].total * 100) / 100;
    }
    
    return inventory;
}
```

## 🎯 Contoh Penggunaan

### Input

```javascript
const barangDijual = [
  "Electronics:Laptop:500",
  "Electronics:Mouse:15.50",
  "Furniture:Chair:25",
  "Furniture:Table:75.99",
  "Books:Novel:5",
  "Books:Magazine:2.50",
  "Books:Comic:3"
];

const hasil = organizeYardSale(barangDijual);
console.log(hasil);
```

### Output

```javascript
{
  Electronics: { count: 2, total: 515.5 },
  Furniture: { count: 2, total: 100.99 },
  Books: { count: 3, total: 10.5 }
}
```

## 📊 Penjelasan Output

Berdasarkan contoh di atas:

| Kategori | Jumlah Item | Total Harga | Detail |
|----------|-------------|-------------|--------|
| Electronics | 2 | $515.50 | Laptop ($500) + Mouse ($15.50) |
| Furniture | 2 | $100.99 | Chair ($25) + Table ($75.99) |
| Books | 3 | $10.50 | Novel ($5) + Magazine ($2.50) + Comic ($3) |

## 🔍 Cara Kerja

1. **Inisialisasi**: Membuat objek kosong `inventory` untuk menyimpan hasil
2. **Iterasi**: Loop melalui setiap item dalam array
3. **Parsing**: Memisahkan string dengan `.split(':')` menjadi kategori, nama, dan harga
4. **Konversi**: Mengubah harga dari string ke angka dengan `parseFloat()`
5. **Pengelompokan**: Jika kategori belum ada, buat entri baru dengan `count: 0` dan `total: 0`
6. **Perhitungan**: 
   - Tambahkan 1 ke `count`
   - Tambahkan harga ke `total`
   - **Langsung bulatkan** `total` ke 2 desimal setiap kali penambahan
7. **Return**: Kembalikan objek inventory

## 🔬 Perbedaan Teknis

### Pembulatan Real-time vs Batch

Fungsi ini menggunakan **pembulatan real-time** (setiap iterasi):

```javascript
// Bulatkan langsung setiap kali menambah
inventory[category].total += price;
inventory[category].total = Math.round(inventory[category].total * 100) / 100;
```

**Keuntungan:**
- ✅ Mencegah akumulasi error floating point
- ✅ Setiap penambahan langsung presisi 2 desimal
- ✅ Lebih akurat untuk transaksi keuangan

**Cara kerja rumus pembulatan:**
1. `* 100` → menggeser 2 desimal ke kiri (515.50 → 51550)
2. `Math.round()` → membulatkan ke integer terdekat (51550 → 51550)
3. `/ 100` → mengembalikan 2 desimal (51550 → 515.50)

## ⚠️ Catatan Penting

- Pastikan format input benar dengan tanda `:` sebagai pemisah
- Harga harus berupa angka yang valid (mendukung desimal)
- Pembulatan dilakukan **setiap iterasi** untuk akurasi maksimal
- Kategori bersifat case-sensitive (huruf besar/kecil berpengaruh)
- Metode pembulatan ini sangat cocok untuk aplikasi finansial

## 🚀 Tips Penggunaan

- Gunakan nama kategori yang konsisten (misalnya selalu "Electronics", bukan "electronics" atau "ELECTRONICS")
- Pastikan harga tidak mengandung karakter mata uang (gunakan `500` bukan `$500`)
- Fungsi ini cocok untuk aplikasi inventory sederhana, sistem kasir mini, atau aplikasi keuangan
- Pembulatan real-time memastikan tidak ada akumulasi error saat banyak transaksi

## 💡 Contoh Kasus Penggunaan

### 1. Aplikasi Kasir
```javascript
const penjualan = [
  "Makanan:Nasi Goreng:15.5",
  "Makanan:Mie Ayam:12",
  "Minuman:Teh Manis:3.5",
  "Minuman:Kopi:5"
];

const laporan = organizeYardSale(penjualan);
// Output: Makanan (2 item, Rp27.5), Minuman (2 item, Rp8.5)
```

### 2. Inventory Toko Online
```javascript
const produk = [
  "Fashion:Kaos:50",
  "Fashion:Celana:100",
  "Elektronik:Headphone:75.99",
  "Elektronik:Charger:20.50"
];

const ringkasan = organizeYardSale(produk);
// Output: Fashion (2 item, $150), Elektronik (2 item, $96.49)
```

---

💡 **Dibuat untuk memudahkan pengelolaan data yard sale dan aplikasi sejenis dengan akurasi finansial tinggi!**
