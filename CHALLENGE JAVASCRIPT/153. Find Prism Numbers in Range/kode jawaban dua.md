# 📐 Dokumentasi Fungsi `findPrismNumbers`

## 📝 Deskripsi

Fungsi `findPrismNumbers` adalah fungsi yang digunakan untuk mencari semua **bilangan prism** (pronic numbers) dalam rentang tertentu. Bilangan prism adalah hasil perkalian dua bilangan bulat berurutan, dengan rumus: `n × (n + 1)`.

Contoh bilangan prism:
- 2 × 3 = 6
- 3 × 4 = 12
- 4 × 5 = 20
- 5 × 6 = 30

Bilangan prism juga dikenal sebagai **bilangan oblong** atau **bilangan heteromecic**.

---

## 🎯 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `start` | Number | Nilai awal dari rentang pencarian (inklusif) |
| `end` | Number | Nilai akhir dari rentang pencarian (inklusif) |

---

## 📤 Return Value

**Tipe:** `Array`

Mengembalikan array yang berisi semua bilangan prism yang ditemukan dalam rentang `start` hingga `end`.

---

## 💻 Kode Fungsi

```javascript
function findPrismNumbers(start, end) {
    const prismNumbers = [];
    
    // Loop untuk mencari semua bilangan prism dalam rentang
    for (let i = 2; i * (i + 1) <= end; i++) {
        // Hitung bilangan prism dengan rumus: n × (n + 1)
        const prism = i * (i + 1);
        
        // Cek apakah bilangan prism berada dalam rentang yang ditentukan
        if (prism >= start && prism <= end) {
            prismNumbers.push(prism);
        }
    }
    
    return prismNumbers;
}
```

---

## 🔍 Cara Kerja

1. **Inisialisasi Array Kosong**: Membuat array `prismNumbers` untuk menyimpan hasil.

2. **Perulangan**: Loop dimulai dari `i = 2` dan berlanjut selama `i × (i + 1) ≤ end`.
   - Mengapa dimulai dari 2? Karena bilangan prism terkecil adalah 2 × 3 = 6.

3. **Perhitungan**: Setiap iterasi menghitung `prism = i × (i + 1)`.

4. **Pengecekan Rentang**: Jika bilangan prism berada dalam rentang `start` hingga `end`, maka akan ditambahkan ke array.

5. **Return**: Mengembalikan array berisi semua bilangan prism yang ditemukan.

---

## 📊 Tabel Bilangan Prism

| n | Rumus | Bilangan Prism |
|---|-------|----------------|
| 2 | 2 × 3 | 6 |
| 3 | 3 × 4 | 12 |
| 4 | 4 × 5 | 20 |
| 5 | 5 × 6 | 30 |
| 6 | 6 × 7 | 42 |
| 7 | 7 × 8 | 56 |
| 8 | 8 × 9 | 72 |
| 9 | 9 × 10 | 90 |
| 10 | 10 × 11 | 110 |

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

**Penjelasan:** Bilangan prism antara 10-100 (10 inklusif, jadi 6 tidak termasuk).

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

### Contoh 4: Tidak Ada Bilangan Prism

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

- **Time Complexity**: O(√n) dimana n adalah nilai `end`
- **Space Complexity**: O(k) dimana k adalah jumlah bilangan prism yang ditemukan

---

## 💡 Tips untuk Pemula

1. **Bilangan Prism vs Bilangan Prima**: Jangan bingung! Bilangan prism adalah hasil kali dua bilangan berurutan, sedangkan bilangan prima hanya bisa dibagi 1 dan dirinya sendiri.

2. **Rentang Inklusif**: Parameter `start` dan `end` bersifat inklusif, artinya jika ada bilangan prism yang sama dengan `start` atau `end`, maka akan dimasukkan ke hasil.

3. **Efisiensi**: Loop berhenti ketika `i × (i + 1) > end` untuk menghindari perhitungan yang tidak perlu.

---

## 🎓 Pengetahuan Tambahan

Bilangan prism memiliki sifat matematika yang menarik:
- Setiap bilangan prism adalah bilangan genap
- Bilangan prism ke-n = n × (n + 1) = n² + n
- Jumlah dua bilangan prism berurutan selalu berbentuk bilangan kuadrat sempurna

---

**Dibuat dengan ❤️ untuk membantu pembelajaran programming**
