# 🧺 Fruit Basket Checker

## 📖 Deskripsi

Fungsi `fruitBasketChecker` adalah fungsi JavaScript yang digunakan untuk memeriksa apakah sebuah keranjang buah dapat dikategorikan sebagai "splendiferous" (luar biasa) atau tidak. Fungsi ini akan memvalidasi nama buah, memeriksa apakah buah tersebut termasuk buah yang berair (juicy), dan memastikan jumlah buah berada dalam rentang yang valid.

## ✨ Fitur

- ✅ Validasi nama buah (hanya huruf dan spasi)
- 🍊 Pengecekan apakah buah termasuk kategori berair (juicy)
- 🔢 Validasi jumlah buah (1-100)
- 💬 Memberikan pesan yang sesuai berdasarkan hasil pengecekan

## 📝 Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|--------|
| `fruitName` | String | Nama buah yang akan diperiksa. Harus berisi huruf dan spasi saja. | `"Apple"`, `"Orange"` |
| `quantity` | Number | Jumlah buah dalam keranjang. Harus antara 1-100. | `5`, `50` |

## 🍎 Daftar Buah Berair (Juicy Fruits)

| No | Nama Buah | Karakter |
|----|-----------|----------|
| 1 | Apple | 🍎 |
| 2 | Orange | 🍊 |
| 3 | Pear | 🍐 |
| 4 | Peach | 🍑 |
| 5 | Watermelon | 🍉 |

## ⚙️ Cara Kerja

Fungsi ini akan mengembalikan pesan **"Oh my, what a splendiferous fruit basket!"** jika **SEMUA** kondisi berikut terpenuhi:

1. ✅ Nama buah valid (hanya mengandung huruf dan spasi)
2. ✅ Buah termasuk dalam daftar buah berair
3. ✅ Jumlah buah antara 1-100

Jika salah satu kondisi **TIDAK** terpenuhi, fungsi akan mengembalikan pesan **"I'm afraid this fruit basket is not so splendiferous."**

## 💻 Source Code

```javascript
function fruitBasketChecker(fruitName, quantity) {
  
  // Langkah 1: Cek apakah nama buah valid menggunakan regular expression
  const isValidFruitName = /^[a-zA-Z ]+$/.test(fruitName);

  // Langkah 2: Konversi nama buah ke huruf kecil untuk memudahkan perbandingan
  const lowercaseFruitName = fruitName.toLowerCase();

  // Langkah 3: Cek apakah buah termasuk buah berair (juicy)
  const juicyFruits = ['apple', 'orange', 'pear', 'peach', 'watermelon'];
  const isJuicyFruit = juicyFruits.includes(lowercaseFruitName);

  // Langkah 4: Verifikasi apakah jumlah buah berada dalam rentang yang valid (1-100)
  const isValidQuantity = quantity >= 1 && quantity <= 100;

  // Langkah 5: Gabungkan semua kondisi menggunakan operator logika AND
  const isSplendiferous = isValidFruitName && isJuicyFruit && isValidQuantity;

  // Langkah 6: Kembalikan pesan yang sesuai berdasarkan hasil pengecekan
  return isSplendiferous
    ? "Oh my, what a splendiferous fruit basket!"
    : "I'm afraid this fruit basket is not so splendiferous.";
    
}
```

## 📊 Contoh Penggunaan

### ✅ Contoh 1: Keranjang Buah yang Splendiferous

```javascript
fruitBasketChecker("Apple", 10);
```

**Output:**
```
"Oh my, what a splendiferous fruit basket!"
```

**Penjelasan:** Nama buah valid, termasuk buah berair, dan jumlahnya dalam rentang 1-100.

---

### ✅ Contoh 2: Nama Buah dengan Huruf Kapital

```javascript
fruitBasketChecker("ORANGE", 25);
```

**Output:**
```
"Oh my, what a splendiferous fruit basket!"
```

**Penjelasan:** Nama buah valid dan akan dikonversi ke lowercase untuk pengecekan, termasuk buah berair, dan jumlahnya valid.

---

### ❌ Contoh 3: Jumlah Buah Tidak Valid (Melebihi Maksimal)

```javascript
fruitBasketChecker("Orange", 150);
```

**Output:**
```
"I'm afraid this fruit basket is not so splendiferous."
```

**Penjelasan:** Nama buah valid dan termasuk buah berair, tetapi jumlahnya melebihi batas maksimal (100).

---

### ❌ Contoh 4: Nama Buah Tidak Valid (Mengandung Angka)

```javascript
fruitBasketChecker("Apple123", 20);
```

**Output:**
```
"I'm afraid this fruit basket is not so splendiferous."
```

**Penjelasan:** Nama buah mengandung angka, sehingga tidak valid. Hanya huruf dan spasi yang diperbolehkan.

---

### ❌ Contoh 5: Buah Tidak Berair

```javascript
fruitBasketChecker("Banana", 30);
```

**Output:**
```
"I'm afraid this fruit basket is not so splendiferous."
```

**Penjelasan:** Nama buah valid dan jumlah valid, tetapi "banana" tidak termasuk dalam daftar buah berair.

---

### ❌ Contoh 6: Jumlah Buah Nol atau Negatif

```javascript
fruitBasketChecker("Peach", 0);
```

**Output:**
```
"I'm afraid this fruit basket is not so splendiferous."
```

**Penjelasan:** Jumlah buah harus minimal 1. Nilai 0 atau negatif tidak valid.

---

### ❌ Contoh 7: Nama Buah dengan Karakter Spesial

```javascript
fruitBasketChecker("Apple!", 15);
```

**Output:**
```
"I'm afraid this fruit basket is not so splendiferous."
```

**Penjelasan:** Nama buah mengandung karakter spesial (!), sehingga tidak lolos validasi.

## 🎯 Tips Penggunaan

- 💡 Nama buah **tidak case-sensitive** (besar kecil huruf tidak masalah)
- 💡 Pastikan nama buah ditulis dengan benar sesuai daftar (contoh: "watermelon" bukan "water melon")
- 💡 Jumlah buah harus berupa angka bulat antara 1-100
- 💡 Nama buah tidak boleh mengandung angka atau karakter spesial (!, @, #, dll)
- 💡 Spasi di antara kata dalam nama buah diperbolehkan

## 🔍 Validasi yang Dilakukan

| Validasi | Kondisi | Metode |
|----------|---------|--------|
| Nama Valid | Hanya huruf dan spasi | Regular Expression `/^[a-zA-Z ]+$/` |
| Buah Berair | Ada dalam daftar juicyFruits | Method `includes()` |
| Jumlah Valid | Antara 1-100 | Operator perbandingan `>=` dan `<=` |

## 📐 Alur Logika Fungsi

```
Input: fruitName, quantity
    ↓
Step 1: Validasi nama buah (regex)
    ↓
Step 2: Konversi ke lowercase
    ↓
Step 3: Cek apakah buah berair
    ↓
Step 4: Validasi jumlah (1-100)
    ↓
Step 5: Gabungkan semua kondisi (AND)
    ↓
Step 6: Return pesan sesuai hasil
    ↓
Output: String pesan
```

## 📌 Catatan Penting

⚠️ **Perhatian:** Fungsi ini menggunakan operator logika **AND** (`&&`), yang berarti **SEMUA** kondisi harus terpenuhi agar keranjang buah dianggap "splendiferous". Jika ada satu kondisi saja yang tidak terpenuhi, hasilnya akan "not so splendiferous".

💡 **Ternary Operator:** Fungsi ini menggunakan ternary operator (`? :`) untuk return statement yang lebih ringkas. Ini adalah shorthand dari if-else statement.

## 🔧 Penjelasan Teknis

### Regular Expression `/^[a-zA-Z ]+$/`

- `^` = Awal string
- `[a-zA-Z ]` = Karakter yang diizinkan (huruf kecil, huruf besar, dan spasi)
- `+` = Satu atau lebih karakter
- `$` = Akhir string

### Ternary Operator

```javascript
condition ? valueIfTrue : valueIfFalse
```

Cara kerja: Jika `condition` bernilai `true`, return `valueIfTrue`, jika tidak return `valueIfFalse`.

---

Made with 💚 for learning JavaScript
