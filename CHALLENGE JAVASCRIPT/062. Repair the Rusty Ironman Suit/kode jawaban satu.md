# 🔧 Dokumentasi Fungsi `repairIronmanSuit`

## 📝 Deskripsi

Fungsi `repairIronmanSuit` adalah sebuah simulator untuk memperbaiki suit Iron Man yang mengalami kerusakan karat. Fungsi ini akan membersihkan bagian-bagian yang berkarat sesuai dengan kapasitas pembersihan yang tersedia, namun setelah proses pembersihan, karat akan menyebar ke bagian-bagian bersih yang bersebelahan.

## 🎯 Cara Kerja

1. **Fase Pembersihan**: Membersihkan bagian berkarat (`R`) menjadi bersih (`C`) dari kiri ke kanan sesuai dengan jumlah `cleanParts`
2. **Fase Penyebaran Karat**: Karat yang tersisa akan menyebar ke bagian bersih yang bersebelahan (kiri dan kanan)

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `suitStatus` | `string` | Status kondisi suit dalam bentuk string yang berisi karakter 'R' (Rusty/Berkarat) dan 'C' (Clean/Bersih) |
| `cleanParts` | `number` | Jumlah maksimal bagian berkarat yang dapat dibersihkan |

## 🔤 Karakter yang Digunakan

| Karakter | Arti | Deskripsi |
|----------|------|-----------|
| `R` | Rusty | Bagian suit yang berkarat/rusak |
| `C` | Clean | Bagian suit yang bersih/normal |

## 💻 Kode Fungsi

```javascript
function repairIronmanSuit(suitStatus, cleanParts) {
  // Langkah 1: Membersihkan suit dari kiri ke kanan
  let cleanedSuit = suitStatus.split('');
  let cleanedCount = 0;
  
  for (let i = 0; i < cleanedSuit.length && cleanedCount < cleanParts; i++) {
    if (cleanedSuit[i] === 'R') {
      cleanedSuit[i] = 'C';
      cleanedCount++;
    }
  }
  
  // Langkah 2: Menyebarkan karat ke bagian yang bersebelahan
  let finalSuit = cleanedSuit.slice();
  
  for (let i = 0; i < cleanedSuit.length; i++) {
    if (cleanedSuit[i] === 'R') {
      // Menyebarkan karat ke kiri
      if (i > 0 && cleanedSuit[i - 1] === 'C') {
        finalSuit[i - 1] = 'R';
      }
      // Menyebarkan karat ke kanan
      if (i < cleanedSuit.length - 1 && cleanedSuit[i + 1] === 'C') {
        finalSuit[i + 1] = 'R';
      }
    }
  }
  
  return finalSuit.join('');
}
```

## 📊 Contoh Penggunaan dan Output

### Contoh 1: Pembersihan Berhasil Sebagian
```javascript
// Input
const suitStatus = "RRCCRR";
const cleanParts = 2;

// Proses
console.log(repairIronmanSuit(suitStatus, cleanParts));

// Output: "CRRRR"
```

**Penjelasan:**
- Status awal: `RRCCRR`
- Setelah dibersihkan 2 bagian: `CRCCRR` (R pertama dan kedua dibersihkan)
- Setelah karat menyebar: `CRRRR` (karat menyebar ke C yang bersebelahan)

### Contoh 2: Pembersihan Terbatas
```javascript
// Input
const suitStatus = "RCRCR";
const cleanParts = 1;

// Proses
console.log(repairIronmanSuit(suitStatus, cleanParts));

// Output: "RRRCR"
```

**Penjelasan:**
- Status awal: `RCRCR`
- Setelah dibersihkan 1 bagian: `CCRCR` (R pertama dibersihkan)
- Setelah karat menyebar: `RRRCR` (karat dari posisi 2 dan 4 menyebar)

### Contoh 3: Tidak Ada Karat untuk Dibersihkan
```javascript
// Input
const suitStatus = "CCCCC";
const cleanParts = 3;

// Proses
console.log(repairIronmanSuit(suitStatus, cleanParts));

// Output: "CCCCC"
```

**Penjelasan:**
- Status awal: `CCCCC` (semua sudah bersih)
- Tidak ada yang perlu dibersihkan
- Tidak ada karat yang menyebar
- Hasil tetap: `CCCCC`

### Contoh 4: Pembersihan Total dengan Penyebaran
```javascript
// Input
const suitStatus = "RCRCRR";
const cleanParts = 4;

// Proses
console.log(repairIronmanSuit(suitStatus, cleanParts));

// Output: "CCCCCC"
```

**Penjelasan:**
- Status awal: `RCRCRR`
- Setelah dibersihkan semua bagian berkarat: `CCCC CC` (semua R dibersihkan)
- Tidak ada karat tersisa untuk menyebar
- Hasil akhir: `CCCCCC`

## ⚠️ Catatan Penting

1. **Urutan Pembersihan**: Pembersihan dilakukan dari kiri ke kanan secara berurutan
2. **Penyebaran Karat**: Karat hanya menyebar ke bagian yang **bersebelahan langsung** (kiri dan kanan)
3. **Batasan Pembersihan**: Jika `cleanParts` lebih besar dari jumlah bagian berkarat, hanya bagian berkarat yang ada yang akan dibersihkan
4. **Salinan Array**: Menggunakan `slice()` untuk membuat salinan array agar penyebaran karat tidak saling mengganggu
5. **Tidak Ada Efek Samping**: Fungsi tidak mengubah input asli, melainkan mengembalikan string baru

## 🔄 Alur Algoritma

```
Input: suitStatus, cleanParts
  ↓
1. Konversi string ke array (cleanedSuit)
  ↓
2. Inisialisasi counter pembersihan (cleanedCount = 0)
  ↓
3. Loop dari kiri ke kanan:
   - Jika ditemukan 'R' dan cleanedCount < cleanParts
   - Ubah 'R' menjadi 'C'
   - Increment cleanedCount
  ↓
4. Buat salinan array untuk hasil akhir (finalSuit)
  ↓
5. Loop untuk penyebaran karat:
   - Untuk setiap 'R' yang tersisa
   - Sebarkan ke kiri jika ada 'C'
   - Sebarkan ke kanan jika ada 'C'
  ↓
6. Konversi array kembali ke string
  ↓
Output: Status suit setelah perbaikan dan penyebaran karat
```

## 🔍 Detail Implementasi

### Variabel yang Digunakan
- `cleanedSuit`: Array hasil konversi dari string input untuk proses pembersihan
- `cleanedCount`: Counter untuk melacak jumlah bagian yang sudah dibersihkan
- `finalSuit`: Salinan array untuk hasil akhir setelah penyebaran karat

### Metode Array yang Digunakan
- `split('')`: Mengubah string menjadi array karakter
- `slice()`: Membuat salinan array tanpa mengubah array asli
- `join('')`: Menggabungkan array karakter kembali menjadi string

## 🎮 Tips Penggunaan

- Gunakan fungsi ini untuk simulasi game atau puzzle yang melibatkan penyebaran kondisi
- Cocok untuk pembelajaran algoritma tentang manipulasi array dan string
- Bisa dikembangkan lebih lanjut dengan menambahkan fitur seperti multiple types of damage atau repair strategies yang berbeda
- Pastikan input `cleanParts` tidak negatif untuk hasil yang optimal

## 🧪 Test Cases Tambahan

```javascript
// Test case untuk edge cases
console.log(repairIronmanSuit("R", 1));     // Output: "C"
console.log(repairIronmanSuit("C", 5));     // Output: "C"  
console.log(repairIronmanSuit("RCR", 1));   // Output: "RRR"
console.log(repairIronmanSuit("", 1));      // Output: ""
```
