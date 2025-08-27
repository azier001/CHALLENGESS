# 💎 Count Tiffany Bracelets

## 🏷️ Informasi Challenge
- **Level Kesulitan:** `Easy`
- **Tipe Challenge:** Binary Manipulation
- **Skills:** Konversi angka, Operasi binary, Loops

---

## 📋 Deskripsi Problem

Buatlah sebuah function bernama `countTiffanyBracelets` yang memproses jumlah bracelet di toko perhiasan menggunakan representasi binary.

### 🎯 Objective
Tugas Anda adalah menghitung jumlah digit `1` dalam representasi binary dari angka yang diberikan.

---

## ⚙️ Requirement Function

### Function Signature
```javascript
function countTiffanyBracelets(num)
```

### Parameter
- **`num`** *(number)*: Merepresentasikan jumlah bracelet di toko

### Alur Process
Function harus mengikuti langkah-langkah berikut:

1. **🔄 Convert** angka input ke representasi binary
2. **🔢 Initialize** variabel counter ke `0`
3. **🔍 Loop** melalui setiap digit dalam string binary
4. **➕ Increment** counter sebesar `1` jika digit saat ini adalah `'1'`
5. **📤 Return** nilai counter akhir

---

## 💡 Breakdown Algorithm

```
Input: num (integer)
│
├─ Step 1: Convert num ke binary string
├─ Step 2: counter = 0
├─ Step 3: Untuk setiap digit dalam binary string:
│           │
│           └─ Jika digit == '1':
│               └─ counter++
│
└─ Step 4: Return counter
```

---

## 🧮 Contoh Walkthrough

Mari kita trace melalui contoh:

**Input:** `num = 13`

1. **Konversi binary:** `13` → `"1101"`
2. **Initialize counter:** `counter = 0`
3. **Loop melalui digit:**
   - `'1'` → counter menjadi `1`
   - `'1'` → counter menjadi `2`  
   - `'0'` → counter tetap `2`
   - `'1'` → counter menjadi `3`
4. **Result:** `3`

---

## 📊 Test Cases

| Input | Binary | Expected Output | Description |
|-------|--------|----------------|-------------|
| `0`   | `"0"`  | `0`            | Tidak ada bit yang set |
| `1`   | `"1"`  | `1`            | Single set bit |
| `7`   | `"111"`| `3`            | Semua bit set |
| `8`   | `"1000"`| `1`           | Power of 2 |
| `15`  | `"1111"`| `4`           | Semua bit dalam nibble |

---

## 🏆 Kriteria Success

- ✅ Function berhasil convert angka ke binary
- ✅ Menghitung digit '1' dengan benar
- ✅ Return count yang akurat
- ✅ Handle edge cases (0, powers of 2)
- ✅ Implementasi yang efisien

---

## 💭 Hints

> 🔍 **Hint 1:** Method `toString(2)` JavaScript dapat convert angka ke binary  
> 🔍 **Hint 2:** Anda bisa iterate melalui string seperti array  
> 🔍 **Hint 3:** Ingat untuk convert string digit ke angka saat membandingkan
