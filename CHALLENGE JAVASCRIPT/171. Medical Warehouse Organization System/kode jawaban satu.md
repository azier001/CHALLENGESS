# 📦 Dokumentasi Fungsi `organizeWarehouse()`

## 📝 Deskripsi Fungsi

Fungsi `organizeWarehouse()` adalah sebuah fungsi yang dirancang untuk **mengorganisir dan mengelola data persediaan barang di gudang**. Fungsi ini mengelompokkan barang berdasarkan jenisnya, mengurutkan berdasarkan nomor lot, menghitung total unit, dan membuat label untuk setiap kelompok barang.

Fungsi ini sangat berguna untuk:
- 🏭 Manajemen inventori gudang
- 📊 Pengorganisasian stok barang
- 🏷️ Pembuatan label dan penempatan rak
- 📈 Perhitungan total persediaan per jenis

---

## 🔧 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `supplies` | Array | Array yang berisi objek-objek barang dengan properti `type`, `lotNumber`, dan `units` |

### Struktur Objek dalam Array `supplies`:

```javascript
{
  type: String,        // Jenis/tipe barang (contoh: "elektronik", "furniture")
  lotNumber: Number,   // Nomor lot/batch barang
  units: Number        // Jumlah unit barang
}
```

---

## 🎯 Penjelasan Cara Kerja

Fungsi ini bekerja melalui 3 tahap utama:

1. **Pengelompokan** 📂
   - Mengelompokkan semua barang berdasarkan jenisnya (`type`)
   - Barang dengan jenis yang sama dikumpulkan dalam satu array

2. **Pengurutan & Perhitungan** 🔢
   - Mengurutkan setiap kelompok berdasarkan nomor lot dari yang terkecil hingga terbesar
   - Menghitung total unit untuk setiap jenis barang
   - Membuat label unik untuk setiap barang

3. **Output Hasil** 📋
   - Mengembalikan objek yang berisi informasi lengkap setiap jenis barang

---

## 💻 Kode Asli (Dengan Komentar Bahasa Indonesia)

```javascript
function organizeWarehouse(supplies) {
  // Membuat objek kosong untuk menyimpan barang yang sudah dikelompokkan
  const grouped = {};
  
  // Tahap 1: Mengelompokkan barang berdasarkan jenis
  supplies.forEach(supply => {
    // Jika jenis barang belum ada di dalam grouped, buat array baru
    if (!grouped[supply.type]) {
      grouped[supply.type] = [];
    }
    // Tambahkan barang ke dalam kelompoknya
    grouped[supply.type].push(supply);
  });
  
  // Tahap 2: Memproses setiap kelompok barang
  const result = {};
  let shelfPosition = 1;
  
  // Proses setiap jenis barang
  Object.keys(grouped).forEach(type => {
    // Urutkan barang dalam kelompok berdasarkan nomor lot (dari kecil ke besar)
    grouped[type].sort((a, b) => a.lotNumber - b.lotNumber);
    
    // Hitung total unit untuk jenis barang ini
    const totalUnits = grouped[type].reduce((sum, item) => sum + item.units, 0);
    
    // Buat label untuk setiap barang dengan format: JENIS_LOTX
    const labels = grouped[type].map(item => 
      `${type.toUpperCase()}_LOT${item.lotNumber}`
    );
    
    // Simpan hasil ke dalam objek result
    result[type] = {
      totalUnits: totalUnits,         // Total unit untuk jenis ini
      shelfPosition: shelfPosition,   // Posisi rak
      labels: labels                  // Label barang
    };
    
    // Naikkan posisi rak untuk jenis barang berikutnya
    shelfPosition++;
  });
  
  // Kembalikan hasil pengorganisasian
  return result;
}
```

---

## 📤 Output (Contoh Hasil)

### Input Contoh:

```javascript
const supplies = [
  { type: "elektronik", lotNumber: 3, units: 15 },
  { type: "elektronik", lotNumber: 1, units: 20 },
  { type: "furniture", lotNumber: 2, units: 5 },
  { type: "elektronik", lotNumber: 2, units: 10 },
  { type: "furniture", lotNumber: 1, units: 8 }
];

const hasil = organizeWarehouse(supplies);
console.log(hasil);
```

### Output Hasil:

```javascript
{
  elektronik: {
    totalUnits: 45,
    shelfPosition: 1,
    labels: ["ELEKTRONIK_LOT1", "ELEKTRONIK_LOT2", "ELEKTRONIK_LOT3"]
  },
  furniture: {
    totalUnits: 13,
    shelfPosition: 2,
    labels: ["FURNITURE_LOT1", "FURNITURE_LOT2"]
  }
}
```

---

## 📊 Penjelasan Tabel Output

| Properti | Nilai | Penjelasan |
|----------|-------|-----------|
| `totalUnits` | `45` | Total jumlah unit barang elektronik (20 + 10 + 15) |
| `shelfPosition` | `1` | Elektronik ditempatkan di rak ke-1 |
| `labels` | Array | Label setiap lot diurutkan dari lot terkecil hingga terbesar |
| `totalUnits` | `13` | Total jumlah unit furniture (5 + 8) |
| `shelfPosition` | `2` | Furniture ditempatkan di rak ke-2 (berturut-turut setelah elektronik) |

---

## 🔍 Contoh Penggunaan Praktis

### Contoh 1: Manajemen Gudang Toko Buku

```javascript
// Data persediaan gudang toko buku
const persediaan = [
  { type: "buku", lotNumber: 5, units: 100 },
  { type: "buku", lotNumber: 2, units: 75 },
  { type: "alat_tulis", lotNumber: 1, units: 200 },
  { type: "buku", lotNumber: 3, units: 50 },
  { type: "alat_tulis", lotNumber: 3, units: 150 }
];

// Jalankan fungsi
const hasilOrganisasi = organizeWarehouse(persediaan);

// Tampilkan hasil
console.log("Hasil Organisasi Gudang:");
console.log(hasilOrganisasi);

// Output:
// {
//   buku: {
//     totalUnits: 225,
//     shelfPosition: 1,
//     labels: ["BUKU_LOT2", "BUKU_LOT3", "BUKU_LOT5"]
//   },
//   alat_tulis: {
//     totalUnits: 350,
//     shelfPosition: 2,
//     labels: ["ALAT_TULIS_LOT1", "ALAT_TULIS_LOT3"]
//   }
// }
```

### Contoh 2: Mengakses Hasil Organisasi

```javascript
const hasilOrganisasi = organizeWarehouse(persediaan);

// Mendapatkan total unit buku
console.log("Total Unit Buku:", hasilOrganisasi.buku.totalUnits); 
// Output: 225

// Mendapatkan posisi rak alat tulis
console.log("Posisi Rak Alat Tulis:", hasilOrganisasi.alat_tulis.shelfPosition);
// Output: 2

// Mendapatkan semua label buku
console.log("Label Buku:", hasilOrganisasi.buku.labels);
// Output: ["BUKU_LOT2", "BUKU_LOT3", "BUKU_LOT5"]
```

---

## ⚙️ Tips Penggunaan

✅ **Yang Boleh Dilakukan:**
- Gunakan untuk mengelola berbagai jenis barang dengan lot berbeda
- Cocok untuk sistem gudang otomatis dan manajemen inventory
- Dapat diperluas untuk kebutuhan reporting dan laporan stok
- Hasil dapat digunakan untuk pembuatan label barcode

⚠️ **Hal yang Perlu Diperhatikan:**
- Pastikan setiap objek dalam array memiliki properti `type`, `lotNumber`, dan `units`
- Nilai `lotNumber` harus berupa angka untuk pengurutan yang benar
- Nilai `units` harus berupa angka positif untuk kalkulasi yang akurat
- Jenis barang (`type`) sebaiknya ditulis dengan format yang konsisten

---

## 🚀 Keunggulan Fungsi

| Keunggulan | Penjelasan |
|-----------|-----------|
| ⚡ **Efisien** | Proses pengelompokan dan pengurutan dilakukan dalam satu fungsi |
| 🏷️ **Otomatis Label** | Membuat label secara otomatis sesuai format yang diinginkan |
| 📦 **Terstruktur** | Output yang rapi dan mudah diakses untuk kebutuhan lanjutan |
| 🔢 **Perhitungan Akurat** | Total unit dihitung dengan akurat menggunakan `reduce()` |

---

## 🎓 Kesimpulan

Fungsi `organizeWarehouse()` adalah solusi praktis dan efisien untuk mengorganisir persediaan gudang secara otomatis. Dengan mengelompokkan, mengurutkan, dan membuat label, fungsi ini memudahkan manajemen inventory, penempatan barang di rak, serta pembuatan laporan stok dengan struktur yang terorganisir dengan baik.
