# 🪵 cutLumberForCabin - Fungsi Pemotong Kayu untuk Kabin

## 📋 Deskripsi

Fungsi `cutLumberForCabin` adalah sebuah utilitas untuk memproses kayu mentah menjadi potongan-potongan kayu yang siap digunakan untuk pembangunan kabin. Fungsi ini akan memotong kayu yang panjangnya melebihi standar menjadi potongan-potongan dengan panjang standar, sambil tetap mempertahankan sisa potongan yang masih berguna.

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `availableLumber` | Array | Array berisi panjang kayu-kayu yang tersedia (dalam satuan meter/feet) |
| `standardLength` | Number | Panjang standar yang diinginkan untuk setiap potongan kayu |

## 🔄 Cara Kerja

1. **Pemeriksaan Panjang**: Fungsi memeriksa setiap potongan kayu
2. **Kondisi Panjang/Sama**: Jika kayu lebih panjang atau sama dengan standar → dipotong menjadi beberapa bagian standar
3. **Kondisi Pendek**: Jika kayu lebih pendek dari standar → tetap disimpan apa adanya
4. **Sisa Potongan**: Sisa potongan yang tidak mencapai panjang standar tetap disimpan

## 💻 Kode Fungsi

```javascript
function cutLumberForCabin(availableLumber, standardLength) {
  // Array untuk menyimpan hasil kayu yang sudah diproses
  let processedLumber = [];
  
  // Loop melalui setiap potongan kayu menggunakan for...of
  for (let piece of availableLumber) {
    
    // Jika kayu lebih panjang atau sama dengan panjang standar
    if (piece >= standardLength) {
      // Hitung berapa banyak potongan standar yang bisa dibuat
      let numCuts = Math.floor(piece / standardLength);
      
      // Tambahkan setiap potongan standar ke hasil
      for (let i = 0; i < numCuts; i++) {
        processedLumber.push(standardLength);
      }
      
      // Hitung sisa potongan
      let remainder = piece % standardLength;
      
      // Tambahkan sisa potongan jika ada
      if (remainder > 0) {
        processedLumber.push(remainder);
      }
    } else {
      // Jika kayu lebih pendek dari standar, simpan apa adanya
      processedLumber.push(piece);
    }
  }
  
  // Kembalikan array kayu yang sudah diproses
  return processedLumber;
}
```

## 📊 Contoh Penggunaan

### Input:
```javascript
let kayuTersedia = [15, 8, 25, 12, 3];
let panjangStandar = 10;

let hasilPemotongan = cutLumberForCabin(kayuTersedia, panjangStandar);
```

### Output:
```javascript
[10, 5, 8, 10, 10, 5, 10, 2, 3]
```

### 📝 Penjelasan Hasil:

| Kayu Asli | Proses | Hasil Potongan |
|-----------|--------|----------------|
| 15 | 15 ≥ 10 → 15 ÷ 10 = 1 potong standar + sisa 5 | `[10, 5]` |
| 8 | 8 < 10 → Lebih pendek dari standar, tetap utuh | `[8]` |
| 25 | 25 ≥ 10 → 25 ÷ 10 = 2 potong standar + sisa 5 | `[10, 10, 5]` |
| 12 | 12 ≥ 10 → 12 ÷ 10 = 1 potong standar + sisa 2 | `[10, 2]` |
| 3 | 3 < 10 → Lebih pendek dari standar, tetap utuh | `[3]` |

**Hasil Akhir**: `[10, 5, 8, 10, 10, 5, 10, 2, 3]`

## 🔍 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Ini | Kelebihan |
|-------|-----------|-----------|
| **Loop Method** | `for...of` | Lebih modern dan mudah dibaca |
| **Kondisi** | `piece >= standardLength` | Mencakup kayu yang tepat sama dengan standar |
| **Variable Naming** | `piece`, `numCuts` | Lebih deskriptif dan mudah dipahami |

## 🎯 Kegunaan Praktis

- **Optimalisasi Material**: Memaksimalkan penggunaan kayu dengan meminimalkan limbah
- **Standardisasi**: Menghasilkan potongan kayu dengan ukuran yang seragam
- **Efisiensi**: Menghitung secara otomatis berapa banyak potongan standar yang bisa didapat
- **Fleksibilitas**: Dapat digunakan untuk berbagai ukuran standar yang berbeda
- **Penanganan Tepat**: Kayu yang tepat sama dengan panjang standar akan dipotong dengan benar

## 📖 Contoh Kasus Khusus

### Kayu Tepat Sama dengan Standar:
```javascript
let kayuSama = [10, 10, 10];
let standar = 10;
let hasil = cutLumberForCabin(kayuSama, standar);
// Output: [10, 10, 10] - semua kayu tetap utuh
```

### Kayu Kelipatan Sempurna:
```javascript
let kayuKelipatan = [20, 30, 40];
let standar = 10;
let hasil = cutLumberForCabin(kayuKelipatan, standar);
// Output: [10, 10, 10, 10, 10, 10, 10, 10] - tidak ada sisa
```

## ⚠️ Catatan Penting

- Fungsi ini tidak mengubah array input asli (`availableLumber`)
- Semua sisa potongan tetap disimpan, tidak ada yang terbuang
- Panjang standar harus berupa angka positif
- Array input harus berisi angka-angka yang merepresentasikan panjang kayu
- Kayu yang tepat sama dengan panjang standar akan tetap menghasilkan 1 potongan standar
