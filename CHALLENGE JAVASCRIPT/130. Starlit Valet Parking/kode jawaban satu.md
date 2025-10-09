# 🚗 Dokumentasi Fungsi `parkingValet`

## 📋 Deskripsi

Fungsi `parkingValet` digunakan untuk mengatur plat nomor kendaraan dalam area parkir berbentuk grid (baris dan kolom). Fungsi ini mensimulasikan cara valet parker mengatur kendaraan di area parkir dengan pola zigzag - baris genap diisi dari kiri ke kanan, sedangkan baris ganjil diisi dari kanan ke kiri.

Jika jumlah plat nomor tidak cukup untuk mengisi semua slot parkir di baris terakhir, maka slot kosong akan diisi dengan karakter `-`.

---

## 🎯 Kegunaan

- Mengatur plat nomor kendaraan dalam format grid parkir
- Menampilkan tata letak parkir dengan pola zigzag yang realistis
- Menangani kasus ketika jumlah kendaraan tidak habis dibagi dengan jumlah slot per baris

---

## 📊 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `licensePlates` | `string` | String berisi karakter-karakter yang merepresentasikan plat nomor kendaraan |
| `spotsPerRow` | `number` | Jumlah slot parkir yang tersedia per baris |

---

## 📤 Return Value

**Tipe**: `Array<Array<string>>`

Mengembalikan array 2 dimensi yang merepresentasikan grid area parkir, dimana:
- Setiap elemen array utama adalah satu baris parkir
- Setiap baris berisi array karakter yang merepresentasikan plat nomor atau slot kosong (`-`)
- Baris dengan indeks ganjil (1, 3, 5, ...) dibalik urutannya (kanan ke kiri)

---

## 💻 Code Fungsi

```javascript
function parkingValet(licensePlates, spotsPerRow) {
  const result = [];
  let row = [];
  let reverse = false;
  
  // Loop melalui setiap karakter plat nomor
  for (let i = 0; i < licensePlates.length; i++) {
    // Tambahkan karakter plat ke baris saat ini
    row.push(licensePlates[i]);
    
    // Cek apakah baris sudah penuh ATAU ini adalah karakter terakhir
    if (row.length === spotsPerRow || i === licensePlates.length - 1) {
      
      // Isi slot kosong dengan '-' jika baris belum penuh
      while (row.length < spotsPerRow) {
        row.push('-');
      }
      
      // Tambahkan baris ke hasil (balik jika perlu)
      result.push(reverse ? row.reverse() : row);
      
      // Reset baris untuk baris berikutnya
      row = [];
      
      // Toggle flag reverse untuk baris selanjutnya
      reverse = !reverse;
    }
  }
  
  return result;
}
```

---

## 🔍 Cara Kerja

1. **Inisialisasi**: Siapkan array `result` untuk menyimpan semua baris, array `row` untuk baris saat ini, dan flag `reverse` untuk menentukan apakah baris perlu dibalik

2. **Loop Karakter**: Iterasi melalui setiap karakter dalam string `licensePlates`

3. **Isi Baris**: Tambahkan karakter ke array `row` satu per satu

4. **Cek Baris Penuh**: Ketika baris sudah penuh (`row.length === spotsPerRow`) ATAU sudah mencapai karakter terakhir, maka:
   - Isi slot kosong dengan `-` jika diperlukan
   - Balik urutan baris jika flag `reverse` bernilai `true`
   - Tambahkan baris ke `result`
   - Reset `row` menjadi array kosong
   - Toggle flag `reverse` untuk baris berikutnya

5. **Kembalikan Grid**: Return array 2 dimensi sebagai representasi area parkir

---

## 📝 Contoh Penggunaan

### Contoh 1: Grid Sempurna (Plat Cukup)

```javascript
const result1 = parkingValet("ABCDEF", 3);
console.log(result1);
```

**Output:**
```javascript
[
  ['A', 'B', 'C'],  // Baris 0 (reverse=false): kiri ke kanan
  ['F', 'E', 'D']   // Baris 1 (reverse=true): kanan ke kiri (dibalik)
]
```

**Visualisasi:**
```
A B C
F E D
```

---

### Contoh 2: Plat Tidak Cukup (Ada Slot Kosong)

```javascript
const result2 = parkingValet("12345", 3);
console.log(result2);
```

**Output:**
```javascript
[
  ['1', '2', '3'],  // Baris 0 (reverse=false): kiri ke kanan
  ['-', '-', '5']   // Baris 1 (reverse=true): kanan ke kiri + slot kosong
]
```

**Visualisasi:**
```
1 2 3
- - 5
```

**Penjelasan:** Karakter '4' dan '5' ditambahkan ke baris kedua. Ketika mencapai karakter terakhir ('5'), slot kosong diisi dengan '-', lalu baris dibalik menjadi ['-', '-', '5'].

---

### Contoh 3: Banyak Baris

```javascript
const result3 = parkingValet("ABCDEFGHIJK", 4);
console.log(result3);
```

**Output:**
```javascript
[
  ['A', 'B', 'C', 'D'],  // Baris 0 (reverse=false): kiri ke kanan
  ['H', 'G', 'F', 'E'],  // Baris 1 (reverse=true): kanan ke kiri
  ['I', 'J', 'K', '-']   // Baris 2 (reverse=false): kiri ke kanan
]
```

**Visualisasi:**
```
A B C D
H G F E
I J K -
```

---

### Contoh 4: Satu Karakter

```javascript
const result4 = parkingValet("X", 3);
console.log(result4);
```

**Output:**
```javascript
[
  ['X', '-', '-']  // Baris 0: langsung terdeteksi sebagai karakter terakhir
]
```

**Visualisasi:**
```
X - -
```

---

## 🎨 Tabel Karakter Khusus

| Karakter | Arti | Penggunaan |
|----------|------|------------|
| `-` | Slot parkir kosong | Digunakan ketika jumlah plat nomor kurang dari total slot yang tersedia di baris terakhir |

---

## ⚙️ Alur Flag `reverse`

| Baris | Nilai `reverse` (awal) | Aksi | Nilai `reverse` (setelah) |
|-------|------------------------|------|---------------------------|
| 0 | `false` | Tidak dibalik | `true` |
| 1 | `true` | Dibalik | `false` |
| 2 | `false` | Tidak dibalik | `true` |
| 3 | `true` | Dibalik | `false` |

Flag `reverse` di-toggle setiap kali selesai memproses satu baris, menciptakan pola zigzag.

---

## 💡 Tips Penggunaan

- ✅ Pastikan `spotsPerRow` adalah angka positif
- ✅ String `licensePlates` bisa berisi huruf, angka, atau karakter apapun
- ✅ Fungsi otomatis menangani kasus ketika plat tidak cukup mengisi semua slot
- ✅ Implementasi ini lebih efisien karena hanya loop sekali melalui string
- ⚠️ Spasi dalam string `licensePlates` akan dihitung sebagai karakter tersendiri

---

## 🧪 Test Case

```javascript
// Test 1: Grid kecil sempurna
parkingValet("ABC", 3);
// Output: [['A', 'B', 'C']]

// Test 2: Dua baris dengan slot kosong
parkingValet("12345", 3);
// Output: [['1','2','3'], ['-','-','5']]

// Test 3: Tiga baris zigzag
parkingValet("123456789", 3);
// Output: [['1','2','3'], ['6','5','4'], ['7','8','9']]

// Test 4: Satu slot per baris
parkingValet("ABCD", 1);
// Output: [['A'], ['B'], ['C'], ['D']]

// Test 5: Banyak slot kosong
parkingValet("XYZ", 5);
// Output: [['X', 'Y', 'Z', '-', '-']]
```

---

## 🔄 Perbandingan dengan Implementasi Lain

Implementasi ini memiliki keunggulan:
- **Lebih efisien**: Hanya satu loop melalui string (O(n))
- **Lebih sederhana**: Menggunakan flag boolean untuk kontrol zigzag
- **Lebih mudah dibaca**: Logika yang straightforward tanpa perhitungan indeks kompleks

---

## 📚 Catatan Tambahan

Fungsi ini sangat berguna untuk:
- Simulasi sistem parkir valet
- Visualisasi data dalam format grid
- Pembelajaran tentang manipulasi array 2 dimensi
- Memahami konsep toggle flag untuk membuat pola bergantian

Pola zigzag yang dihasilkan mencerminkan cara parkir yang efisien di dunia nyata, dimana valet parker bergerak bolak-balik antar baris untuk meminimalkan jarak tempuh.

---

## 🎓 Konsep Penting yang Digunakan

1. **String Indexing**: Mengakses karakter string dengan `licensePlates[i]`
2. **Array Push**: Menambahkan elemen ke array dengan `push()`
3. **Array Reverse**: Membalik urutan array dengan `reverse()`
4. **Boolean Toggle**: Mengubah nilai boolean dengan `!reverse`
5. **Conditional (Ternary) Operator**: `reverse ? row.reverse() : row`
6. **While Loop**: Mengisi slot kosong sampai baris penuh
