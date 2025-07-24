# 🎓 Tantangan Academic Debate Winner

## 📊 Informasi Challenge
- **Level Kesulitan:** `Easy`
- **Tipe Challenge:** Implementasi Function
- **Topik:** String Manipulation & Array Processing

---

## 🎯 Overview Challenge

Buat sebuah function yang mensimulasikan debat akademis yang intens antara dua scholar dan menentukan pemenang berdasarkan kekuatan argumen mereka. Challenge ini menguji kemampuan Anda dalam membandingkan array, memproses string, dan mengimplementasikan logika scoring.

## 📝 Spesifikasi Function

### Nama Function
```javascript
debateWinner(scholar1Arguments, scholar2Arguments)
```

### 🔍 Deskripsi Problem

Function ini mensimulasikan **debat akademis yang heated** antara dua scholar dimana pemenang ditentukan dengan membandingkan kekuatan argumen mereka. Kekuatan setiap argumen diukur berdasarkan **panjang string**.

### ⚖️ Aturan Scoring

Debat mengikuti aturan spesifik berikut untuk menentukan poin:

1. **🏆 Perbandingan Head-to-Head**
   - Jika argumen Scholar 1 **lebih panjang** dari argumen Scholar 2 yang bersesuaian → Scholar 1 mendapat **1 poin**
   - Jika argumen Scholar 2 **lebih panjang** dari argumen Scholar 1 yang bersesuaian → Scholar 2 mendapat **1 poin**
   - Jika kedua argumen memiliki **panjang yang sama** → **Tidak ada poin** yang diberikan

2. **📊 Bonus Argumen Ekstra**
   - Jika seorang scholar memiliki **lebih banyak argumen** dari lawan mereka, mereka otomatis menang poin untuk setiap argumen ekstra

3. **🏅 Kondisi Kemenangan**
   - Scholar dengan **total skor tertinggi** memenangkan debat
   - Jika kedua scholar memiliki **skor yang sama** → Hasilnya seri

---

## 🔧 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `scholar1Arguments` | `Array<String>` | Array string yang merepresentasikan argumen scholar pertama |
| `scholar2Arguments` | `Array<String>` | Array string yang merepresentasikan argumen scholar kedua |

---

## 📤 Return Value

Function mengembalikan sebuah **string** yang menunjukkan hasil debat:

| Return Value | Kondisi |
|--------------|---------|
| `"Scholar 1 wins!"` | Ketika Scholar 1 memiliki lebih banyak poin |
| `"Scholar 2 wins!"` | Ketika Scholar 2 memiliki lebih banyak poin |
| `"It's a tie!"` | Ketika kedua scholar memiliki poin yang sama |

---

## 💡 Contoh Skenario

### Skenario 1: Pemenang yang Jelas
```javascript
scholar1Arguments = ["Argumen panjang di sini", "Pendek"]
scholar2Arguments = ["Singkat", "Argumen dengan panjang sedang"]
// Scholar 1: 24 vs 7 (1 poin), 6 vs 28 (0 poin) = 1 poin
// Scholar 2: 7 vs 24 (0 poin), 28 vs 6 (1 poin) = 1 poin
// Hasil: "It's a tie!"
```

### Skenario 2: Argumen Ekstra
```javascript
scholar1Arguments = ["Argumen", "Lainnya", "Yang ekstra"]
scholar2Arguments = ["Argumen", "Lainnya"]
// Sama untuk dua yang pertama, Scholar 1 mendapat 1 poin untuk argumen ekstra
// Hasil: "Scholar 1 wins!"
```

---

## 🎯 Poin Implementasi Kunci

- Bandingkan panjang argumen karakter demi karakter
- Handle array dengan panjang berbeda dengan tepat
- Implementasikan logika scoring yang benar untuk semua skenario
- Return format string pemenang yang benar

---

## 🚀 Siap untuk Coding?

Saatnya mengimplementasikan function `debateWinner` Anda dan menyelesaikan perselisihan akademis ini! Good luck! 🍀
