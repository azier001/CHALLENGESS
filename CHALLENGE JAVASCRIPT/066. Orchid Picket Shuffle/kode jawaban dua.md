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
    let numStr = picketNumber.toString();
    
    // Balik urutan digit dari kanan ke kiri
    let reversedStr = numStr.split('').reverse().join('');
    
    // Tambah 1 pada setiap digit (9 akan menjadi 0)
    let modifiedStr = reversedStr.split('').map(digit => {
        let num = parseInt(digit);
        return ((num + 1) % 10).toString();
    }).join('');
    
    // Konversi kembali ke integer dan return hasil
    return parseInt(modifiedStr);
}
```

---

## 🎯 Cara Kerja Fungsi

### Langkah 1: Konversi ke String
```javascript
// Input: 123
let numStr = "123"
```

### Langkah 2: Balik Urutan Digit
```javascript
// "123" → ["1", "2", "3"] → ["3", "2", "1"] → "321"
let reversedStr = "321"
```

### Langkah 3: Tambah 1 pada Setiap Digit
```javascript
// "321" → "3" menjadi "4", "2" menjadi "3", "1" menjadi "2"
// Hasil: "432"
let modifiedStr = "432"
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

---

## ⚠️ Catatan Penting

- **Digit 9** akan berubah menjadi **0** karena menggunakan modulo 10
- **Leading zero** pada hasil akan hilang karena konversi ke integer (contoh: "098" menjadi 98)
- Fungsi ini hanya bekerja dengan **bilangan bulat positif**
- **Angka negatif** akan menghasilkan hasil yang tidak terduga

---

## 🎨 Use Case

1. **Enkripsi sederhana** untuk data numerik
2. **Transformasi ID** atau kode referensi
3. **Game logic** untuk mengacak angka
4. **Educational purpose** untuk memahami manipulasi string dan angka

---

## 🛠️ Tips Pengembangan

Jika ingin menangani edge cases lebih baik, bisa menambahkan validasi:

```javascript
function orchidPicketShuffleEnhanced(picketNumber) {
    // Validasi input
    if (!Number.isInteger(picketNumber) || picketNumber < 0) {
        throw new Error('Input harus berupa bilangan bulat positif');
    }
    
    // Proses yang sama seperti fungsi asli
    let numStr = picketNumber.toString();
    let reversedStr = numStr.split('').reverse().join('');
    let modifiedStr = reversedStr.split('').map(digit => {
        let num = parseInt(digit);
        return ((num + 1) % 10).toString();
    }).join('');
    
    return parseInt(modifiedStr);
}
```
