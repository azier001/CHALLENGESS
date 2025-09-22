# 🏝️ Dokumentasi Fungsi `decodeIslandMap`

## 📋 Deskripsi

Fungsi `decodeIslandMap` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung jumlah pulau yang terdapat dalam sebuah peta yang dikodekan dalam bentuk string. Fungsi ini bekerja dengan cara menghitung berapa banyak karakter '1' yang ada dalam string peta, dimana setiap karakter '1' merepresentasikan satu pulau.

## 🔧 Sintaks

```javascript
function decodeIslandMap(encodedMap) {
    // Memisahkan string berdasarkan karakter '1' dan menghitung jumlah pulau
    return encodedMap.split('1').length - 1;
}
```

## 📥 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `encodedMap` | `string` | ✅ | String yang berisi peta terkodekan dengan karakter '0' dan '1', dimana '1' merepresentasikan pulau dan '0' merepresentasikan air/laut |

## 📊 Tabel Karakter

| Karakter | Makna | Contoh |
|----------|--------|---------|
| `'1'` | 🏝️ Pulau | Daratan/tanah |
| `'0'` | 🌊 Air/Laut | Perairan |

## 🔄 Return Value

- **Tipe**: `number`
- **Deskripsi**: Mengembalikan jumlah total pulau (karakter '1') yang ditemukan dalam peta

## 📝 Cara Kerja

1. Fungsi menerima parameter `encodedMap` berupa string
2. Menggunakan method `split('1')` untuk memisahkan string berdasarkan karakter '1'
3. Menghitung panjang array hasil split dikurangi 1 untuk mendapatkan jumlah karakter '1'
4. Mengembalikan hasil perhitungan sebagai jumlah pulau

## 💡 Contoh Penggunaan

### Contoh 1: Peta Sederhana
```javascript
const peta1 = "001100";
const jumlahPulau1 = decodeIslandMap(peta1);
console.log(jumlahPulau1); 
// Output: 2
// Penjelasan: Ada 2 karakter '1' dalam string "001100"
```

### Contoh 2: Peta Tanpa Pulau
```javascript
const peta2 = "000000";
const jumlahPulau2 = decodeIslandMap(peta2);
console.log(jumlahPulau2);
// Output: 0
// Penjelasan: Tidak ada karakter '1' dalam string "000000"
```

### Contoh 3: Peta dengan Banyak Pulau
```javascript
const peta3 = "1010101";
const jumlahPulau3 = decodeIslandMap(peta3);
console.log(jumlahPulau3);
// Output: 4
// Penjelasan: Ada 4 karakter '1' dalam string "1010101"
```

### Contoh 4: Peta Semua Pulau
```javascript
const peta4 = "111111";
const jumlahPulau4 = decodeIslandMap(peta4);
console.log(jumlahPulau4);
// Output: 6
// Penjelasan: Ada 6 karakter '1' dalam string "111111"
```

## 🎯 Contoh Output Detail

| Input String | Visualisasi | Jumlah Pulau | Output |
|--------------|-------------|--------------|---------|
| `"001100"` | `🌊🌊🏝️🏝️🌊🌊` | 2 | `2` |
| `"101010"` | `🏝️🌊🏝️🌊🏝️🌊` | 3 | `3` |
| `"000000"` | `🌊🌊🌊🌊🌊🌊` | 0 | `0` |
| `"111111"` | `🏝️🏝️🏝️🏝️🏝️🏝️` | 6 | `6` |

## ⚠️ Catatan Penting

1. **Input harus berupa string**: Fungsi ini dirancang khusus untuk menerima input bertipe string
2. **Hanya menghitung karakter '1'**: Karakter selain '0' dan '1' tidak akan mempengaruhi hasil perhitungan secara langsung
3. **Tidak ada validasi input**: Fungsi tidak melakukan pengecekan apakah input valid atau tidak

## 🧮 Penjelasan Algoritma

Algoritma yang digunakan sangat sederhana:
- `split('1')` akan memecah string menjadi array berdasarkan pemisah '1'
- Jika ada n buah karakter '1', maka `split('1')` akan menghasilkan array dengan (n+1) elemen
- Oleh karena itu, untuk mendapatkan jumlah karakter '1', kita perlu mengurangi panjang array dengan 1

**Contoh detail:**
```javascript
"001100".split('1') // Hasil: ["00", "", "00"]
// Array memiliki 3 elemen, berarti ada 2 karakter '1'
// Jadi: 3 - 1 = 2 pulau
```

## 🔗 Kode Sumber

```javascript
function decodeIslandMap(encodedMap) {
    // Memisahkan string berdasarkan karakter '1' dan menghitung jumlah pulau
    return encodedMap.split('1').length - 1;
}
```
