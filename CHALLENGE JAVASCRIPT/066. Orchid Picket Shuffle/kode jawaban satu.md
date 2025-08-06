# 🌺 Dokumentasi Fungsi `orchidPicketShuffle`

## 📋 Deskripsi Fungsi

Fungsi `orchidPicketShuffle` adalah sebuah fungsi JavaScript yang melakukan transformasi angka dengan cara:
1. **Membalik urutan digit** - Angka dibalik dari kanan ke kiri
2. **Menambah 1 pada setiap digit** - Setiap digit ditambah 1 (digit 9 akan menjadi 0)

Fungsi ini berguna untuk enkripsi sederhana atau transformasi data angka dengan pola tertentu.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `picketNumber` | `number` | Angka yang akan ditransformasi | `123`, `456`, `789` |

---

## 📤 Return Value

**Tipe:** `number`

**Deskripsi:** Angka hasil transformasi setelah dibalik dan setiap digitnya ditambah 1.

---

## 💻 Source Code

```javascript
function orchidPicketShuffle(picketNumber) {
  // Konversi angka menjadi string untuk mengakses digit individual
  const picketString = picketNumber.toString();
  
  // Balik urutan digit dari kanan ke kiri
  const reversedString = picketString.split('').reverse().join('');
  
  // Tambah 1 pada setiap digit (9 akan menjadi 0) dan gabung kembali
  const incrementedString = reversedString
    .split('')
    .map(digit => (parseInt(digit) + 1) % 10)
    .join('');
  
  // Konversi kembali ke integer dan return hasil
  return parseInt(incrementedString);
}
```

---

## 🎯 Cara Kerja Fungsi

### Langkah 1: Konversi ke String
```javascript
// Input: 123
const picketString = "123"
```

### Langkah 2: Balik Urutan Digit
```javascript
// "123" → ["1", "2", "3"] → ["3", "2", "1"] → "321"
const reversedString = "321"
```

### Langkah 3: Tambah 1 pada Setiap Digit
```javascript
// "321" → split → ["3", "2", "1"] → map → [4, 3, 2] → join → "432"
const incrementedString = "432"
```

### Langkah 4: Konversi ke Integer
```javascript
// Output: 432
return 432
```

---

## 📊 Tabel Transformasi Digit

| Digit Asli | Digit Setelah +1 |
|------------|------------------|
| 0 | 1 |
| 1 | 2 |
| 2 | 3 |
| 3 | 4 |
| 4 | 5 |
| 5 | 6 |
| 6 | 7 |
| 7 | 8 |
| 8 | 9 |
| 9 | 0 |

---

## 🚀 Contoh Penggunaan

```javascript
// Contoh 1: Angka 3 digit
console.log(orchidPicketShuffle(123));
// Output: 432

// Contoh 2: Angka dengan digit 9
console.log(orchidPicketShuffle(789));
// Output: 980

// Contoh 3: Angka 1 digit
console.log(orchidPicketShuffle(5));
// Output: 6

// Contoh 4: Angka dengan angka 0
console.log(orchidPicketShuffle(102));
// Output: 312

// Contoh 5: Angka dengan digit 9 di akhir
console.log(orchidPicketShuffle(999));
// Output: 0
```

---

## 📈 Contoh Output Detail

| Input | Langkah 1 (String) | Langkah 2 (Reverse) | Langkah 3 (+1 per digit) | Output |
|-------|-------------------|---------------------|---------------------------|--------|
| `123` | `"123"` | `"321"` | `"432"` | `432` |
| `789` | `"789"` | `"987"` | `"098"` | `98` |
| `456` | `"456"` | `"654"` | `"765"` | `765` |
| `999` | `"999"` | `"999"` | `"000"` | `0` |
| `102` | `"102"` | `"201"` | `"312"` | `312` |
| `505` | `"505"` | `"505"` | `"616"` | `616` |

---

## 🔍 Analisis Kode

### Keunggulan Implementasi

1. **Menggunakan `const`** - Praktik terbaik untuk variabel yang tidak berubah
2. **Method chaining** - Kode lebih ringkas dan mudah dibaca
3. **Functional programming approach** - Menggunakan `map()` untuk transformasi
4. **Clean code** - Nama variabel yang deskriptif dan mudah dipahami

### Breakdown Method Chaining

```javascript
// Method chaining pada langkah 3
reversedString
  .split('')        // "321" → ["3", "2", "1"]
  .map(digit =>     // Transform setiap element
    (parseInt(digit) + 1) % 10  // 3→4, 2→3, 1→2
  )                 // → [4, 3, 2]
  .join('');        // → "432"
```

---

## ⚠️ Catatan Penting

- **Digit 9** akan berubah menjadi **0** karena menggunakan modulo 10
- **Leading zero** pada hasil akan hilang karena konversi ke integer (contoh: "098" menjadi 98)
- Fungsi ini hanya bekerja dengan **bilangan bulat positif**
- **Angka negatif** akan menghasilkan hasil yang tidak terduga
- Fungsi menggunakan **immutable approach** - tidak mengubah input asli

---

## 🎨 Use Case

1. **Enkripsi sederhana** untuk data numerik
2. **Transformasi ID** atau kode referensi
3. **Game logic** untuk mengacak angka
4. **Obfuscation** sederhana untuk nomor urut
5. **Educational purpose** untuk memahami manipulasi string dan angka

---

## 🛠️ Tips Pengembangan

### Versi dengan Validasi Input

```javascript
function orchidPicketShuffleEnhanced(picketNumber) {
  // Validasi input
  if (!Number.isInteger(picketNumber) || picketNumber < 0) {
    throw new Error('Input harus berupa bilangan bulat positif');
  }
  
  // Proses transformasi
  const picketString = picketNumber.toString();
  const reversedString = picketString.split('').reverse().join('');
  const incrementedString = reversedString
    .split('')
    .map(digit => (parseInt(digit) + 1) % 10)
    .join('');
  
  return parseInt(incrementedString);
}
```

### Versi dengan Preservasi Leading Zero

```javascript
function orchidPicketShuffleWithLeadingZero(picketNumber, preserveLength = false) {
  const originalLength = picketNumber.toString().length;
  const result = orchidPicketShuffle(picketNumber);
  
  if (preserveLength) {
    return result.toString().padStart(originalLength, '0');
  }
  
  return result;
}
```

---

## 🧪 Testing Examples

```javascript
// Test berbagai skenario
const testCases = [
  { input: 123, expected: 432 },
  { input: 999, expected: 0 },
  { input: 1, expected: 2 },
  { input: 1000, expected: 1111 },
  { input: 505, expected: 616 }
];

testCases.forEach(test => {
  const result = orchidPicketShuffle(test.input);
  console.log(`Input: ${test.input}, Expected: ${test.expected}, Got: ${result}`);
});
```
