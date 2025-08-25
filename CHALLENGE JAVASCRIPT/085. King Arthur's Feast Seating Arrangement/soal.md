# 🏰 Pengaturan Tempat Duduk Pesta King Arthur

## 📋 Overview Challenge

**Tingkat Kesulitan:** `Easy`

Buat pengaturan tempat duduk ala medieval untuk pesta legendaris di meja bundar King Arthur! Challenge ini melibatkan pengorganisasian knights dan goblet wine dalam pola berselang-seling yang spesifik di sekitar meja.

---

## 🎯 Objektif

Rancang sebuah function yang membuat pengaturan tempat duduk di mana setiap posisi lainnya di meja bundar memiliki goblet wine, memastikan pola berselang-seling yang sempurna antara knights dan wine.

---

## 🛡️ Spesifikasi Function

### Nama Function
```javascript
feastArrangement(numKnights)
```

### Parameter
- **`numKnights`** *(number)*: Total jumlah knights yang menghadiri pesta King Arthur

### Return Value
- **Array of strings**: Merepresentasikan pengaturan tempat duduk lengkap
- Setiap elemen berupa:
  - `"knight"` - merepresentasikan seorang knight yang duduk
  - `"wine"` - merepresentasikan sebuah goblet wine

---

## 📐 Requirements

### Aturan Utama
1. **Pola Berselang-seling**: Tempat duduk harus berselang-seling antara knights dan goblet wine
2. **Posisi Awal**: Pengaturan harus dimulai dengan knight
3. **Logika Round Table**: Pertimbangkan sifat melingkar dari pengaturan tempat duduk

### Pola yang Diharapkan
```
Posisi 1: "knight"
Posisi 2: "wine" 
Posisi 3: "knight"
Posisi 4: "wine"
...dan seterusnya
```

---

## 💡 Contoh Skenario

### Perkumpulan Kecil (3 Knights)
```javascript
// Input: 3
// Expected Output: ["knight", "wine", "knight", "wine", "knight", "wine"]
```

### Perkumpulan Sedang (5 Knights)
```javascript
// Input: 5  
// Expected Output: ["knight", "wine", "knight", "wine", "knight", "wine", "knight", "wine", "knight", "wine"]
```

---

## 🤔 Pertimbangan Kunci

- **Panjang Array**: Total panjang akan menjadi `numKnights × 2` (setiap knight mendapat goblet wine)
- **Konsistensi Pola**: Pertahankan urutan berselang-seling sepanjang array
- **Edge Cases**: Pertimbangkan skenario dengan knights yang sangat sedikit (1-2)
- **Tema Medieval**: Jaga output string tetap sesuai spesifikasi: `"knight"` dan `"wine"`

---

## 🎭 Konteks Cerita

> *Di aula megah Camelot, King Arthur mengadakan pesta mewah di meja bundar legendaris miliknya. Untuk memastikan keramahan yang tepat, dia mewajibkan bahwa setiap knight harus memiliki goblet wine berkualitas yang ditempatkan di samping mereka. Tugas Anda adalah membantu royal steward mengatur tempat duduk untuk mempertahankan tradisi mulia ini!*

---

**Semoga berhasil, programmer yang mulia! Semoga code Anda selegendaris Excalibur! ⚔️**
