# 🔓 Fungsi unlockDoor

## 📋 Deskripsi

Fungsi `unlockDoor` adalah sebuah simulasi untuk membuka pintu dengan kode tertentu. Fungsi ini akan mencoba membuka pintu dengan melakukan percobaan dari angka 1 hingga jumlah percobaan yang ditentukan. Jika kode pintu ditemukan dalam rentang percobaan tersebut, pintu akan terbuka. Jika tidak, fungsi akan mengembalikan petunjuk yang diberikan.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `doorCode` | Number | Kode untuk membuka pintu (angka yang harus ditemukan) |
| `numAttempts` | Number | Jumlah maksimal percobaan yang diizinkan |
| `clue` | String | Petunjuk yang akan dikembalikan jika pintu gagal dibuka |

## 📝 Kode Fungsi

```javascript
function unlockDoor(doorCode, numAttempts, clue) {
  // Melakukan percobaan dari 1 hingga jumlah percobaan maksimal
  for (let i = 1; i <= numAttempts; i++) {
    // Jika nomor percobaan sama dengan kode pintu
    if (i === doorCode) {
      // Kembalikan pesan sukses dengan kode yang benar
      return "Door unlocked! The code was " + doorCode;
    }
  }
  
  // Jika semua percobaan gagal, kembalikan petunjuk
  return clue;
}
```

## 📊 Cara Kerja

1. **Iterasi Percobaan**: Fungsi akan melakukan loop dari angka 1 sampai `numAttempts`
2. **Pencocokan Kode**: Setiap iterasi akan mengecek apakah nomor percobaan saat ini sama dengan `doorCode`
3. **Hasil Sukses**: Jika kode ditemukan, fungsi mengembalikan pesan sukses
4. **Hasil Gagal**: Jika semua percobaan habis tanpa menemukan kode, fungsi mengembalikan `clue`

## 🎯 Contoh Penggunaan

### Contoh 1: Pintu Berhasil Dibuka
```javascript
const hasil1 = unlockDoor(3, 5, "Coba angka yang lebih kecil");
console.log(hasil1);
// Output: "Door unlocked! The code was 3"
```

### Contoh 2: Pintu Gagal Dibuka
```javascript
const hasil2 = unlockDoor(8, 5, "Angka terlalu besar, coba yang lebih kecil");
console.log(hasil2);
// Output: "Angka terlalu besar, coba yang lebih kecil"
```

### Contoh 3: Kode di Batas Percobaan
```javascript
const hasil3 = unlockDoor(10, 10, "Hampir berhasil!");
console.log(hasil3);
// Output: "Door unlocked! The code was 10"
```

## 📈 Tabel Hasil Berdasarkan Input

| doorCode | numAttempts | clue | Hasil |
|----------|-------------|------|-------|
| 2 | 5 | "Terlalu rendah" | "Door unlocked! The code was 2" |
| 7 | 5 | "Terlalu tinggi" | "Terlalu tinggi" |
| 1 | 3 | "Coba lagi" | "Door unlocked! The code was 1" |
| 10 | 8 | "Hampir benar" | "Hampir benar" |

## ⚠️ Catatan Penting

- Fungsi ini hanya akan berhasil jika `doorCode` berada dalam rentang 1 sampai `numAttempts`
- Jika `doorCode` lebih besar dari `numAttempts`, pintu tidak akan pernah terbuka
- Jika `doorCode` adalah 0 atau negatif, pintu tidak akan terbuka karena loop dimulai dari 1
- Parameter `clue` sangat berguna untuk memberikan petunjuk kepada pengguna saat gagal

## 🎮 Skenario Penggunaan

Fungsi ini cocok digunakan untuk:
- **Game puzzle**: Sebagai mekanisme membuka pintu dalam permainan
- **Simulasi keamanan**: Untuk mempelajari konsep brute force attack
- **Pembelajaran programming**: Sebagai contoh penggunaan loop dan conditional statement
- **Sistem akses sederhana**: Untuk prototype sistem keamanan dasar
