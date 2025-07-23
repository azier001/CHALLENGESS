# 🐛 Dokumentasi Fungsi `sortInsectSpecimens`

## 📋 Deskripsi

Fungsi `sortInsectSpecimens` adalah sebuah fungsi JavaScript yang digunakan untuk memproses dan mengurutkan data spesimen serangga. Fungsi ini melakukan dua operasi utama:

1. **Modifikasi Data**: Menambahkan nilai 1 pada setiap spesimen ketiga dalam array
2. **Pengurutan**: Mengurutkan seluruh array dalam urutan naik (ascending order)

Fungsi ini berguna dalam konteks penelitian entomologi atau pengelolaan koleksi serangga dimana diperlukan penyesuaian ukuran dan pengurutan data spesimen.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `specimens` | `Array<number>` | Array berisi angka yang merepresentasikan ukuran atau data numerik spesimen serangga |

### 📝 Detail Parameter

- **specimens**: Array yang berisi data numerik spesimen serangga
  - Tipe data: Array of Numbers
  - Wajib diisi: Ya
  - Contoh: `[5, 3, 8, 2, 7, 4]`

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Array<number>` | Array yang sudah dimodifikasi dan diurutkan dalam urutan naik |

## 🔍 Cara Kerja Fungsi

### Langkah 1: Modifikasi Spesimen Ketiga
Fungsi akan menambahkan nilai 1 pada setiap elemen ketiga dalam array (indeks 2, 5, 8, dst.)

### Langkah 2: Pengurutan
Array yang sudah dimodifikasi kemudian diurutkan dalam urutan naik menggunakan metode `sort()`

### Langkah 3: Return
Mengembalikan array yang sudah diproses

## 💻 Kode Fungsi

```javascript
function sortInsectSpecimens(specimens) {
  // Langkah 1: Tambahkan ukuran setiap spesimen ketiga
  for (let i = 2; i < specimens.length; i += 3) {
    specimens[i] += 1;
  }
  
  // Langkah 2: Urutkan array dalam urutan naik
  specimens.sort((a, b) => a - b);
  
  // Langkah 3: Kembalikan array yang sudah diurutkan
  return specimens;
}
```

## 📊 Contoh Penggunaan

### Contoh 1: Array Sederhana

```javascript
// Input
const specimens1 = [5, 3, 8, 2, 7, 4];
const result1 = sortInsectSpecimens(specimens1);

console.log(result1);
// Output: [2, 3, 5, 5, 7, 9]
```

**Penjelasan Proses:**
- Spesimen ketiga (indeks 2): 8 + 1 = 9
- Spesimen keenam (indeks 5): 4 + 1 = 5
- Array setelah modifikasi: `[5, 3, 9, 2, 7, 5]`
- Array setelah diurutkan: `[2, 3, 5, 5, 7, 9]`

### Contoh 2: Array Dengan Lebih Banyak Elemen

```javascript
// Input
const specimens2 = [10, 15, 20, 25, 30, 35, 40, 45, 50];
const result2 = sortInsectSpecimens(specimens2);

console.log(result2);
// Output: [10, 15, 21, 25, 30, 36, 40, 45, 51]
```

**Penjelasan Proses:**
- Spesimen ketiga (indeks 2): 20 + 1 = 21
- Spesimen keenam (indeks 5): 35 + 1 = 36  
- Spesimen kesembilan (indeks 8): 50 + 1 = 51
- Array setelah modifikasi: `[10, 15, 21, 25, 30, 36, 40, 45, 51]`
- Array sudah dalam urutan yang benar setelah modifikasi

### Contoh 3: Array Kecil

```javascript
// Input
const specimens3 = [100, 50];
const result3 = sortInsectSpecimens(specimens3);

console.log(result3);
// Output: [50, 100]
```

**Penjelasan Proses:**
- Tidak ada elemen ketiga untuk dimodifikasi (array hanya 2 elemen)
- Array langsung diurutkan: `[50, 100]`

## ⚠️ Catatan Penting

- **Modifikasi In-Place**: Fungsi ini memodifikasi array asli (`specimens`). Jika Anda ingin mempertahankan array asli, buat salinan terlebih dahulu:
  ```javascript
  const originalSpecimens = [5, 3, 8, 2, 7, 4];
  const copySpecimens = [...originalSpecimens];
  const result = sortInsectSpecimens(copySpecimens);
  ```

- **Indeks Array**: JavaScript menggunakan indeks berbasis 0, sehingga "spesimen ketiga" berada pada indeks 2

- **Tipe Data**: Pastikan array hanya berisi angka untuk hasil yang optimal

- **Loop Pattern**: Loop dimulai dari indeks 2 dan bertambah 3 setiap iterasi (2, 5, 8, 11, ...)

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- Pengelolaan data koleksi serangga dalam museum atau laboratorium
- Preprocessing data sebelum analisis statistik
- Simulasi pertumbuhan spesimen dalam penelitian biologi
- Standardisasi data pengukuran dalam penelitian entomologi

## 🔗 Teknologi Terkait

- **JavaScript Array Methods**: `sort()`, loop `for`
- **ES6 Features**: Arrow functions
- **Data Processing**: Manipulasi array numerik
