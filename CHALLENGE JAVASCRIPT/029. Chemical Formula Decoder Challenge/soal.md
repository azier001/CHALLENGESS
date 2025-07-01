# Challenge Decoder Formula Kimia

## 🧪 Gambaran Masalah

**Tingkat Kesulitan:** Easy

Di laboratorium yang remang-remang, seorang ilmuwan mencoba mendekode formula kimia misterius. Tugas Anda adalah membantu ilmuwan tersebut dengan membuat function yang dapat mendekode formula-formula tersebut.

## 📋 Deskripsi Tugas

Buat sebuah function bernama `decodeChemicalFormula` yang menerima `codedFormula` sebagai parameternya.

### Function Signature
```javascript
function decodeChemicalFormula(codedFormula) {
    // Implementasi Anda di sini
}
```

## 🔬 Aturan Decoding

Function harus mendecode input string dengan menerapkan aturan transformasi berikut:

- **'a'** → **'H'** (Hydrogen)
- **'b'** → **'O'** (Oxygen)  
- **'c'** → **'C'** (Carbon)
- **'d'** → **'N'** (Nitrogen)
- **'e'** → **'Cl'** (Chlorine)
- **Huruf kecil lainnya** → **Ubah menjadi huruf besar**

## ⚗️ Langkah-langkah Pemrosesan

1. **Decode** input string menggunakan aturan di atas
2. **Hitung** kemunculan setiap elemen
3. **Tambahkan subscript** untuk elemen yang muncul lebih dari sekali

> **Catatan:** Jika suatu elemen muncul lebih dari sekali, tambahkan angka subscript setelahnya.

## 📥 Parameter

- **`codedFormula`** *(string)*: String yang merepresentasikan formula kimia yang dikodekan
  - Hanya akan berisi huruf kecil
  - Merepresentasikan formula misterius yang akan didecode

## 📤 Return Value

- **Returns:** String yang merepresentasikan formula kimia yang sudah didecode dengan simbol elemen dan subscript yang tepat

## 🎯 Contoh Skenario

### Alur Pemrosesan Input:
```
Input: "aabbc"
↓
Decode: "H" + "H" + "O" + "O" + "C"
↓
Count: H(2), O(2), C(1)
↓
Output: "H2O2C"
```

### Contoh Lain:
```
Input: "abcde" 
↓
Decode: "H" + "O" + "C" + "N" + "Cl"
↓
Count: Semua muncul sekali
↓
Output: "HOCNCl"
```

## 🧬 Referensi Elemen Kimia

| Code | Element | Symbol | Nama |
|------|---------|--------|------|
| a | H | Hydrogen | Elemen paling melimpah |
| b | O | Oxygen | Penting untuk kehidupan |
| c | C | Carbon | Dasar kimia organik |
| d | N | Nitrogen | 78% dari atmosfer |
| e | Cl | Chlorine | Elemen halogen |

---

*Semoga berhasil membantu ilmuwan mendecode formula-formula misterius tersebut! 🔬✨*
