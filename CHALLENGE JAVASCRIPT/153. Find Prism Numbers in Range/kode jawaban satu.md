# 📐 Dokumentasi Fungsi `findPrismNumbers` & `isPrismNumber`

## 📝 Deskripsi

Fungsi `findPrismNumbers` adalah fungsi yang digunakan untuk mencari semua **bilangan prism** (pronic numbers) dalam rentang tertentu. Bilangan prism adalah hasil perkalian dua bilangan bulat berurutan, dengan rumus: `n × (n + 1)`.

Contoh bilangan prism:
- 2 × 3 = 6
- 3 × 4 = 12
- 4 × 5 = 20
- 5 × 6 = 30

Bilangan prism juga dikenal sebagai **bilangan oblong** atau **bilangan heteromecic**.

Fungsi ini bekerja dengan cara mengiterasi setiap angka dalam rentang dan memeriksa apakah angka tersebut adalah bilangan prism menggunakan fungsi helper `isPrismNumber`.

---

## 🎯 Parameter Fungsi

### `findPrismNumbers(start, end)`

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `start` | Number | Nilai awal dari rentang pencarian (inklusif) |
| `end` | Number | Nilai akhir dari rentang pencarian (inklusif) |

### `isPrismNumber(num)`

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `num` | Number | Bilangan yang akan diperiksa apakah merupakan bilangan prism |

---

## 📤 Return Value

### `findPrismNumbers(start, end)`

**Tipe:** `Array`

Mengembalikan array yang berisi semua bilangan prism yang ditemukan dalam rentang `start` hingga `end`.

### `isPrismNumber(num)`

**Tipe:** `Boolean`

Mengembalikan `true` jika `num` adalah bilangan prism, dan `false` jika bukan.

---

## 💻 Kode Fungsi

```javascript
function findPrismNumbers(start, end) {
  const prismNumbers = [];
  
  // Iterasi setiap angka dari start hingga end
  for (let i = start; i <= end; i++) {
    // Cek apakah angka i adalah bilangan prism
    if (isPrismNumber(i)) {
      prismNumbers.push(i);
    }
  }
  
  return prismNumbers;
}


function isPrismNumber(num) {
  // Loop dari 2 hingga akar kuadrat dari num
  for (let i = 2; i <= Math.sqrt(num); i++) {
    // Cek apakah num habis dibagi i DAN hasil baginya adalah i+1
    // Jika ya, maka num = i × (i+1) yang merupakan bilangan prism
    if (num % i === 0 && num / i === i + 1) {
      return true;
    }
  }
  
  return false;
}
```

---

## 🔍 Cara Kerja

### Fungsi `findPrismNumbers`

1. **Inisialisasi Array Kosong**: Membuat array `prismNumbers` untuk menyimpan hasil.

2. **Perulangan**: Loop dari `start` hingga `end` untuk memeriksa setiap angka.

3. **Pengecekan**: Setiap angka diperiksa menggunakan fungsi `isPrismNumber()`.

4. **Penyimpanan**: Jika angka adalah bilangan prism, tambahkan ke array `prismNumbers`.

5. **Return**: Mengembalikan array berisi semua bilangan prism yang ditemukan.

### Fungsi `isPrismNumber`

1. **Perulangan**: Loop dari `i = 2` hingga `√num`.
   - Mengapa hingga √num? Karena jika `num = i × (i+1)`, maka `i` pasti ≤ √num.

2. **Pengecekan Dua Kondisi**:
   - `num % i === 0`: Cek apakah num habis dibagi i (i adalah faktor dari num)
   - `num / i === i + 1`: Cek apakah hasil bagi num dengan i adalah (i+1)

3. **Logic**: Jika kedua kondisi terpenuhi, berarti `num = i × (i+1)`, yang merupakan definisi bilangan prism.

4. **Return**: Kembalikan `true` jika bilangan prism ditemukan, `false` jika tidak.

---

## 📊 Tabel Bilangan Prism

| n | Rumus | Bilangan Prism | Faktor |
|---|-------|----------------|--------|
| 2 | 2 × 3 | 6 | 2 dan 3 |
| 3 | 3 × 4 | 12 | 3 dan 4 |
| 4 | 4 × 5 | 20 | 4 dan 5 |
| 5 | 5 × 6 | 30 | 5 dan 6 |
| 6 | 6 × 7 | 42 | 6 dan 7 |
| 7 | 7 × 8 | 56 | 7 dan 8 |
| 8 | 8 × 9 | 72 | 8 dan 9 |
| 9 | 9 × 10 | 90 | 9 dan 10 |
| 10 | 10 × 11 | 110 | 10 dan 11 |

---

## 🎬 Contoh Penggunaan

### Contoh 1: Rentang 1-50

```javascript
const result = findPrismNumbers(1, 50);
console.log(result);
```

**Output:**
```javascript
[6, 12, 20, 30, 42]
```

**Penjelasan:** Bilangan prism antara 1-50 adalah 6, 12, 20, 30, dan 42.

---

### Contoh 2: Rentang 10-100

```javascript
const result = findPrismNumbers(10, 100);
console.log(result);
```

**Output:**
```javascript
[12, 20, 30, 42, 56, 72, 90]
```

**Penjelasan:** Bilangan prism antara 10-100. Angka 6 tidak termasuk karena < 10.

---

### Contoh 3: Rentang 50-150

```javascript
const result = findPrismNumbers(50, 150);
console.log(result);
```

**Output:**
```javascript
[56, 72, 90, 110, 132]
```

**Penjelasan:** Bilangan prism antara 50-150.

---

### Contoh 4: Mengecek Satu Bilangan

```javascript
console.log(isPrismNumber(6));   // true
console.log(isPrismNumber(12));  // true
console.log(isPrismNumber(15));  // false
console.log(isPrismNumber(20));  // true
console.log(isPrismNumber(25));  // false
```

**Output:**
```javascript
true
true
false
true
false
```

**Penjelasan:**
- 6 = 2 × 3 ✅ (bilangan prism)
- 12 = 3 × 4 ✅ (bilangan prism)
- 15 = 3 × 5 ❌ (bukan bilangan berurutan)
- 20 = 4 × 5 ✅ (bilangan prism)
- 25 = 5 × 5 ❌ (bukan dua bilangan berbeda)

---

### Contoh 5: Tidak Ada Bilangan Prism

```javascript
const result = findPrismNumbers(7, 11);
console.log(result);
```

**Output:**
```javascript
[]
```

**Penjelasan:** Tidak ada bilangan prism dalam rentang 7-11 (karena 6 < 7 dan 12 > 11).

---

## ⚡ Kompleksitas

### `findPrismNumbers`
- **Time Complexity**: O(n × √m) 
  - n = jumlah angka dalam rentang (end - start + 1)
  - m = nilai maksimum yang diperiksa
- **Space Complexity**: O(k) dimana k adalah jumlah bilangan prism yang ditemukan

### `isPrismNumber`
- **Time Complexity**: O(√n) dimana n adalah nilai yang diperiksa
- **Space Complexity**: O(1) - hanya menggunakan beberapa variabel

---

## 🔄 Perbedaan dengan Implementasi Sebelumnya

Implementasi ini menggunakan pendekatan **iterasi penuh** dengan helper function, yang berbeda dengan implementasi sebelumnya:

| Aspek | Implementasi Ini | Implementasi Sebelumnya |
|-------|------------------|-------------------------|
| **Pendekatan** | Cek setiap angka dalam rentang | Generate bilangan prism langsung |
| **Kompleksitas** | O(n × √m) | O(√n) |
| **Fleksibilitas** | Bisa cek bilangan individual | Hanya untuk rentang |
| **Kode** | Lebih modular dengan helper | Lebih efisien |

---

## 💡 Tips untuk Pemula

1. **Helper Function**: Fungsi `isPrismNumber` adalah contoh bagus dari helper function yang membuat kode lebih modular dan mudah dibaca.

2. **Kondisi AND (&&)**: Perhatikan penggunaan `&&` dalam pengecekan. Kedua kondisi harus `true` agar bilangan dianggap sebagai bilangan prism.

3. **Math.sqrt()**: Menggunakan akar kuadrat untuk membatasi loop agar lebih efisien.

4. **Modulo Operator (%)**: Operator `%` digunakan untuk mengecek apakah suatu bilangan habis dibagi bilangan lain (sisa bagi = 0).

5. **Testing Individual**: Dengan pendekatan ini, kamu bisa dengan mudah mengecek apakah satu bilangan tertentu adalah bilangan prism tanpa perlu mencari dalam rentang.

---

## 🎓 Pengetahuan Tambahan

### Mengapa Cek `num / i === i + 1`?

Jika `num` adalah bilangan prism, maka:
- `num = i × (i + 1)`
- Jadi: `num / i = (i + 1)`

Contoh dengan num = 12:
- Loop mencoba i = 2: `12 / 2 = 6`, tapi `6 ≠ 3` ❌
- Loop mencoba i = 3: `12 / 3 = 4`, dan `4 = 3 + 1` ✅

### Sifat Bilangan Prism

- Setiap bilangan prism adalah bilangan **genap**
- Bilangan prism ke-n = n² + n
- Bilangan prism selalu habis dibagi 2
- Jumlah digit dari bilangan prism yang kecil: 6(6), 12(3), 20(2), 30(3), 42(6)...

---

## 🐛 Debugging Example

Jika ingin melihat proses pengecekan:

```javascript
function isPrismNumberDebug(num) {
  console.log(`Mengecek bilangan: ${num}`);
  
  for (let i = 2; i <= Math.sqrt(num); i++) {
    console.log(`  Coba i = ${i}: ${num} % ${i} = ${num % i}, ${num} / ${i} = ${num / i}`);
    
    if (num % i === 0 && num / i === i + 1) {
      console.log(`  ✅ Bilangan prism! ${num} = ${i} × ${i + 1}`);
      return true;
    }
  }
  
  console.log(`  ❌ Bukan bilangan prism`);
  return false;
}

// Test
isPrismNumberDebug(12);
```

**Output:**
```
Mengecek bilangan: 12
  Coba i = 2: 12 % 2 = 0, 12 / 2 = 6
  Coba i = 3: 12 % 3 = 0, 12 / 3 = 4
  ✅ Bilangan prism! 12 = 3 × 4
```

---

**Dibuat dengan ❤️ untuk membantu pembelajaran programming**
