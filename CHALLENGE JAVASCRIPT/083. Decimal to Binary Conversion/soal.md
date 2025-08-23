# 🔢 Konversi Decimal ke Binary

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Buat sebuah function yang mengkonversi angka decimal ke representasi binary-nya. Latihan programming fundamental ini membantu Anda memahami konversi basis angka dan operasi bitwise.

---

## 🎯 Tujuan

Rancang sebuah function bernama `decimalToBinary` yang menerima integer positif dalam basis 10 dan mengembalikan ekuivalen binary-nya sebagai string.

---

## 📝 Spesifikasi Function

### Function Signature
```javascript
function decimalToBinary(number) {
    // Implementasi Anda di sini
}
```

### Parameter
- **`number`** *(integer)*: Integer positif dalam format decimal

### Return Value
- **Type:** `string`
- **Content:** Representasi binary dari input number

---

## 🔧 Requirements

✅ **Batasan Input:**
- Input `number` akan selalu berupa integer positif
- Tidak perlu menangani negative number atau zero

✅ **Format Output:**
- Return ekuivalen binary sebagai string
- Tidak perlu leading zeros (kecuali untuk angka 0 itu sendiri)

✅ **Pendekatan Algorithm:**
- Berulang kali bagi number dengan 2
- Catat remainder yang didapat
- Remainder dalam urutan terbalik membentuk ekuivalen binary

---

## 💡 Penjelasan Algorithm

### Proses Step-by-Step:

1. **Inisialisasi** container result kosong
2. **Bagi** number decimal dengan 2
3. **Catat** remainder (0 atau 1)
4. **Update** number menjadi quotient
5. **Ulangi** langkah 2-4 hingga number menjadi 0
6. **Balik** urutan remainder yang terkumpul untuk mendapat hasil binary

### Contoh Visual:
```
Konversi 13 ke binary:
13 ÷ 2 = 6 remainder 1
6 ÷ 2 = 3 remainder 0
3 ÷ 2 = 1 remainder 1
1 ÷ 2 = 0 remainder 1

Membaca remainder dari bawah ke atas: 1101
```

---

## 🧪 Test Cases

| Input | Expected Output | Deskripsi |
|-------|----------------|-----------|
| `1` | `"1"` | Integer positif terkecil |
| `2` | `"10"` | Power of 2 pertama |
| `8` | `"1000"` | Power of 2 |
| `13` | `"1101"` | Mixed binary digits |
| `255` | `"11111111"` | Maximum 8-bit |

---

## 🚀 Getting Started

Siap untuk mengimplementasikan solusi Anda? Ingat untuk:

- Handle operasi division dan remainder dengan benar
- Build string binary dalam urutan yang tepat
- Test dengan berbagai input values
- Pertimbangkan edge cases seperti powers of 2

**Good luck coding!** 🎉
