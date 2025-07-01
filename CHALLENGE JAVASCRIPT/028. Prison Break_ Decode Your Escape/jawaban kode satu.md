# 🔓 Dokumentasi Fungsi `prisonBreak`

## 📋 Deskripsi

Fungsi `prisonBreak` adalah sebuah algoritma dekripsi sederhana yang mengekstrak bagian tertentu dari pesan terenkripsi berdasarkan nomor sel penjara. Fungsi ini mengambil substring dari posisi tertentu dengan panjang yang sama dengan nomor sel, kemudian menggabungkannya dengan nomor sel untuk membentuk kode pelarian.

## 🎯 Cara Kerja

1. **Ekstraksi Substring**: Mengambil bagian dari pesan mulai dari indeks `cellNumber` dengan panjang sebesar `cellNumber`
2. **Pengecekan Overflow**: Jika nomor sel lebih besar dari panjang pesan, gunakan seluruh pesan
3. **Penggabungan**: Menggabungkan substring dengan nomor sel dalam bentuk string
4. **Output**: Mengembalikan kode pelarian sebagai string gabungan

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `encodedMessage` | `string` | Pesan terenkripsi yang akan didekripsi |
| `cellNumber` | `number` | Nomor sel penjara (digunakan sebagai indeks dan panjang ekstraksi) |

## 🔧 Kode Fungsi

```javascript
function prisonBreak(encodedMessage, cellNumber) {
  let substring = encodedMessage.substring(cellNumber, cellNumber + cellNumber);
  if (cellNumber > encodedMessage.length) {
    substring = encodedMessage;
  }
  const escapeCode = [substring, cellNumber.toString()].join('');
  return escapeCode;
}
```

## 💡 Contoh Penggunaan

### Contoh 1: Kasus Normal
```javascript
prisonBreak("ABCDEFGHIJK", 3);
// Output: "DEF3"
```

**Penjelasan:**
- Mulai dari indeks 3 (karakter 'D')
- Ambil 3 karakter: "DEF"
- Gabungkan dengan nomor sel "3"
- Hasil: "DEF3"

### Contoh 2: Nomor Sel Lebih Besar dari Panjang Pesan
```javascript
prisonBreak("HELLO", 10);
// Output: "HELLO10"
```

**Penjelasan:**
- Nomor sel (10) > panjang pesan (5)
- Substring diganti dengan seluruh pesan "HELLO"
- Gabungkan dengan nomor sel "10"
- Hasil: "HELLO10"

### Contoh 3: Nomor Sel di Tengah String
```javascript
prisonBreak("SECRETCODE", 4);
// Output: "ETCO4"
```

**Penjelasan:**
- Mulai dari indeks 4 (karakter 'E')
- Ambil 4 karakter: "ETCO"
- Gabungkan dengan nomor sel "4"
- Hasil: "ETCO4"

### Contoh 4: Nomor Sel Sama dengan Panjang Pesan
```javascript
prisonBreak("CODE", 4);
// Output: "CODE4"
```

**Penjelasan:**
- Nomor sel (4) = panjang pesan (4)
- Substring dari indeks 4 kosong, tetapi kondisi override aktif
- Gunakan seluruh pesan "CODE"
- Hasil: "CODE4"

## 📊 Tabel Karakter untuk Contoh

| Indeks | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|--------|---|---|---|---|---|---|---|---|---|---|
| Karakter | S | E | C | R | E | T | C | O | D | E |

**Untuk `prisonBreak("SECRETCODE", 4)`:**
- Mulai dari indeks 4 (E)
- Ambil 4 karakter: E, T, C, O
- Hasil substring: "ETCO"

## ⚠️ Catatan Penting

- **Perbedaan Utama**: Jika `cellNumber` lebih besar dari panjang pesan, fungsi akan menggunakan seluruh pesan sebagai substring
- **Override Logic**: Kondisi `cellNumber > encodedMessage.length` akan mengganti substring dengan pesan lengkap
- **Keamanan**: Fungsi menggunakan `substring()` yang aman dari index overflow
- **Output**: Selalu berupa string yang menggabungkan substring dan nomor sel

## 🔄 Perbandingan Logika

| Kondisi | Substring Yang Digunakan |
|---------|--------------------------|
| `cellNumber < encodedMessage.length` | Ekstraksi dari indeks cellNumber |
| `cellNumber = encodedMessage.length` | Seluruh pesan (override) |
| `cellNumber > encodedMessage.length` | Seluruh pesan (override) |

## 🎮 Skenario Penggunaan

Fungsi ini cocok digunakan untuk:
- 🔐 Sistem dekripsi dengan fallback
- 🎯 Game puzzle dengan mekanisme pengamanan
- 📱 Aplikasi yang membutuhkan ekstraksi data fleksibel
- 🔢 Algoritma encoding/decoding dengan error handling

## 🧪 Tips untuk Pemula

1. **Pahami Override**: Jika nomor sel terlalu besar, seluruh pesan akan digunakan
2. **Substring Safety**: `substring()` tidak akan error meski indeks melebihi batas
3. **Urutan Eksekusi**: Substring diekstrak dulu, baru dicek kondisi override
4. **Konversi Tipe**: Nomor sel selalu dikonversi ke string untuk penggabungan

## 🔍 Debugging Guide

Untuk memahami output yang tidak sesuai ekspektasi:

1. **Cek panjang pesan**: `encodedMessage.length`
2. **Bandingkan dengan cellNumber**: Apakah lebih besar?
3. **Trace substring**: Apa yang diekstrak sebelum override?
4. **Verifikasi join**: Apakah penggabungan sudah benar?
