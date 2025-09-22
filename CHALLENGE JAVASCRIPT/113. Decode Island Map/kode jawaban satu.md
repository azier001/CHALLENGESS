# 🏴‍☠️ Dokumentasi Fungsi `decodeIslandMap`

## 📋 Deskripsi

Fungsi `decodeIslandMap` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung jumlah harta karun yang terdapat dalam sebuah peta yang dikodekan dalam bentuk string. Fungsi ini bekerja dengan cara mengiterasi setiap karakter dalam string peta dan menghitung berapa banyak karakter '1' yang ditemukan, dimana setiap karakter '1' merepresentasikan lokasi harta karun.

## 🔧 Sintaks

```javascript
function decodeIslandMap(encodedMap) {
  // Inisialisasi counter untuk menghitung jumlah harta karun
  let treasureCount = 0;
  
  // Iterasi setiap karakter dalam peta terkodekan
  for (let i = 0; i < encodedMap.length; i++) {
    // Jika karakter adalah '1', tambahkan ke counter harta karun
    if (encodedMap[i] === '1') {
      treasureCount++;
    }
  }
  
  // Kembalikan total jumlah harta karun yang ditemukan
  return treasureCount;
}
```

## 📥 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `encodedMap` | `string` | ✅ | String yang berisi peta terkodekan dengan karakter '0' dan '1', dimana '1' merepresentasikan lokasi harta karun dan '0' merepresentasikan area kosong |

## 📊 Tabel Karakter

| Karakter | Makna | Simbol Visual | Contoh |
|----------|--------|---------------|---------|
| `'1'` | 💰 Harta Karun | 🏆 | Lokasi dengan harta |
| `'0'` | 🏝️ Area Kosong | ⬜ | Tanah kosong/laut |

## 🔄 Return Value

- **Tipe**: `number`
- **Deskripsi**: Mengembalikan jumlah total harta karun (karakter '1') yang ditemukan dalam peta
- **Range**: `0` hingga `encodedMap.length`

## 📝 Cara Kerja

1. **Inisialisasi**: Membuat variabel `treasureCount` dengan nilai 0 untuk menghitung harta karun
2. **Iterasi**: Menggunakan loop `for` untuk memeriksa setiap karakter dalam string `encodedMap`
3. **Pengecekan**: Pada setiap iterasi, memeriksa apakah karakter saat ini adalah '1'
4. **Penghitungan**: Jika karakter adalah '1', menambahkan 1 ke `treasureCount`
5. **Return**: Setelah loop selesai, mengembalikan total jumlah harta karun

## 💡 Contoh Penggunaan

### Contoh 1: Peta dengan Beberapa Harta Karun
```javascript
const peta1 = "001100";
const jumlahHarta1 = decodeIslandMap(peta1);
console.log(jumlahHarta1); 
// Output: 2
// Penjelasan: Ada 2 harta karun (karakter '1') di posisi index 2 dan 3
```

### Contoh 2: Peta Tanpa Harta Karun
```javascript
const peta2 = "000000";
const jumlahHarta2 = decodeIslandMap(peta2);
console.log(jumlahHarta2);
// Output: 0
// Penjelasan: Tidak ada harta karun (tidak ada karakter '1')
```

### Contoh 3: Peta dengan Pola Berselang-seling
```javascript
const peta3 = "1010101";
const jumlahHarta3 = decodeIslandMap(peta3);
console.log(jumlahHarta3);
// Output: 4
// Penjelasan: Ada 4 harta karun di posisi index 0, 2, 4, dan 6
```

### Contoh 4: Peta Penuh Harta Karun
```javascript
const peta4 = "111111";
const jumlahHarta4 = decodeIslandMap(peta4);
console.log(jumlahHarta4);
// Output: 6
// Penjelasan: Semua posisi berisi harta karun
```

### Contoh 5: Peta Panjang dengan Berbagai Pola
```javascript
const peta5 = "11100011101";
const jumlahHarta5 = decodeIslandMap(peta5);
console.log(jumlahHarta5);
// Output: 7
// Penjelasan: Ada 7 harta karun tersebar dalam peta
```

## 🎯 Contoh Output Detail dengan Visualisasi

| Input String | Visualisasi | Posisi Harta | Jumlah | Output |
|--------------|-------------|--------------|---------|---------|
| `"001100"` | `⬜⬜💰💰⬜⬜` | [2, 3] | 2 | `2` |
| `"101010"` | `💰⬜💰⬜💰⬜` | [0, 2, 4] | 3 | `3` |
| `"000000"` | `⬜⬜⬜⬜⬜⬜` | [] | 0 | `0` |
| `"111111"` | `💰💰💰💰💰💰` | [0,1,2,3,4,5] | 6 | `6` |
| `"11001100"` | `💰💰⬜⬜💰💰⬜⬜` | [0,1,4,5] | 4 | `4` |

## 🧮 Analisis Kompleksitas

| Aspek | Nilai | Penjelasan |
|-------|-------|------------|
| **Time Complexity** | `O(n)` | Dimana n adalah panjang string `encodedMap` |
| **Space Complexity** | `O(1)` | Hanya menggunakan variabel counter tambahan |
| **Best Case** | `O(n)` | Tetap harus memeriksa semua karakter |
| **Worst Case** | `O(n)` | Tetap harus memeriksa semua karakter |

## 🔍 Penjelasan Algoritma Step-by-Step

```javascript
// Contoh dengan input "101"
let encodedMap = "101";
let treasureCount = 0; // Step 1: Inisialisasi counter

// Step 2: Loop dimulai
// i = 0: encodedMap[0] = '1' → treasureCount = 1
// i = 1: encodedMap[1] = '0' → treasureCount tetap 1  
// i = 2: encodedMap[2] = '1' → treasureCount = 2

// Step 3: Return treasureCount = 2
```

## ⚡ Keunggulan Pendekatan Ini

1. **Mudah Dipahami**: Algoritma sederhana dengan logika yang straightforward
2. **Efisien**: Kompleksitas waktu linear O(n) yang optimal untuk masalah ini
3. **Memory Efficient**: Hanya menggunakan satu variabel tambahan
4. **Readable**: Kode mudah dibaca dan di-maintain
5. **Robust**: Bekerja untuk semua ukuran input string

## ⚠️ Catatan Penting

1. **Input Validation**: Fungsi tidak melakukan validasi input - pastikan `encodedMap` adalah string valid
2. **Karakter Selain '0' dan '1'**: Karakter lain akan diabaikan (tidak dihitung sebagai harta)
3. **Empty String**: Jika input adalah string kosong `""`, fungsi akan mengembalikan `0`
4. **Case Sensitive**: Fungsi hanya mengenali karakter '1' (bukan '1' dalam bentuk lain)

## 🔗 Kode Sumber Lengkap

```javascript
function decodeIslandMap(encodedMap) {
  // Inisialisasi counter untuk menghitung jumlah harta karun
  let treasureCount = 0;
  
  // Iterasi setiap karakter dalam peta terkodekan
  for (let i = 0; i < encodedMap.length; i++) {
    // Jika karakter adalah '1', tambahkan ke counter harta karun
    if (encodedMap[i] === '1') {
      treasureCount++;
    }
  }
  
  // Kembalikan total jumlah harta karun yang ditemukan
  return treasureCount;
}
```

## 🧪 Test Cases

```javascript
// Test case 1: Normal case
console.assert(decodeIslandMap("101010") === 3, "Test 1 failed");

// Test case 2: All zeros
console.assert(decodeIslandMap("000000") === 0, "Test 2 failed");

// Test case 3: All ones  
console.assert(decodeIslandMap("111111") === 6, "Test 3 failed");

// Test case 4: Empty string
console.assert(decodeIslandMap("") === 0, "Test 4 failed");

// Test case 5: Single character
console.assert(decodeIslandMap("1") === 1, "Test 5 failed");
console.assert(decodeIslandMap("0") === 0, "Test 6 failed");

console.log("✅ Semua test berhasil!");
```
