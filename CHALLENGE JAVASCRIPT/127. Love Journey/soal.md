# 💝 Love Journey

## Gambaran Umum Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang menghitung love score dengan memproses array memory book menggunakan operasi matematika tertentu.

---

## 📋 Spesifikasi Function

### Nama Function
```javascript
loveJourney(loveScore, memoryBook)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `loveScore` | Number | Nilai love score awal |
| `memoryBook` | Array<Number> | Array berisi angka-angka yang merepresentasikan memori |

### Return Value

- **Tipe:** Number
- **Deskripsi:** Love score akhir setelah memproses semua memori

---

## 🎯 Persyaratan Challenge

### Proses Step-by-Step

#### **Step 1: Slice Memory Book**
Ekstrak subset dari array `memoryBook`:
- **Mulai:** Elemen ke-2 (index `1`)
- **Akhir:** Elemen ke-2 dari belakang (index `length - 1`)

```javascript
// Contoh:
// memoryBook = [10, 20, 30, 40, 50]
// Hasil slice = [20, 30, 40]
```

#### **Step 2: Proses Setiap Memori**
Loop melalui sliced array dan update `loveScore`:

- ✅ **Jika elemen GENAP:** Tambahkan ke `loveScore`
  ```
  loveScore += element
  ```

- ❌ **Jika elemen GANJIL:** Kurangi dari `loveScore`
  ```
  loveScore -= element
  ```

#### **Step 3: Return Hasilnya**
Return nilai akhir `loveScore`

---

## 💡 Contoh Walkthrough

### Input
```javascript
loveScore = 100
memoryBook = [5, 10, 15, 20, 25, 30, 8]
```

### Proses

1. **Slice array:** `[10, 15, 20, 25, 30]`
   - Dari index 1 sampai index 5 (tidak termasuk elemen terakhir)

2. **Loop setiap elemen:**
   - `10` genap → `100 + 10 = 110`
   - `15` ganjil → `110 - 15 = 95`
   - `20` genap → `95 + 20 = 115`
   - `25` ganjil → `115 - 25 = 90`
   - `30` genap → `90 + 30 = 120`

3. **Return:** `120`

---

## 📝 Template Implementasi

```javascript
function loveJourney(loveScore, memoryBook) {
  // Kode Anda di sini
}
```

---

## ✅ Test Cases

```javascript
// Test Case 1
loveJourney(100, [5, 10, 15, 20, 25, 30, 8]);
// Expected output: 120

// Test Case 2
loveJourney(50, [1, 2, 3, 4, 5, 6, 7]);
// Expected output: 54

// Test Case 3
loveJourney(0, [10, 20, 30, 40, 50]);
// Expected output: 80
```

---

## 🎓 Konsep Penting

Challenge ini membantu Anda berlatih:

- 🔹 Manipulasi array dengan `slice()`
- 🔹 Logika kondisional (statement if/else)
- 🔹 Iterasi loop
- 🔹 Deteksi bilangan genap/ganjil
- 🔹 Pattern accumulator

---

## 💪 Semangat!

Ingat untuk test solusi Anda dengan berbagai input untuk memastikan dapat menangani semua kasus dengan benar!
