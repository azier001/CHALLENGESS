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
    // Mengubah string menjadi array untuk manipulasi yang lebih mudah
    let suit = suitStatus.split('');
    
    // Langkah 1: Membersihkan bagian berkarat dari kiri ke kanan
    let cleaned = 0;
    for (let i = 0; i < suit.length && cleaned < cleanParts; i++) {
        if (suit[i] === 'R') {
            suit[i] = 'C';
            cleaned++;
        }
    }
    
    // Langkah 2: Karat menyebar ke bagian bersih yang bersebelahan
    let newSuit = [...suit]; // Membuat salinan untuk menghindari interferensi saat penyebaran
    
    for (let i = 0; i < suit.length; i++) {
        if (suit[i] === 'R') {
            // Menyebarkan karat ke kiri
            if (i > 0 && suit[i - 1] === 'C') {
                newSuit[i - 1] = 'R';
            }
            // Menyebarkan karat ke kanan
            if (i < suit.length - 1 && suit[i + 1] === 'C') {
                newSuit[i + 1] = 'R';
            }
        }
    }
    
    // Mengembalikan hasil dalam bentuk string
    return newSuit.join('');
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

## ⚠️ Catatan Penting

1. **Urutan Pembersihan**: Pembersihan dilakukan dari kiri ke kanan
2. **Penyebaran Karat**: Karat hanya menyebar ke bagian yang **bersebelahan langsung** (kiri dan kanan)
3. **Batasan Pembersihan**: Jika `cleanParts` lebih besar dari jumlah bagian berkarat, hanya bagian berkarat yang ada yang akan dibersihkan
4. **Tidak Ada Efek Samping**: Fungsi tidak mengubah input asli, melainkan mengembalikan string baru

## 🔄 Alur Algoritma

```
Input: suitStatus, cleanParts
  ↓
1. Konversi string ke array
  ↓
2. Bersihkan bagian berkarat (R → C) dari kiri ke kanan
   sesuai batas cleanParts
  ↓
3. Buat salinan array untuk penyebaran karat
  ↓
4. Untuk setiap bagian berkarat yang tersisa:
   - Sebarkan ke kiri jika ada bagian bersih
   - Sebarkan ke kanan jika ada bagian bersih
  ↓
5. Konversi array kembali ke string
  ↓
Output: Status suit setelah perbaikan dan penyebaran karat
```

## 🎮 Tips Penggunaan

- Gunakan fungsi ini untuk simulasi game atau puzzle yang melibatkan penyebaran kondisi
- Cocok untuk pembelajaran algoritma tentang manipulasi array dan string
- Bisa dikembangkan lebih lanjut dengan menambahkan fitur seperti multiple types of damage atau repair strategies yang berbeda
