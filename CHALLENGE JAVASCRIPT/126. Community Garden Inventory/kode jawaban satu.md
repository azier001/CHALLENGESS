# 🌱 Dokumentasi Fungsi `gardenInventory`

## 📝 Deskripsi

Fungsi `gardenInventory` digunakan untuk mengelola inventori tanaman di kebun. Fungsi ini akan membandingkan daftar tanaman yang sudah ada dengan tanaman baru yang akan ditambahkan, kemudian mengkategorikan tanaman-tanaman tersebut menjadi:

- **Tanaman yang sudah ada** (duplikat)
- **Tanaman baru** (belum ada di kebun)
- **Total tanaman unik** di kebun setelah penambahan

Fungsi ini sangat berguna untuk menghindari pencatatan duplikat dan mengetahui berapa banyak varietas tanaman yang dimiliki. Versi ini menggunakan **Set** untuk performa yang lebih optimal.

---

## 🎯 Parameter

Fungsi ini menerima 2 parameter:

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `currentPlants` | Array | Daftar tanaman yang sudah ada di kebun saat ini |
| `newPlants` | Array | Daftar tanaman baru yang akan ditambahkan ke kebun |

---

## 📤 Return Value

Fungsi ini mengembalikan sebuah **objek** dengan struktur sebagai berikut:

| Property | Tipe | Deskripsi |
|----------|------|-----------|
| `existingPlants` | Array | Daftar tanaman dari `newPlants` yang sudah ada di `currentPlants` (termasuk duplikat) |
| `newPlants` | Array | Daftar tanaman dari `newPlants` yang belum ada di `currentPlants` |
| `totalPlants` | Number | Jumlah total tanaman unik setelah penggabungan |

---

## 💻 Kode Fungsi

```javascript
function gardenInventory(currentPlants, newPlants) {
  const existingPlants = [];
  const uniqueNewPlants = [];
  
  // Buat Set dari tanaman yang sudah ada untuk pencarian lebih cepat
  const allPlants = new Set(currentPlants);
  
  // Iterasi setiap tanaman baru
  for (const plant of newPlants) {
    
    // Cek apakah tanaman sudah ada di Set
    if (allPlants.has(plant)) {
      // Jika sudah ada, masukkan ke existingPlants
      existingPlants.push(plant);
    } else {
      // Jika belum ada, masukkan ke uniqueNewPlants
      uniqueNewPlants.push(plant);
      
      // Tambahkan tanaman baru ke Set
      allPlants.add(plant);
    }
  }
  
  return {
    existingPlants: existingPlants,
    newPlants: uniqueNewPlants,
    totalPlants: allPlants.size
  };
}
```

---

## 🔍 Cara Kerja

1. **Inisialisasi**: Membuat dua array kosong (`existingPlants` dan `uniqueNewPlants`) dan satu Set yang berisi semua tanaman yang sudah ada.

2. **Menggunakan Set**: Set digunakan karena operasi pencarian (`.has()`) lebih cepat dibanding array, terutama untuk data yang banyak.

3. **Iterasi Tanaman Baru**: Menggunakan `for...of` loop yang lebih modern untuk memeriksa setiap tanaman di `newPlants`.

4. **Pengecekan dengan Set**: Untuk setiap tanaman baru:
   - Jika **sudah ada** di Set: Tambahkan ke `existingPlants` (duplikat dicatat)
   - Jika **belum ada** di Set: Tambahkan ke `uniqueNewPlants` dan masukkan ke Set

5. **Menghitung Total**: Menggunakan `allPlants.size` untuk mendapatkan jumlah total tanaman unik dengan cepat.

6. **Return**: Mengembalikan objek dengan informasi lengkap tentang inventori tanaman.

---

## 🆚 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Lama | Versi Baru (Set) |
|-------|------------|------------------|
| **Struktur Data** | Array only | Array + Set |
| **Pencarian** | Nested loop O(n²) | Set.has() O(1) |
| **Performa** | Lambat untuk data besar | Lebih cepat |
| **Loop** | `for` dengan index | `for...of` (lebih modern) |
| **Duplikat di existingPlants** | Tidak ada | Ada (sesuai input) |

---

## 📋 Contoh Penggunaan

### Contoh 1: Menambahkan Tanaman Campuran

```javascript
const tanamanSekarang = ['Mawar', 'Melati', 'Anggrek'];
const tanamanBaru = ['Melati', 'Kaktus', 'Mawar', 'Lily'];

const hasil = gardenInventory(tanamanSekarang, tanamanBaru);
console.log(hasil);
```

**Output:**
```javascript
{
  existingPlants: ['Melati', 'Mawar'],
  newPlants: ['Kaktus', 'Lily'],
  totalPlants: 5
}
```

**Penjelasan:**
- `Melati` dan `Mawar` sudah ada di kebun → masuk `existingPlants`
- `Kaktus` dan `Lily` belum ada di kebun → masuk `newPlants`
- Total tanaman unik: Mawar, Melati, Anggrek, Kaktus, Lily = **5 tanaman**

---

### Contoh 2: Tanaman Baru dengan Duplikat

```javascript
const tanamanSekarang = ['Mawar', 'Melati'];
const tanamanBaru = ['Mawar', 'Mawar', 'Kaktus'];

const hasil = gardenInventory(tanamanSekarang, tanamanBaru);
console.log(hasil);
```

**Output:**
```javascript
{
  existingPlants: ['Mawar', 'Mawar'],
  newPlants: ['Kaktus'],
  totalPlants: 3
}
```

**Penjelasan:**
- `Mawar` muncul 2 kali dan keduanya sudah ada → masuk `existingPlants` 2 kali
- `Kaktus` belum ada → masuk `newPlants`
- Total tanaman unik tetap: Mawar, Melati, Kaktus = **3 tanaman**

---

### Contoh 3: Semua Tanaman Baru

```javascript
const tanamanSekarang = ['Mawar', 'Melati'];
const tanamanBaru = ['Kaktus', 'Lily', 'Bambu'];

const hasil = gardenInventory(tanamanSekarang, tanamanBaru);
console.log(hasil);
```

**Output:**
```javascript
{
  existingPlants: [],
  newPlants: ['Kaktus', 'Lily', 'Bambu'],
  totalPlants: 5
}
```

---

### Contoh 4: Semua Tanaman Sudah Ada

```javascript
const tanamanSekarang = ['Mawar', 'Melati', 'Anggrek'];
const tanamanBaru = ['Mawar', 'Melati'];

const hasil = gardenInventory(tanamanSekarang, tanamanBaru);
console.log(hasil);
```

**Output:**
```javascript
{
  existingPlants: ['Mawar', 'Melati'],
  newPlants: [],
  totalPlants: 3
}
```

---

## ⚡ Keunggulan Menggunakan Set

### 1. **Performa Lebih Cepat**
- Pencarian dengan `Set.has()` memiliki kompleksitas **O(1)** (konstan)
- Array `includes()` memiliki kompleksitas **O(n)** (linear)
- Untuk 1000 tanaman, Set bisa **ratusan kali lebih cepat**!

### 2. **Kode Lebih Bersih**
- Tidak perlu nested loop
- Lebih mudah dibaca dan dipahami
- Loop `for...of` lebih modern dan elegan

### 3. **Penghitungan Total Otomatis**
- `Set.size` langsung memberikan jumlah elemen unik
- Tidak perlu iterasi tambahan untuk menghitung

---

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive**, artinya 'Mawar' dan 'mawar' dianggap berbeda
- **Duplikat dalam `newPlants` akan dicatat** di `existingPlants` jika tanaman tersebut sudah ada
- Array kosong `[]` pada parameter akan menghasilkan hasil yang valid
- Set hanya menyimpan nilai unik, cocok untuk tracking tanaman yang sudah ada
- Fungsi ini lebih efisien untuk dataset besar

---

## 🎓 Tips untuk Pemula

**Kapan menggunakan fungsi ini?**
- Saat ingin menambahkan tanaman baru ke kebun dan ingin tahu mana yang duplikat
- Saat perlu melacak total varietas tanaman yang dimiliki
- Saat ingin menghindari pencatatan tanaman yang sama dua kali
- Saat bekerja dengan data dalam jumlah besar (lebih dari 100 item)

**Kenapa Set lebih baik?**
Bayangkan Anda punya 1000 tanaman dan ingin mengecek apakah "Mawar" ada di daftar:
- **Dengan Array**: Harus mengecek satu-satu dari awal sampai ketemu (bisa 1000 kali pengecekan)
- **Dengan Set**: Langsung tahu jawabannya dalam 1 kali pengecekan!

---

## 📚 Istilah Teknis

| Istilah | Penjelasan |
|---------|------------|
| **Array** | Kumpulan data yang disimpan dalam satu variabel, bisa ada duplikat |
| **Set** | Kumpulan data unik (tidak ada duplikat), dengan pencarian super cepat |
| **for...of** | Loop modern untuk iterasi elemen array atau Set |
| **.has()** | Method Set untuk mengecek apakah suatu nilai ada (lebih cepat dari includes) |
| **.add()** | Method Set untuk menambahkan elemen baru |
| **.size** | Property Set untuk mendapatkan jumlah elemen unik |
| **O(1)** | Kompleksitas waktu konstan - selalu cepat tidak peduli ukuran data |
| **O(n)** | Kompleksitas waktu linear - semakin besar data, semakin lama prosesnya |

---

## 🎯 Ringkasan

Fungsi `gardenInventory` versi ini adalah solusi **modern dan efisien** untuk mengelola inventori tanaman. Dengan menggunakan Set, fungsi ini:

✅ Lebih cepat untuk data besar  
✅ Kode lebih bersih dan mudah dipahami  
✅ Menggunakan fitur JavaScript modern  
✅ Lebih hemat memori untuk operasi pencarian  

**Dibuat dengan ❤️ untuk membantu pengelolaan kebun digital Anda!** 🌺
