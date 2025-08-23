# 🔢 Dokumentasi Fungsi `decimalToBinary`

## 📋 Deskripsi Fungsi

Fungsi `decimalToBinary` adalah sebuah fungsi JavaScript yang mengkonversi angka desimal (basis 10) menjadi representasi biner (basis 2). Fungsi ini menggunakan pendekatan yang lebih ringkas dengan memanfaatkan operator logika OR (`||`) untuk menangani kasus angka 0, sehingga lebih efisien dan elegan dalam penulisan kode.

## 📝 Sintaks

```javascript
decimalToBinary(number)
```

## 🎯 Parameter

| Parameter | Tipe     | Deskripsi                                    | Wajib |
|-----------|----------|----------------------------------------------|-------|
| `number`  | `number` | Angka desimal yang akan dikonversi ke biner | ✅ Ya |

### ⚠️ Catatan Parameter:
- Parameter `number` harus berupa bilangan bulat non-negatif
- Jika input adalah 0, fungsi akan mengembalikan string "0"
- Fungsi tidak menangani bilangan negatif atau desimal

## ↩️ Return Value

**Tipe:** `string`

**Deskripsi:** String yang berisi representasi biner dari angka desimal input.

## 🔧 Source Code

```javascript
function decimalToBinary(number) {
  // Variabel untuk menyimpan hasil konversi biner
  let binary = '';
  
  // Loop selama angka masih lebih besar dari 0
  while (number > 0) {
    // Ambil sisa bagi dengan 2 dan tambahkan ke depan string binary
    binary = (number % 2) + binary;
    
    // Bagi angka dengan 2 dan bulatkan ke bawah
    number = Math.floor(number / 2);
  }
  
  // Kembalikan hasil konversi biner, atau '0' jika binary kosong
  return binary || '0';
}
```

## 🎮 Contoh Penggunaan

### Contoh 1: Angka Sederhana
```javascript
console.log(decimalToBinary(5));
// Output: "101"
```

### Contoh 2: Angka Nol
```javascript
console.log(decimalToBinary(0));
// Output: "0"
```

### Contoh 3: Angka Besar
```javascript
console.log(decimalToBinary(255));
// Output: "11111111"
```

### Contoh 4: Angka Kecil
```javascript
console.log(decimalToBinary(1));
// Output: "1"
```

## 📊 Tabel Contoh Konversi

| Desimal | Biner      | Penjelasan                           |
|---------|------------|--------------------------------------|
| 0       | 0          | Ditangani oleh operator `||`         |
| 1       | 1          | 1 = 1×2⁰                            |
| 2       | 10         | 2 = 1×2¹ + 0×2⁰                     |
| 3       | 11         | 3 = 1×2¹ + 1×2⁰                     |
| 4       | 100        | 4 = 1×2² + 0×2¹ + 0×2⁰              |
| 5       | 101        | 5 = 1×2² + 0×2¹ + 1×2⁰              |
| 8       | 1000       | 8 = 1×2³ + 0×2² + 0×2¹ + 0×2⁰       |
| 10      | 1010       | 10 = 1×2³ + 0×2² + 1×2¹ + 0×2⁰      |
| 16      | 10000      | 16 = 1×2⁴ + 0×2³ + 0×2² + 0×2¹ + 0×2⁰ |

## 🔍 Cara Kerja Algoritma

1. **Inisialisasi**: Buat variabel `binary` sebagai string kosong (`''`)
2. **Loop Konversi**: 
   - Ambil sisa bagi angka dengan 2 (`number % 2`)
   - Tambahkan hasil sisa ke depan string `binary`
   - Bagi angka dengan 2 dan bulatkan ke bawah
   - Ulangi sampai angka menjadi 0
3. **Return dengan Fallback**: Kembalikan `binary` atau `'0'` jika `binary` kosong (untuk kasus input 0)

## ✨ Keunggulan Pendekatan Ini

### 🎯 **Operator Logical OR (`||`)**
```javascript
return binary || '0';
```

**Penjelasan:**
- Jika `binary` adalah string kosong (`''`), maka dianggap "falsy" dalam JavaScript
- Operator `||` akan mengembalikan nilai di sebelah kanan (`'0'`) jika nilai kiri adalah falsy
- Ini lebih ringkas daripada menggunakan `if (number === 0)` di awal fungsi

### 📝 **Perbandingan dengan Pendekatan Lain:**

**Pendekatan dengan if statement:**
```javascript
if (number === 0) return "0";  // Pengecekan eksplisit
```

**Pendekatan dengan operator ||:**
```javascript
return binary || '0';  // Lebih ringkas dan elegan
```

## ⚡ Kompleksitas

- **Time Complexity**: O(log n) - dimana n adalah nilai input
- **Space Complexity**: O(log n) - untuk menyimpan string hasil

## 🚨 Limitasi

- Hanya menerima bilangan bulat non-negatif
- Tidak menangani bilangan desimal/float
- Tidak menangani bilangan negatif
- Tidak ada validasi input

## 🎓 Tips untuk Pemula

### 💡 **Mengapa `binary = (number % 2) + binary`?**
Karena kita membangun representasi biner dari kanan ke kiri, tetapi membacanya dari kiri ke kanan. Dengan menambahkan digit baru di depan string, urutan bit tetap benar.

### 📝 **Step-by-step untuk angka 5:**
```
Input: 5
1. 5 % 2 = 1, binary = "1", number = Math.floor(5/2) = 2
2. 2 % 2 = 0, binary = "0" + "1" = "01", number = Math.floor(2/2) = 1  
3. 1 % 2 = 1, binary = "1" + "01" = "101", number = Math.floor(1/2) = 0
4. Loop berhenti (number = 0)
5. return "101" || "0" = "101"
```

### 🔍 **Step-by-step untuk angka 0:**
```
Input: 0
1. Loop tidak dijalankan karena 0 > 0 adalah false
2. binary tetap ""
3. return "" || "0" = "0"
```

## 🎯 Konsep JavaScript yang Dipelajari

| Konsep | Penjelasan | Contoh dalam Fungsi |
|--------|------------|-------------------|
| **Truthy/Falsy** | String kosong (`''`) adalah falsy | `binary \|\| '0'` |
| **Operator Modulus** | Sisa bagi untuk mendapatkan digit biner | `number % 2` |
| **Math.floor()** | Pembulatan ke bawah | `Math.floor(number / 2)` |
| **String Concatenation** | Penggabungan string | `(number % 2) + binary` |
| **Logical OR** | Memberikan nilai default | `binary \|\| '0'` |

## 🔗 Fungsi Terkait

Anda mungkin juga tertarik dengan:
- `binaryToDecimal()` - Konversi biner ke desimal
- `parseInt(string, 2)` - Built-in JavaScript untuk parsing biner
- `number.toString(2)` - Built-in JavaScript untuk konversi ke biner

## 🧪 Testing

```javascript
// Test cases untuk fungsi
const testCases = [
  { input: 0, expected: "0" },
  { input: 1, expected: "1" },
  { input: 5, expected: "101" },
  { input: 8, expected: "1000" },
  { input: 255, expected: "11111111" }
];

testCases.forEach(test => {
  const result = decimalToBinary(test.input);
  console.log(`Input: ${test.input}, Expected: ${test.expected}, Got: ${result}`);
});
```
