# 🌊 Dokumentasi Fungsi `seawaySightseeing`

## 📋 Deskripsi

Fungsi `seawaySightseeing` digunakan untuk menghitung berapa kali setiap pemandangan (sight) muncul dalam sebuah array. Fungsi ini sangat berguna ketika Anda ingin mengetahui frekuensi kemunculan setiap elemen dalam sebuah daftar.

Bayangkan Anda sedang berlayar di laut dan mencatat semua pemandangan yang Anda lihat. Fungsi ini akan membantu Anda menghitung berapa kali Anda melihat setiap jenis pemandangan tersebut.

---

## 🔧 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `sights` | Array | ✅ Ya | Array yang berisi daftar pemandangan. Bisa berisi string, angka, atau tipe data lainnya |

---

## 📤 Return Value

Fungsi ini mengembalikan sebuah **objek** yang berisi:
- **Key (Kunci)**: Nama pemandangan
- **Value (Nilai)**: Jumlah kemunculan pemandangan tersebut

---

## 💻 Source Code

```javascript
function seawaySightseeing(sights) {
  // Objek untuk menyimpan jumlah kemunculan setiap pemandangan
  const sightCounts = {};
  
  // Looping melalui setiap pemandangan dalam array menggunakan for...of
  for (const sight of sights) {
    
    // Jika pemandangan sudah ada di objek, tambahkan 1
    if (sight in sightCounts) {
      sightCounts[sight]++;
    } 
    // Jika pemandangan belum ada, inisialisasi dengan nilai 1
    else {
      sightCounts[sight] = 1;
    }
  }
  
  // Kembalikan objek yang berisi jumlah kemunculan setiap pemandangan
  return sightCounts;
}
```

---

## 📚 Cara Kerja

1. **Inisialisasi**: Membuat objek kosong `sightCounts` untuk menyimpan hasil perhitungan
2. **Iterasi**: Melakukan perulangan untuk setiap elemen dalam array `sights` menggunakan `for...of` loop
3. **Pengecekan**: 
   - Menggunakan operator `in` untuk mengecek apakah pemandangan sudah ada dalam objek
   - Jika sudah ada, tambahkan 1 ke nilai yang ada
   - Jika belum ada (pemandangan baru), set nilainya menjadi 1
4. **Return**: Mengembalikan objek hasil perhitungan

---

## 🎯 Contoh Penggunaan

### Contoh 1: Pemandangan Laut
```javascript
const pemandangan = ['pulau', 'kapal', 'pulau', 'ikan', 'kapal', 'pulau'];
const hasil = seawaySightseeing(pemandangan);

console.log(hasil);
```

**Output:**
```javascript
{
  pulau: 3,
  kapal: 2,
  ikan: 1
}
```

**Penjelasan:** Dalam perjalanan laut, kita melihat pulau sebanyak 3 kali, kapal 2 kali, dan ikan 1 kali.

---

### Contoh 2: Menggunakan Angka
```javascript
const angka = [1, 2, 3, 1, 2, 1, 4];
const hasil = seawaySightseeing(angka);

console.log(hasil);
```

**Output:**
```javascript
{
  1: 3,
  2: 2,
  3: 1,
  4: 1
}
```

**Penjelasan:** Angka 1 muncul 3 kali, angka 2 muncul 2 kali, sedangkan angka 3 dan 4 masing-masing muncul 1 kali.

---

### Contoh 3: Array Kosong
```javascript
const kosong = [];
const hasil = seawaySightseeing(kosong);

console.log(hasil);
```

**Output:**
```javascript
{}
```

**Penjelasan:** Jika tidak ada pemandangan yang terlihat (array kosong), hasilnya adalah objek kosong.

---

## 🔍 Perbedaan Teknik yang Digunakan

Fungsi ini menggunakan beberapa teknik modern JavaScript:

### 1. **`for...of` Loop**
```javascript
for (const sight of sights)
```
- Lebih sederhana dan mudah dibaca dibanding `for` tradisional
- Langsung mengakses nilai elemen, tidak perlu index
- Lebih aman dari kesalahan index

### 2. **Operator `in`**
```javascript
if (sight in sightCounts)
```
- Mengecek apakah properti ada dalam objek
- Lebih eksplisit daripada pengecekan truthiness
- Lebih jelas maksudnya untuk pengecekan keberadaan key

---

## 💡 Tips Penggunaan

- ✅ Fungsi ini bekerja dengan berbagai tipe data (string, number, dll)
- ✅ Cocok untuk menghitung frekuensi data dalam survey atau statistik sederhana
- ✅ Dapat digunakan untuk menganalisis data berulang dalam aplikasi
- ✅ Menggunakan sintaks modern JavaScript yang lebih clean
- ⚠️ Perhatikan bahwa angka dan string akan dianggap berbeda (contoh: `1` berbeda dengan `"1"`)

---

## 🎓 Untuk Pemula

Jika Anda baru belajar programming, fungsi ini mengajarkan konsep penting:

1. **Object/Objek**: Struktur data yang menyimpan pasangan key-value
2. **for...of Loop**: Cara modern untuk mengulang setiap elemen dalam array
3. **Operator `in`**: Mengecek keberadaan properti dalam objek
4. **Conditional**: Penggunaan if-else untuk membuat keputusan
5. **Counting Algorithm**: Teknik dasar untuk menghitung frekuensi data

### 🆚 Perbandingan dengan Gaya Lama

| Gaya Lama | Gaya Modern (Ini) |
|-----------|-------------------|
| `for (let i = 0; i < arr.length; i++)` | `for (const item of arr)` |
| `if (obj[key])` | `if (key in obj)` |

Ini adalah pattern yang sangat umum digunakan dalam programming modern! 🚀
