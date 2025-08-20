# 🍵 Tantangan Tea Cup Array Reversal

## 📋 Ringkasan Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function yang membalik urutan tea cup dalam array, karena terkadang cangkir terakhir yang diseduh harus menjadi yang pertama disajikan! ☕

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `reverseTeaCupArray` yang menerima array berisi jenis-jenis teh dan mengembalikannya dalam urutan terbalik.

## 📝 Spesifikasi Function

### Nama Function
```javascript
reverseTeaCupArray
```

### Parameter
- **`teaCups`** *(array)*
  - Array berisi string
  - Setiap string merepresentasikan jenis teh
  - Contoh: `["Green Tea", "Earl Grey", "Chamomile", "Oolong"]`

### Return Value
- **Tipe:** Array
- **Deskripsi:** Array baru yang berisi tea cup yang sama tetapi dalam urutan terbalik
- **Contoh:** `["Oolong", "Chamomile", "Earl Grey", "Green Tea"]`

---

## 💡 Contoh Penggunaan

```javascript
// Input
const teaCups = ["Green Tea", "Earl Grey", "Chamomile", "Oolong"];

// Pemanggilan function
const reversedCups = reverseTeaCupArray(teaCups);

// Output
console.log(reversedCups);
// ["Oolong", "Chamomile", "Earl Grey", "Green Tea"]
```

---

## ✅ Ringkasan Requirements

- [ ] Function harus diberi nama `reverseTeaCupArray`
- [ ] Harus menerima satu parameter: `teaCups` (array)
- [ ] Harus return **array baru** (jangan memodifikasi array asli)
- [ ] Elemen array harus dalam urutan terbalik
- [ ] Handle array dengan panjang berapa pun (termasuk array kosong)

---

## 🔍 Edge Case yang Perlu Dipertimbangkan

| Kasus | Input | Output yang Diharapkan |
|-------|-------|------------------------|
| Array kosong | `[]` | `[]` |
| Satu elemen | `["Matcha"]` | `["Matcha"]` |
| Dua elemen | `["Black Tea", "White Tea"]` | `["White Tea", "Black Tea"]` |

---

## 🌟 Tips Challenge

> **Hint:** JavaScript menyediakan beberapa method bawaan untuk manipulasi array. Pertimbangkan method mana yang paling tepat untuk membalik array sambil menjaga array asli tetap utuh.

**Selamat coding! 🚀**
