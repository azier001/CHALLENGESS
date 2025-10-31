# 📊 Dokumentasi Fungsi `analyzeMagnetodynamo`

## 🎯 Deskripsi

Fungsi `analyzeMagnetodynamo` adalah fungsi yang menganalisis dua set data dengan cara menggabungkan **bagian pertama dari data primer** dengan **bagian akhir dari data sekunder**, kemudian menghitung nilai rata-ratanya.

Fungsi ini berguna ketika Anda ingin mengambil sampel dari dua sumber data yang berbeda dan mendapatkan nilai statistik gabungan dari kedua sampel tersebut.

---

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `primaryData` | Array | Array berisi data angka yang akan diambil setengah bagian pertamanya |
| `secondaryData` | Array | Array berisi data angka yang akan diambil setengah bagian akhirnya |

---

## 🔄 Cara Kerja

1. **Mengambil Setengah Pertama** dari `primaryData`
2. **Mengambil Setengah Akhir** dari `secondaryData`
3. **Menggabungkan** kedua bagian tersebut menjadi satu array
4. **Menghitung Rata-rata** dari array gabungan

---

## 💻 Kode Fungsi

```javascript
function analyzeMagnetodynamo(primaryData, secondaryData) {
  
  // Potong array primaryData untuk mengambil hanya setengah bagian pertama dari elemen-elemennya
  const slicedPrimary = primaryData.slice(0, Math.floor(primaryData.length / 2));
  
  // Potong array secondaryData untuk mengambil hanya setengah bagian akhir dari elemen-elemennya
  const slicedSecondary = secondaryData.slice(Math.ceil(secondaryData.length / 2));
  
  // Gabungkan primaryData yang telah dipotong dengan secondaryData yang telah dipotong
  const combinedData = slicedPrimary.concat(slicedSecondary);
  
  // Hitung nilai rata-rata (mean) dari array gabungan yang dihasilkan
  const average = combinedData.reduce((sum, value) => sum + value, 0) / combinedData.length;
  
  // Kembalikan nilai rata-rata yang telah dihitung
  return average;
}
```

---

## 📊 Contoh Penggunaan

### Contoh 1: Array dengan Jumlah Genap

```javascript
const dataA = [10, 20, 30, 40];
const dataB = [50, 60, 70, 80];

const hasil = analyzeMagnetodynamo(dataA, dataB);
console.log(hasil);
```

**Output:**
```
50
```

**Penjelasan:**
- Setengah pertama dari `dataA`: `[10, 20]`
- Setengah akhir dari `dataB`: `[70, 80]`
- Gabungan: `[10, 20, 70, 80]`
- Rata-rata: `(10 + 20 + 70 + 80) / 4 = 50`

---

### Contoh 2: Array dengan Jumlah Ganjil

```javascript
const dataX = [5, 10, 15, 20, 25];
const dataY = [30, 35, 40, 45, 50];

const hasil = analyzeMagnetodynamo(dataX, dataY);
console.log(hasil);
```

**Output:**
```
30
```

**Penjelasan:**
- Setengah pertama dari `dataX`: `[5, 10]` (pembulatan ke bawah)
- Setengah akhir dari `dataY`: `[40, 45, 50]` (pembulatan ke atas)
- Gabungan: `[5, 10, 40, 45, 50]`
- Rata-rata: `(5 + 10 + 40 + 45 + 50) / 5 = 30`

---

## ⚠️ Catatan Penting

- Pastikan kedua parameter berisi array dengan elemen berupa angka
- Fungsi menggunakan `Math.floor()` untuk setengah pertama dan `Math.ceil()` untuk setengah akhir
- Jika array kosong, fungsi akan menghasilkan `NaN` (Not a Number)

---

## 🎓 Tips untuk Pemula

- **`slice()`**: Metode untuk mengambil sebagian elemen dari array
- **`concat()`**: Metode untuk menggabungkan dua array
- **`reduce()`**: Metode untuk menjumlahkan semua elemen dalam array
- **`Math.floor()`**: Membulatkan angka ke bawah (misal: 2.8 → 2)
- **`Math.ceil()`**: Membulatkan angka ke atas (misal: 2.2 → 3)

---

## 📌 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Number` | Nilai rata-rata dari gabungan setengah pertama `primaryData` dan setengah akhir `secondaryData` |

---

**© 2025 - Dokumentasi dibuat dengan ❤️**
