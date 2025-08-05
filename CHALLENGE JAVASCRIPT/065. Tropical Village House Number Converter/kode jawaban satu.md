# 🏠 House Number Converter

## 📋 Deskripsi Fungsi

Fungsi `houseNumberConverter` adalah sebuah utility yang mengubah array angka desimal menjadi array string biner, kemudian membalik urutan elemen dalam array tersebut. Fungsi ini berguna untuk konversi sistem bilangan dan manipulasi urutan data.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `decimalNumbers` | `Array<number>` | Array berisi angka-angka desimal yang akan dikonversi |

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Array<string>` | Array berisi string biner dalam urutan terbalik |

## 💻 Source Code

```javascript
function houseNumberConverter(decimalNumbers) {
  // Konversi angka desimal ke string biner
  const binaryNumbers = decimalNumbers.map(num => num.toString(2));
  
  // Balik urutan array string biner
  const reversedBinaryNumbers = binaryNumbers.reverse();
  
  return reversedBinaryNumbers;
}
```

## 🎯 Cara Kerja

1. **Konversi Desimal ke Biner**: Setiap angka dalam array `decimalNumbers` dikonversi menjadi representasi biner menggunakan method `toString(2)`
2. **Pembalikan Urutan**: Array hasil konversi kemudian dibalik urutannya menggunakan method `reverse()`
3. **Return Hasil**: Mengembalikan array string biner yang sudah dalam urutan terbalik

## 📊 Contoh Penggunaan

### Contoh 1: Array Angka Sederhana
```javascript
const input = [1, 2, 3, 4, 5];
const result = houseNumberConverter(input);
console.log(result);
// Output: ["101", "100", "11", "10", "1"]
```

### Contoh 2: Array dengan Angka Lebih Besar
```javascript
const input = [10, 15, 8];
const result = houseNumberConverter(input);
console.log(result);
// Output: ["1000", "1111", "1010"]
```

### Contoh 3: Array dengan Satu Elemen
```javascript
const input = [7];
const result = houseNumberConverter(input);
console.log(result);
// Output: ["111"]
```

## 📈 Tabel Konversi Desimal ke Biner

| Desimal | Biner |
|---------|-------|
| 0 | 0 |
| 1 | 1 |
| 2 | 10 |
| 3 | 11 |
| 4 | 100 |
| 5 | 101 |
| 6 | 110 |
| 7 | 111 |
| 8 | 1000 |
| 9 | 1001 |
| 10 | 1010 |

## ⚠️ Catatan Penting

- Fungsi ini mengubah array asli karena menggunakan method `reverse()`
- Jika ingin mempertahankan array asli, gunakan spread operator: `[...binaryNumbers].reverse()`
- Input harus berupa array yang berisi angka (number)
- Hasil konversi berupa string, bukan number

## 🔄 Versi yang Tidak Mengubah Array Asli

```javascript
function houseNumberConverter(decimalNumbers) {
  // Konversi angka desimal ke string biner
  const binaryNumbers = decimalNumbers.map(num => num.toString(2));
  
  // Balik urutan array tanpa mengubah array asli
  const reversedBinaryNumbers = [...binaryNumbers].reverse();
  
  return reversedBinaryNumbers;
}
```

## 🎓 Tips untuk Pemula

- **Method `toString(2)`**: Mengkonversi number ke string dengan basis 2 (biner)
- **Method `map()`**: Membuat array baru dengan menerapkan fungsi ke setiap elemen
- **Method `reverse()`**: Membalik urutan elemen dalam array (mengubah array asli)
- **Spread Operator `[...]`**: Membuat salinan array untuk menghindari perubahan pada array asli
