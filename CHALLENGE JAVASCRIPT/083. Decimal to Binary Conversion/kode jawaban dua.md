# 🔢 Dokumentasi Fungsi `decimalToBinary`

## 📋 Deskripsi Fungsi

Fungsi `decimalToBinary` adalah sebuah fungsi JavaScript yang mengkonversi angka desimal (basis 10) menjadi representasi biner (basis 2). Fungsi ini sangat berguna untuk keperluan pembelajaran sistem bilangan, pemrograman tingkat rendah, atau aplikasi yang memerlukan manipulasi bit.

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
    // Jika angka adalah 0, langsung kembalikan "0"
    if (number === 0) return "0";
    
    // Variabel untuk menyimpan hasil konversi biner
    let binary = "";
    
    // Loop selama angka masih lebih besar dari 0
    while (number > 0) {
        // Ambil sisa bagi dengan 2 dan tambahkan ke depan string binary
        binary = (number % 2) + binary;
        
        // Bagi angka dengan 2 dan bulatkan ke bawah
        number = Math.floor(number / 2);
    }
    
    // Kembalikan hasil konversi biner
    return binary;
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

## 📊 Tabel Contoh Konversi

| Desimal | Biner      | Penjelasan                           |
|---------|------------|--------------------------------------|
| 0       | 0          | Kasus khusus                         |
| 1       | 1          | 1 = 1×2⁰                            |
| 2       | 10         | 2 = 1×2¹ + 0×2⁰                     |
| 3       | 11         | 3 = 1×2¹ + 1×2⁰                     |
| 4       | 100        | 4 = 1×2² + 0×2¹ + 0×2⁰              |
| 5       | 101        | 5 = 1×2² + 0×2¹ + 1×2⁰              |
| 8       | 1000       | 8 = 1×2³ + 0×2² + 0×2¹ + 0×2⁰       |
| 10      | 1010       | 10 = 1×2³ + 0×2² + 1×2¹ + 0×2⁰      |
| 16      | 10000      | 16 = 1×2⁴ + 0×2³ + 0×2² + 0×2¹ + 0×2⁰ |

## 🔍 Cara Kerja Algoritma

1. **Pengecekan Kasus Khusus**: Jika input adalah 0, langsung return "0"
2. **Inisialisasi**: Buat variabel `binary` sebagai string kosong
3. **Loop Konversi**: 
   - Ambil sisa bagi angka dengan 2 (`number % 2`)
   - Tambahkan hasil sisa ke depan string `binary`
   - Bagi angka dengan 2 dan bulatkan ke bawah
   - Ulangi sampai angka menjadi 0
4. **Return Hasil**: Kembalikan string biner yang sudah terbentuk

## ⚡ Kompleksitas

- **Time Complexity**: O(log n) - dimana n adalah nilai input
- **Space Complexity**: O(log n) - untuk menyimpan string hasil

## 🚨 Limitasi

- Hanya menerima bilangan bulat non-negatif
- Tidak menangani bilangan desimal/float
- Tidak menangani bilangan negatif
- Tidak ada validasi input

## 🎓 Tips untuk Pemula

**Mengapa menggunakan `(number % 2) + binary` bukan `binary + (number % 2)`?**

Karena dalam sistem biner, digit yang paling kanan adalah yang paling signifikan dalam urutan pembacaan kiri-ke-kanan. Dengan menambahkan digit baru di depan string, kita memastikan urutan bit yang benar.

**Contoh step-by-step untuk angka 5:**
1. 5 % 2 = 1, binary = "1", number = 2
2. 2 % 2 = 0, binary = "01", number = 1  
3. 1 % 2 = 1, binary = "101", number = 0
4. Loop berhenti, return "101"

## 🔗 Fungsi Terkait

Anda mungkin juga tertarik dengan:
- `binaryToDecimal()` - Konversi biner ke desimal
- `parseInt(string, 2)` - Built-in JavaScript untuk parsing biner
- `number.toString(2)` - Built-in JavaScript untuk konversi ke biner
