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
  const plates = licensePlates.split('');
  
  // Loop melalui setiap karakter plat dengan increment sebesar spotsPerRow
  for (let i = 0; i < plates.length; i += spotsPerRow) {
    const row = [];
    
    // Isi setiap slot dalam satu baris
    for (let j = 0; j < spotsPerRow; j++) {
      if (i + j < plates.length) {
        // Jika masih ada plat yang tersedia, masukkan ke slot
        row.push(plates[i + j]);
      } else {
        // Jika plat habis, isi dengan karakter kosong '-'
        row.push('-');
      }
    }
    
    // Tentukan indeks baris saat ini
    const rowIndex = Math.floor(i / spotsPerRow);
    
    // Jika baris ganjil (1, 3, 5, ...), balik urutan slot
    if (rowIndex % 2 === 1) {
      row.reverse();
    }
    
    // Tambahkan baris ke hasil akhir
    result.push(row);
  }
  
  return result;
}
```

---

## 🔍 Cara Kerja

1. **Pecah String**: String `licensePlates` dipecah menjadi array karakter individu
2. **Buat Baris**: Loop luar membuat baris baru setiap `spotsPerRow` karakter
3. **Isi Slot**: Loop dalam mengisi setiap slot di baris dengan karakter plat atau `-` jika plat habis
4. **Pola Zigzag**: Baris dengan indeks ganjil dibalik untuk menciptakan pola zigzag
5. **Kembalikan Grid**: Array 2 dimensi dikembalikan sebagai representasi area parkir

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
  ['A', 'B', 'C'],  // Baris 0 (genap): kiri ke kanan
  ['F', 'E', 'D']   // Baris 1 (ganjil): kanan ke kiri (dibalik)
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
  ['1', '2', '3'],  // Baris 0 (genap): kiri ke kanan
  ['-', '-', '5']   // Baris 1 (ganjil): kanan ke kiri + slot kosong
]
```

**Visualisasi:**
```
1 2 3
- - 5
```

---

### Contoh 3: Banyak Baris

```javascript
const result3 = parkingValet("ABCDEFGHIJK", 4);
console.log(result3);
```

**Output:**
```javascript
[
  ['A', 'B', 'C', 'D'],  // Baris 0 (genap): kiri ke kanan
  ['H', 'G', 'F', 'E'],  // Baris 1 (ganjil): kanan ke kiri
  ['I', 'J', 'K', '-']   // Baris 2 (genap): kiri ke kanan
]
```

**Visualisasi:**
```
A B C D
H G F E
I J K -
```

---

## 🎨 Tabel Karakter Khusus

| Karakter | Arti | Penggunaan |
|----------|------|------------|
| `-` | Slot parkir kosong | Digunakan ketika jumlah plat nomor kurang dari total slot yang tersedia |

---

## 💡 Tips Penggunaan

- ✅ Pastikan `spotsPerRow` adalah angka positif
- ✅ String `licensePlates` bisa berisi huruf, angka, atau karakter apapun
- ✅ Fungsi otomatis menangani kasus ketika plat tidak cukup mengisi semua slot
- ⚠️ Spasi dalam string `licensePlates` akan dihitung sebagai karakter tersendiri

---

## 🧪 Test Case

```javascript
// Test 1
parkingValet("ABC", 2);
// Output: [['A', 'B'], ['C', '-']]

// Test 2
parkingValet("123456789", 3);
// Output: [['1','2','3'], ['6','5','4'], ['7','8','9']]

// Test 3
parkingValet("XYZ", 5);
// Output: [['X', 'Y', 'Z', '-', '-']]
```

---

## 📚 Catatan Tambahan

Fungsi ini sangat berguna untuk:
- Simulasi sistem parkir valet
- Visualisasi data dalam format grid
- Pembelajaran tentang manipulasi array 2 dimensi
- Memahami konsep modulo untuk membuat pola bergantian

Pola zigzag yang dihasilkan mencerminkan cara parkir yang efisien di dunia nyata, dimana valet parker bergerak bolak-balik antar baris untuk meminimalkan jarak tempuh.
