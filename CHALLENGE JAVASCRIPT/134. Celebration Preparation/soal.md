# 🎉 Celebration Preparation Challenge

**Tingkat Kesulitan:** Easy

---

## 📋 Gambaran Umum Challenge

Buat sebuah function bernama `celebrationPrep` yang menerima `binaryNumbers` sebagai parameter-nya. Function ini mengorganisir dan mengurutkan sebuah guest list yang direpresentasikan oleh binary numbers.

---

## 🎯 Tujuan

Tugas Anda adalah:

1. **Konversi** setiap binary number di dalam array `binaryNumbers` ke decimal equivalent-nya
2. **Urutkan** decimal numbers yang telah dikonversi dalam urutan ascending
3. **Kembalikan** array terurut dari decimal numbers

---

## 📥 Parameter Function

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `binaryNumbers` | `array of strings` | Array dari binary numbers yang direpresentasikan sebagai strings |

**Contoh Input:**
```javascript
['1010', '11', '1000', '1111', '10']
```

---

## 📤 Return Value

**Type:** `array of integers`

Array dari integers yang merepresentasikan decimal equivalents terurut dari input binary numbers.

**Contoh Output:**
```javascript
[2, 8, 10, 15]
```

---

## 💡 Function Signature

```javascript
function celebrationPrep(binaryNumbers) {
  // Implementasi Anda di sini
}
```

---

## 📝 Langkah-Langkah Implementasi

**Langkah 1:** Konversi binary strings ke decimal
- Gunakan `parseInt(string, 2)` untuk mengkonversi setiap binary string ke decimal

**Langkah 2:** Urutkan decimal numbers
- Gunakan method `.sort()` dengan comparison function

**Langkah 3:** Kembalikan array terurut
- Return array hasil sorting dari integers

---

## ✅ Contoh Test Case

**Input:**
```javascript
celebrationPrep(['1010', '11', '1000', '1111', '10'])
```

**Expected Output:**
```javascript
[2, 8, 10, 15]
```

**Penjelasan:**
- `'10'` → 2
- `'11'` → 3
- `'1000'` → 8
- `'1010'` → 10
- `'1111'` → 15

Kemudian diurutkan dalam ascending order: `[2, 8, 10, 15]`

---

## 🚀 Tips untuk Kesuksesan

- Ingat bahwa binary adalah base-2, jadi setiap digit merepresentasikan power of 2
- Function `parseInt()` adalah best friend Anda untuk binary conversion
- Jangan lupa menggunakan comparison yang tepat dalam function sort
- Pertimbangkan edge cases seperti empty arrays atau single-element arrays
