# 🌊 Dokumentasi Fungsi `countRiverObstacles`

## 📋 Deskripsi

Fungsi `countRiverObstacles` digunakan untuk menghitung jumlah rintangan (obstacles) yang ada di dalam sungai. Fungsi ini akan menelusuri setiap elemen dalam array sungai dan menghitung berapa banyak rintangan yang ditemukan.

Rintangan direpresentasikan dengan angka `1`, sedangkan area yang aman/kosong direpresentasikan dengan angka `0`.

---

## 🎯 Kegunaan

Fungsi ini berguna untuk:
- ✅ Menghitung total rintangan dalam sebuah jalur sungai
- ✅ Menganalisis tingkat kesulitan navigasi sungai
- ✅ Membantu dalam perencanaan rute atau permainan berbasis sungai

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `river` | Array | Array yang berisi representasi sungai dengan angka `0` (aman) dan `1` (rintangan) |

---

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| Number | Jumlah total rintangan (angka `1`) yang ditemukan dalam array sungai |

---

## 🔤 Tabel Karakter

| Karakter | Nilai | Arti |
|----------|-------|------|
| Area Aman | `0` | Tidak ada rintangan, aman untuk dilalui |
| Rintangan | `1` | Ada rintangan, berbahaya untuk dilalui |

---

## 💻 Kode Fungsi

```javascript
function countRiverObstacles(river) {
  // Inisialisasi variabel untuk menyimpan jumlah rintangan
  let obstacleCount = 0;
  
  // Loop melalui setiap elemen dalam array sungai
  for (let i = 0; i < river.length; i++) {
    
    // Jika elemen bernilai 1 (rintangan), tambahkan counter
    if (river[i] === 1) {
      obstacleCount++;
    }
    
  }
  
  // Kembalikan total jumlah rintangan
  return obstacleCount;
}
```

---

## 📖 Cara Kerja

1. **Inisialisasi**: Fungsi membuat variabel `obstacleCount` dengan nilai awal `0`
2. **Iterasi**: Fungsi melakukan perulangan untuk setiap elemen dalam array `river`
3. **Pengecekan**: Di setiap iterasi, fungsi mengecek apakah nilai elemen sama dengan `1`
4. **Penghitungan**: Jika nilai adalah `1`, maka `obstacleCount` ditambah 1
5. **Return**: Setelah semua elemen diperiksa, fungsi mengembalikan total jumlah rintangan

---

## 🎮 Contoh Penggunaan

### Contoh 1: Sungai dengan Beberapa Rintangan
```javascript
const river1 = [0, 1, 0, 1, 1, 0, 1];
const result1 = countRiverObstacles(river1);
console.log(result1);
```

**Output:**
```
4
```

**Penjelasan:** Dalam array `[0, 1, 0, 1, 1, 0, 1]`, terdapat 4 rintangan (angka 1).

---

### Contoh 2: Sungai Tanpa Rintangan
```javascript
const river2 = [0, 0, 0, 0, 0];
const result2 = countRiverObstacles(river2);
console.log(result2);
```

**Output:**
```
0
```

**Penjelasan:** Tidak ada rintangan sama sekali, semua elemen bernilai 0.

---

### Contoh 3: Sungai Penuh Rintangan
```javascript
const river3 = [1, 1, 1, 1];
const result3 = countRiverObstacles(river3);
console.log(result3);
```

**Output:**
```
4
```

**Penjelasan:** Semua elemen adalah rintangan, sehingga totalnya 4.

---

### Contoh 4: Sungai Kosong
```javascript
const river4 = [];
const result4 = countRiverObstacles(river4);
console.log(result4);
```

**Output:**
```
0
```

**Penjelasan:** Array kosong tidak memiliki rintangan, sehingga hasilnya 0.

---

## ⚠️ Catatan Penting

- Array harus berisi angka `0` dan `1` saja untuk hasil yang akurat
- Fungsi tidak memvalidasi input, pastikan data yang diberikan sudah benar
- Kompleksitas waktu: **O(n)** dimana n adalah panjang array
- Kompleksitas ruang: **O(1)** karena hanya menggunakan satu variabel tambahan

---

## 🚀 Tips Penggunaan

- Gunakan fungsi ini untuk game atau simulasi yang melibatkan navigasi sungai
- Bisa dikombinasikan dengan fungsi lain untuk membuat sistem penilaian kesulitan
- Cocok untuk pemula yang belajar tentang array dan perulangan

---

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
