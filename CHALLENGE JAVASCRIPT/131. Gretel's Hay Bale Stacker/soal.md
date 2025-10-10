# 🌾 Gretel's Hay Bale Stacker

## Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

---

## 📖 Cerita

Gretel, seorang gadis petani, sedang menumpuk hay bales (bal jerami) di lumbungnya yang rustic. Tugasmu adalah membantunya mengorganisir hay bales tersebut menjadi daftar yang rapi dan dipisahkan dengan koma.

---

## 🎯 Tujuan

Buat sebuah function bernama **`stackHayBales`** yang menambahkan hay bale baru ke dalam stack saat ini dan mengembalikan representasi string yang terformat dengan baik dari semua hay bales.

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
stackHayBales(currentStack, newBale)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `currentStack` | `array` | Sebuah array berisi strings yang merepresentasikan stack hay bales saat ini |
| `newBale` | `string` | Sebuah string yang merepresentasikan hay bale baru yang akan ditambahkan ke stack |

### Return Value

- **Type:** `string`
- **Format:** Semua hay bales dalam stack, dipisahkan dengan koma, dan kata "and" sebelum hay bale terakhir

---

## 📋 Requirements

1. Tambahkan `newBale` ke akhir dari `currentStack`
2. Format output sebagai single string dengan:
   - Koma memisahkan hay bales
   - Kata "and" sebelum hay bale terakhir
3. Return string yang telah diformat

---

## 💡 Contoh Format

Jika stack berisi `["Bale A", "Bale B", "Bale C"]`, maka output harus berupa:

```
Bale A, Bale B, and Bale C
```

---

## ✨ Tips

- Pikirkan tentang edge cases: Bagaimana jika hanya ada satu bale? Dua bales?
- Pertimbangkan bagaimana cara menggabungkan elemen array dengan punctuation yang benar
- Ingat untuk menambahkan bale baru sebelum memformat output

---

**Selamat Coding! 🚜**
