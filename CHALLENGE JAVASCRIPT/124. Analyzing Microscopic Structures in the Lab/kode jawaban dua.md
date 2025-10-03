# 📊 Dokumentasi Fungsi `analyzeMicrostructures`

## 📝 Deskripsi

Fungsi `analyzeMicrostructures` digunakan untuk menganalisis dan mencari struktur mikro tertentu dalam sebuah array. Fungsi ini akan mencari posisi struktur target dalam array dan memberikan laporan mengenai hasil pencarian beserta jumlah total struktur yang diperiksa.

---

## 🎯 Kegunaan

Fungsi ini cocok digunakan untuk:
- Mencari posisi suatu elemen dalam array
- Menganalisis data struktur mikro
- Validasi keberadaan data dalam koleksi
- Audit dan pelacakan elemen dalam dataset

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `structures` | Array | Array yang berisi kumpulan struktur mikro yang akan dianalisis |
| `target` | String/Number/Any | Struktur target yang ingin dicari dalam array |

---

## 📤 Return Value

| Kondisi | Tipe Return | Format Output |
|---------|-------------|---------------|
| Struktur **ditemukan** | String | `"Structure '[target]' found at position [posisi]. Total structures examined: [total]."` |
| Struktur **tidak ditemukan** | String | `"Structure '[target]' not found. Total structures examined: [total]."` |

> **Catatan:** Posisi yang dikembalikan menggunakan indeks berbasis 1 (dimulai dari 1, bukan 0)

---

## 💻 Source Code

```javascript
function analyzeMicrostructures(structures, target) {
  // Mencari indeks dari struktur target dalam array
  const index = structures.indexOf(target);
  
  // Menghitung total jumlah struktur dalam array
  const total = structures.length;
  
  // Mengecek apakah struktur ditemukan (indeks tidak sama dengan -1)
  if (index !== -1) {
    // Mengkonversi indeks ke posisi (indeks + 1 karena posisi dimulai dari 1)
    const position = index + 1;
    
    // Mengembalikan pesan sukses dengan informasi posisi
    return `Structure '${target}' found at position ${position}. Total structures examined: ${total}.`;
    
  } else {
    // Mengembalikan pesan bahwa struktur tidak ditemukan
    return `Structure '${target}' not found. Total structures examined: ${total}.`;
  }
}
```

---

## 🔍 Cara Kerja

1. **Pencarian Indeks**: Fungsi menggunakan method `indexOf()` untuk mencari posisi target dalam array
2. **Perhitungan Total**: Menghitung jumlah total elemen dalam array menggunakan property `length`
3. **Validasi Hasil**: 
   - Jika `index !== -1` → struktur ditemukan
   - Jika `index === -1` → struktur tidak ditemukan
4. **Konversi Posisi**: Mengubah indeks (berbasis 0) menjadi posisi (berbasis 1)
5. **Return Pesan**: Mengembalikan string dengan informasi hasil pencarian

---

## 📚 Contoh Penggunaan

### Contoh 1: Struktur Ditemukan ✅

```javascript
const materials = ['Ferit', 'Austenit', 'Martensit', 'Perlit', 'Bainit'];
const result = analyzeMicrostructures(materials, 'Martensit');

console.log(result);
```

**Output:**
```
Structure 'Martensit' found at position 3. Total structures examined: 5.
```

---

### Contoh 2: Struktur Tidak Ditemukan ❌

```javascript
const materials = ['Ferit', 'Austenit', 'Martensit', 'Perlit', 'Bainit'];
const result = analyzeMicrostructures(materials, 'Sementit');

console.log(result);
```

**Output:**
```
Structure 'Sementit' not found. Total structures examined: 5.
```

---

### Contoh 3: Array dengan Angka 🔢

```javascript
const codes = [101, 202, 303, 404, 505];
const result = analyzeMicrostructures(codes, 303);

console.log(result);
```

**Output:**
```
Structure '303' found at position 3. Total structures examined: 5.
```

---

### Contoh 4: Array Kosong 📭

```javascript
const empty = [];
const result = analyzeMicrostructures(empty, 'Test');

console.log(result);
```

**Output:**
```
Structure 'Test' not found. Total structures examined: 0.
```

---

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** untuk string (membedakan huruf besar dan kecil)
- Pencarian menggunakan **strict equality** (`===`), sehingga tipe data harus sama persis
- Jika ada duplikat dalam array, fungsi akan mengembalikan posisi kemunculan **pertama**
- Posisi yang dikembalikan dimulai dari **1** (bukan 0 seperti indeks array)

---

## 🚀 Tips Penggunaan

**Untuk Pemula:**
- Pastikan array `structures` sudah terisi sebelum memanggil fungsi
- Perhatikan tipe data `target` harus sama dengan tipe data elemen dalam array
- Gunakan fungsi ini untuk validasi data sebelum processing lebih lanjut

**Contoh Validasi:**
```javascript
const structures = ['A', 'B', 'C'];
const target = 'B';
const result = analyzeMicrostructures(structures, target);

if (result.includes('found')) {
  console.log('✅ Struktur valid, lanjut proses...');
} else {
  console.log('❌ Struktur tidak valid!');
}
```

---

**Dibuat dengan ❤️ untuk memudahkan analisis struktur mikro**
