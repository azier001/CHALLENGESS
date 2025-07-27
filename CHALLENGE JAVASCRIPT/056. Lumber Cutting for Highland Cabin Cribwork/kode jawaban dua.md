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
2. **Kondisi Pendek**: Jika kayu lebih pendek dari standar → tetap disimpan apa adanya
3. **Kondisi Panjang**: Jika kayu lebih panjang dari standar → dipotong menjadi beberapa bagian standar
4. **Sisa Potongan**: Sisa potongan yang tidak mencapai panjang standar tetap disimpan

## 💻 Kode Fungsi

```javascript
function cutLumberForCabin(availableLumber, standardLength) {
    // Array untuk menyimpan hasil kayu yang sudah diproses
    let processedLumber = [];
    
    // Loop melalui setiap potongan kayu yang tersedia
    for (let i = 0; i < availableLumber.length; i++) {
        let currentPiece = availableLumber[i];
        
        // Jika kayu lebih pendek dari panjang standar
        if (currentPiece < standardLength) {
            // Simpan potongan kayu apa adanya
            processedLumber.push(currentPiece);
        } else {
            // Potong menjadi potongan-potongan dengan panjang standar
            let numberOfCuts = Math.floor(currentPiece / standardLength);
            
            // Tambahkan setiap potongan standar ke hasil
            for (let j = 0; j < numberOfCuts; j++) {
                processedLumber.push(standardLength);
            }
            
            // Tambahkan sisa potongan jika ada
            let remainder = currentPiece % standardLength;
            if (remainder > 0) {
                processedLumber.push(remainder);
            }
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
| 15 | 15 ÷ 10 = 1 potong standar + sisa 5 | `[10, 5]` |
| 8 | Lebih pendek dari standar, tetap utuh | `[8]` |
| 25 | 25 ÷ 10 = 2 potong standar + sisa 5 | `[10, 10, 5]` |
| 12 | 12 ÷ 10 = 1 potong standar + sisa 2 | `[10, 2]` |
| 3 | Lebih pendek dari standar, tetap utuh | `[3]` |

**Hasil Akhir**: `[10, 5, 8, 10, 10, 5, 10, 2, 3]`

## 🎯 Kegunaan Praktis

- **Optimalisasi Material**: Memaksimalkan penggunaan kayu dengan meminimalkan limbah
- **Standardisasi**: Menghasilkan potongan kayu dengan ukuran yang seragam
- **Efisiensi**: Menghitung secara otomatis berapa banyak potongan standar yang bisa didapat
- **Fleksibilitas**: Dapat digunakan untuk berbagai ukuran standar yang berbeda

## ⚠️ Catatan Penting

- Fungsi ini tidak mengubah array input asli (`availableLumber`)
- Semua sisa potongan tetap disimpan, tidak ada yang terbuang
- Panjang standar harus berupa angka positif
- Array input harus berisi angka-angka yang merepresentasikan panjang kayu
