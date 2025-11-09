# 📦 Dokumentasi Fungsi `organizeYardSale`

## 📝 Deskripsi

Fungsi `organizeYardSale` adalah fungsi untuk mengorganisir dan menghitung ringkasan barang-barang yang dijual dalam acara yard sale (garasi sale). Fungsi ini akan mengelompokkan barang berdasarkan kategori, menghitung jumlah item per kategori, dan menghitung total harga per kategori.

## ✨ Fitur Utama

- ✅ Mengelompokkan barang berdasarkan kategori
- ✅ Menghitung jumlah item per kategori
- ✅ Menghitung total harga per kategori
- ✅ Pembulatan otomatis ke 2 angka desimal

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
  // Objek untuk menyimpan ringkasan per kategori
  const summary = {};
  
  // Loop melalui setiap item
  for (const item of items) {
    // Memisahkan string berdasarkan titik dua (:)
    const [category, name, price] = item.split(':');
    const priceNum = parseFloat(price);
    
    // Jika kategori belum ada, buat objek baru
    if (!summary[category]) {
      summary[category] = { count: 0, total: 0 };
    }
    
    // Tambahkan jumlah dan total harga
    summary[category].count++;
    summary[category].total += priceNum;
  }
  
  // Bulatkan total harga ke 2 angka desimal
  for (const category in summary) {
    summary[category].total = parseFloat(summary[category].total.toFixed(2));
  }
  
  return summary;
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

1. **Inisialisasi**: Membuat objek kosong `summary` untuk menyimpan hasil
2. **Iterasi**: Loop melalui setiap item dalam array
3. **Parsing**: Memisahkan string dengan `.split(':')` menjadi kategori, nama, dan harga
4. **Konversi**: Mengubah harga dari string ke angka dengan `parseFloat()`
5. **Pengelompokan**: Jika kategori belum ada, buat entri baru
6. **Perhitungan**: Tambahkan count dan total untuk setiap kategori
7. **Pembulatan**: Bulatkan semua total ke 2 angka desimal
8. **Return**: Kembalikan objek summary

## ⚠️ Catatan Penting

- Pastikan format input benar dengan tanda `:` sebagai pemisah
- Harga harus berupa angka yang valid
- Pembulatan otomatis dilakukan untuk menghindari masalah floating point
- Kategori bersifat case-sensitive (huruf besar/kecil berpengaruh)

## 🚀 Tips Penggunaan

- Gunakan nama kategori yang konsisten (misalnya selalu "Electronics", bukan "electronics" atau "ELECTRONICS")
- Pastikan harga tidak mengandung karakter mata uang (gunakan `500` bukan `$500`)
- Fungsi ini cocok untuk aplikasi inventory sederhana atau sistem kasir mini

---

💡 **Dibuat untuk memudahkan pengelolaan data yard sale dan aplikasi sejenis!**
