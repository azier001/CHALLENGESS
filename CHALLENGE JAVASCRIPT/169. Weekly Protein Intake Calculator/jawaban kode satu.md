# 📊 Dokumentasi Fungsi `calculateDailyProtein`

## 🎯 Deskripsi

Fungsi `calculateDailyProtein` digunakan untuk menghitung **total protein harian** dari sebuah rencana makan (meal plan). Fungsi ini akan memproses data rencana makan per hari dan menjumlahkan kandungan protein dari setiap makanan, dengan mengabaikan makanan yang tidak valid (ditandai dengan nilai `-1`).

---

## 📝 Penjelasan Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `mealPlan` | `Array<Array<number>>` | Array 2 dimensi yang berisi rencana makan. Setiap elemen array utama merepresentasikan **satu hari**, dan setiap elemen di dalamnya merepresentasikan **kandungan protein dari satu makanan** (dalam gram). Nilai `-1` menandakan makanan yang tidak valid atau dilewati. |

### 🔍 Penjelasan Detail Parameter

- **`mealPlan`**: Struktur data berupa array di dalam array
  - **Array Luar**: Merepresentasikan hari-hari (misalnya: Hari 1, Hari 2, dst.)
  - **Array Dalam**: Merepresentasikan makanan dalam satu hari (misalnya: Sarapan, Makan Siang, Makan Malam)
  - **Nilai `-1`**: Menandakan makanan yang dilewati atau tidak ada

---

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Array<number>` | Array yang berisi **total protein per hari** (dalam gram). Panjang array sama dengan jumlah hari dalam `mealPlan`. |

---

## 💻 Kode Fungsi

```javascript
function calculateDailyProtein(mealPlan) {
    // Iterasi setiap hari dalam rencana makan
    return mealPlan.map(day => 
        // Hitung total protein per hari dengan menjumlahkan semua makanan
        day.reduce((total, meal) => 
            // Jika meal bernilai -1 (tidak valid), tambahkan 0
            // Jika tidak, tambahkan nilai protein dari meal tersebut
            total + (meal === -1 ? 0 : meal), 
            0 // Nilai awal untuk total adalah 0
        )
    );
}
```

---

## 🎓 Cara Kerja Fungsi

1. **Map** → Fungsi akan melakukan iterasi pada setiap hari (`mealPlan.map()`)
2. **Reduce** → Di setiap hari, fungsi menjumlahkan kandungan protein dari semua makanan (`day.reduce()`)
3. **Filter -1** → Makanan dengan nilai `-1` dianggap 0 gram protein (tidak dihitung)
4. **Return** → Mengembalikan array berisi total protein per hari

---

## 📋 Contoh Penggunaan

### Contoh 1: Rencana Makan 3 Hari

```javascript
// Data: 3 hari dengan 3 makanan per hari
const mealPlan = [
    [25, 30, 35],  // Hari 1: Sarapan 25g, Makan Siang 30g, Makan Malam 35g
    [20, -1, 40],  // Hari 2: Sarapan 20g, Tidak makan siang, Makan Malam 40g
    [30, 25, 30]   // Hari 3: Sarapan 30g, Makan Siang 25g, Makan Malam 30g
];

const result = calculateDailyProtein(mealPlan);
console.log(result);
```

**Output:**
```javascript
[90, 60, 85]
```

**Penjelasan Output:**
- **Hari 1**: 25 + 30 + 35 = **90 gram protein**
- **Hari 2**: 20 + 0 + 40 = **60 gram protein** (makan siang dilewati)
- **Hari 3**: 30 + 25 + 30 = **85 gram protein**

---

### Contoh 2: Rencana Makan dengan Banyak Makanan Dilewati

```javascript
const mealPlan = [
    [15, -1, -1, 20],  // Hanya makan 2 kali
    [-1, -1, -1, -1],  // Tidak ada data protein (puasa/skip)
    [10, 15, 20, 25]   // Makan 4 kali
];

const result = calculateDailyProtein(mealPlan);
console.log(result);
```

**Output:**
```javascript
[35, 0, 70]
```

**Penjelasan Output:**
- **Hari 1**: 15 + 0 + 0 + 20 = **35 gram protein**
- **Hari 2**: 0 + 0 + 0 + 0 = **0 gram protein**
- **Hari 3**: 10 + 15 + 20 + 25 = **70 gram protein**

---

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- 📱 Aplikasi tracking nutrisi harian
- 🏋️ Aplikasi fitness dan diet
- 🍽️ Meal planning dan meal prep
- 📊 Dashboard analisis pola makan
- 💪 Program pembentukan otot (muscle building)

---

## ⚠️ Catatan Penting

- Nilai `-1` akan **diabaikan** dalam perhitungan
- Fungsi menggunakan **operator ternary** untuk mengecek nilai `-1`
- Pastikan setiap elemen dalam array adalah **angka** atau `-1`
- Fungsi akan mengembalikan array dengan panjang yang **sama** dengan jumlah hari

---

## 🚀 Tips Pengembangan

Anda bisa mengembangkan fungsi ini dengan:
- Menambahkan validasi input
- Menghitung rata-rata protein per hari
- Menambahkan tracking nutrisi lain (karbohidrat, lemak)
- Membuat visualisasi grafik dari hasil perhitungan
