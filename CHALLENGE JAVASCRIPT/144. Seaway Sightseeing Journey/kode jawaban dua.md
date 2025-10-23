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
  
  // Looping melalui setiap pemandangan dalam array
  for (let i = 0; i < sights.length; i++) {
    const sight = sights[i];
    
    // Jika pemandangan sudah ada di objek, tambahkan 1
    if (sightCounts[sight]) {
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
2. **Iterasi**: Melakukan perulangan untuk setiap elemen dalam array `sights`
3. **Pengecekan**: 
   - Jika pemandangan sudah pernah dihitung sebelumnya, tambahkan 1 ke nilai yang ada
   - Jika pemandangan baru pertama kali muncul, set nilainya menjadi 1
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

## 💡 Tips Penggunaan

- ✅ Fungsi ini bekerja dengan berbagai tipe data (string, number, dll)
- ✅ Cocok untuk menghitung frekuensi data dalam survey atau statistik sederhana
- ✅ Dapat digunakan untuk menganalisis data berulang dalam aplikasi
- ⚠️ Perhatikan bahwa angka dan string akan dianggap berbeda (contoh: `1` berbeda dengan `"1"`)

---

## 🎓 Untuk Pemula

Jika Anda baru belajar programming, fungsi ini mengajarkan konsep penting:

1. **Object/Objek**: Struktur data yang menyimpan pasangan key-value
2. **Looping**: Cara mengulang setiap elemen dalam array
3. **Conditional**: Penggunaan if-else untuk membuat keputusan
4. **Counting Algorithm**: Teknik dasar untuk menghitung frekuensi data

Ini adalah pattern yang sangat umum digunakan dalam programming! 🚀
