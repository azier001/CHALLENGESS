# 🌱 Dokumentasi Fungsi `gardenInventory`

## 📝 Deskripsi

Fungsi `gardenInventory` digunakan untuk mengelola inventori tanaman di kebun. Fungsi ini akan membandingkan daftar tanaman yang sudah ada dengan tanaman baru yang akan ditambahkan, kemudian mengkategorikan tanaman-tanaman tersebut menjadi:

- **Tanaman yang sudah ada** (duplikat)
- **Tanaman baru** (belum ada di kebun)
- **Total tanaman unik** di kebun setelah penambahan

Fungsi ini sangat berguna untuk menghindari pencatatan duplikat dan mengetahui berapa banyak varietas tanaman yang dimiliki.

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
| `existingPlants` | Array | Daftar tanaman dari `newPlants` yang sudah ada di `currentPlants` |
| `newPlants` | Array | Daftar tanaman dari `newPlants` yang belum ada di `currentPlants` |
| `totalPlants` | Number | Jumlah total tanaman unik setelah penggabungan |

---

## 💻 Kode Fungsi

```javascript
function gardenInventory(currentPlants, newPlants) {
  const existingPlants = [];
  const uniqueNewPlants = [];
  
  // Periksa setiap tanaman baru
  for (let i = 0; i < newPlants.length; i++) {
    let found = false;
    
    // Bandingkan dengan tanaman yang sudah ada
    for (let j = 0; j < currentPlants.length; j++) {
      if (newPlants[i] === currentPlants[j]) {
        found = true;
        
        // Tambahkan ke existingPlants jika belum ada di dalam array
        if (!existingPlants.includes(newPlants[i])) {
          existingPlants.push(newPlants[i]);
        }
        break;
      }
    }
    
    // Jika tidak ditemukan, berarti tanaman baru
    if (!found && !uniqueNewPlants.includes(newPlants[i])) {
      uniqueNewPlants.push(newPlants[i]);
    }
  }
  
  // Hitung total tanaman unik
  const allPlants = [...currentPlants];
  
  for (let i = 0; i < uniqueNewPlants.length; i++) {
    if (!allPlants.includes(uniqueNewPlants[i])) {
      allPlants.push(uniqueNewPlants[i]);
    }
  }
  
  return {
    existingPlants: existingPlants,
    newPlants: uniqueNewPlants,
    totalPlants: allPlants.length
  };
}
```

---

## 🔍 Cara Kerja

1. **Inisialisasi**: Membuat dua array kosong untuk menyimpan tanaman yang sudah ada dan tanaman baru yang unik.

2. **Iterasi Tanaman Baru**: Fungsi akan memeriksa setiap tanaman di `newPlants` satu per satu.

3. **Pengecekan Duplikat**: Untuk setiap tanaman baru, fungsi akan mengecek apakah tanaman tersebut sudah ada di `currentPlants`:
   - Jika **sudah ada**: Tambahkan ke `existingPlants` (hanya sekali, tidak ada duplikat)
   - Jika **belum ada**: Tambahkan ke `uniqueNewPlants`

4. **Menghitung Total**: Menggabungkan `currentPlants` dengan `uniqueNewPlants` untuk mendapatkan total tanaman unik.

5. **Return**: Mengembalikan objek dengan informasi lengkap tentang inventori tanaman.

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

### Contoh 2: Semua Tanaman Baru

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

### Contoh 3: Semua Tanaman Sudah Ada

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

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive**, artinya 'Mawar' dan 'mawar' dianggap berbeda
- Fungsi ini menghilangkan duplikat otomatis dalam hasil
- Array kosong `[]` pada parameter akan menghasilkan hasil yang valid
- Fungsi menggunakan perbandingan sederhana `===`, cocok untuk string dan number

---

## 🎓 Tips untuk Pemula

**Kapan menggunakan fungsi ini?**
- Saat ingin menambahkan tanaman baru ke kebun dan ingin tahu mana yang duplikat
- Saat perlu melacak total varietas tanaman yang dimiliki
- Saat ingin menghindari pencatatan tanaman yang sama dua kali

**Alternatif Modern:**
Fungsi ini bisa dioptimalkan menggunakan `Set` untuk performa lebih baik pada data yang besar, namun kode di atas lebih mudah dipahami untuk pemula.

---

## 📚 Istilah Teknis

| Istilah | Penjelasan |
|---------|------------|
| **Array** | Kumpulan data yang disimpan dalam satu variabel |
| **Loop** | Perulangan untuk memeriksa setiap elemen |
| **Includes** | Method untuk mengecek apakah suatu nilai ada di dalam array |
| **Spread Operator (...)** | Cara untuk menyalin semua elemen array |

---

**Dibuat dengan ❤️ untuk membantu pengelolaan kebun digital Anda!** 🌺
