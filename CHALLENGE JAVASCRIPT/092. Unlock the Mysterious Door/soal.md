# 🚪 Unlock the Mysterious Door

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Buat sebuah function yang mensimulasikan membuka pintu misterius dengan menebak kode yang benar melalui beberapa percobaan.

---

## 🎯 Tujuan

Implementasikan function bernama `unlockDoor` yang mencoba memecahkan kode pintu menggunakan pendekatan sistematis.

## 📝 Spesifikasi Function

### Function Signature
```javascript
function unlockDoor(doorCode, numAttempts, clue)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `doorCode` | `number` | Kode rahasia yang dibutuhkan untuk membuka pintu |
| `numAttempts` | `number` | Jumlah maksimum percobaan yang diizinkan untuk menebak kode |
| `clue` | `string` | Petunjuk yang diberikan ketika semua percobaan gagal |

---

## 🔧 Persyaratan Implementasi

### Logic Utama

1. **Struktur Loop**
   - Gunakan `for` loop yang iterasi dari `1` sampai `numAttempts`
   - Setiap iterasi merepresentasikan satu percobaan untuk menebak kode

2. **Pengecekan Kode**
   - Dalam setiap iterasi, cek apakah nomor iterasi saat ini sama dengan `doorCode`
   - Jika ditemukan kecocokan, langsung return pesan sukses

3. **Kondisi Sukses**
   ```javascript
   return "Door unlocked! The code was " + doorCode;
   ```

4. **Kondisi Gagal**
   - Jika loop selesai tanpa menemukan kode yang benar
   - Return string `clue` yang telah disediakan

---

## 💡 Alur Algorithm

```
MULAI
  ↓
FOR i = 1 TO numAttempts
  ↓
APAKAH i == doorCode?
  ↓ YA
RETURN "Door unlocked! The code was " + doorCode
  ↓ TIDAK
LANJUT LOOP
  ↓
LOOP SELESAI?
  ↓ YA
RETURN clue
  ↓
SELESAI
```

---

## 🧪 Perilaku yang Diharapkan

### Unlock Berhasil
- **Kondisi:** Nomor percobaan saat ini cocok dengan kode pintu
- **Hasil:** Pintu terbuka dengan pesan sukses

### Percobaan Gagal
- **Kondisi:** Semua percobaan habis tanpa menemukan kode
- **Hasil:** Clue diberikan untuk membantu memecahkan misteri

---

## 🎮 Contoh Penggunaan

```javascript
// Contoh 1: Kode ditemukan dalam percobaan
unlockDoor(3, 5, "Think of a magic number")
// Expected: "Door unlocked! The code was 3"

// Contoh 2: Kode tidak ditemukan dalam percobaan
unlockDoor(7, 5, "The answer lies in lucky numbers")
// Expected: "The answer lies in lucky numbers"
```

---

## 🏆 Kriteria Keberhasilan

- ✅ Function melakukan iterasi dengan benar melalui percobaan
- ✅ Mengidentifikasi dengan tepat ketika kode pintu ditemukan
- ✅ Return pesan sukses yang sesuai dengan kode
- ✅ Fallback ke clue ketika percobaan habis
- ✅ Menggunakan format string yang exact untuk pesan sukses

---

*Semoga berhasil memecahkan kodenya! 🔓*
