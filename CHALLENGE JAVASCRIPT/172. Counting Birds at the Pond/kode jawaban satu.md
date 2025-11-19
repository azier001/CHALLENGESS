# 🦆 Dokumentasi Fungsi `countBirds`

## 📋 Deskripsi

Fungsi `countBirds` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung jumlah kemunculan setiap jenis burung dari hasil observasi di kolam. Fungsi ini akan mengambil data array yang berisi nama-nama burung, kemudian menghitung berapa kali setiap jenis burung muncul, dan mengembalikan hasilnya dalam bentuk objek.

---

## 🎯 Kegunaan

- Menghitung frekuensi kemunculan setiap jenis burung
- Mengubah data array menjadi ringkasan statistik
- Cocok untuk analisis data observasi burung
- Memudahkan identifikasi burung yang paling sering muncul

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `pondObservations` | Array | Array yang berisi nama-nama burung yang diamati di kolam. Setiap elemen adalah string yang merepresentasikan nama burung. |

---

## 📤 Output

Fungsi ini mengembalikan sebuah **objek** dengan struktur:
- **Key**: Nama burung (string)
- **Value**: Jumlah kemunculan burung tersebut (number)

---

## 💻 Kode Fungsi

```javascript
function countBirds(pondObservations) {
  
  // Menggunakan reduce untuk menghitung jumlah setiap burung
  // Mulai dengan objek kosong {}
  return pondObservations.reduce((count, bird) => {
    
    // Jika burung sudah ada di objek count, tambahkan 1
    // Jika belum ada, mulai dari 0 lalu tambahkan 1
    count[bird] = (count[bird] || 0) + 1;
    
    // Kembalikan objek count untuk iterasi berikutnya
    return count;
    
  }, {});
}
```

---

## 🔍 Penjelasan Cara Kerja

1. **Fungsi menerima array** `pondObservations` yang berisi nama-nama burung
2. **Menggunakan method `reduce()`** untuk mengiterasi setiap burung dalam array
3. **Untuk setiap burung:**
   - Cek apakah burung sudah ada dalam objek `count`
   - Jika sudah ada, tambahkan 1 ke jumlahnya
   - Jika belum ada, mulai dari 0 kemudian tambahkan 1
4. **Mengembalikan objek** yang berisi ringkasan jumlah setiap burung

---

## 📊 Contoh Penggunaan

### Contoh 1: Observasi Sederhana

```javascript
const observations = ["bebek", "angsa", "bebek", "angsa", "bebek"];
const result = countBirds(observations);

console.log(result);
```

**Output:**
```javascript
{
  bebek: 3,
  angsa: 2
}
```

### Contoh 2: Berbagai Jenis Burung

```javascript
const observations = [
  "burung pipit", 
  "burung merpati", 
  "burung pipit", 
  "burung gagak", 
  "burung merpati", 
  "burung pipit"
];

const result = countBirds(observations);

console.log(result);
```

**Output:**
```javascript
{
  "burung pipit": 3,
  "burung merpati": 2,
  "burung gagak": 1
}
```

### Contoh 3: Array Kosong

```javascript
const observations = [];
const result = countBirds(observations);

console.log(result);
```

**Output:**
```javascript
{}
```

---

## 📚 Catatan Penting

- ✅ Fungsi ini **case-sensitive**, artinya "Bebek" dan "bebek" akan dihitung sebagai burung yang berbeda
- ✅ Fungsi dapat menangani array kosong dan akan mengembalikan objek kosong `{}`
- ✅ Nama burung dapat berupa string apa saja, termasuk yang mengandung spasi
- ✅ Tidak ada batasan jumlah jenis burung yang dapat dihitung

---

## 🎓 Konsep yang Digunakan

| Konsep | Penjelasan |
|--------|------------|
| **Array.reduce()** | Method untuk mengakumulasi nilai array menjadi single value (dalam kasus ini, objek) |
| **Object** | Struktur data key-value untuk menyimpan hasil penghitungan |
| **Logical OR (`\|\|`)** | Operator untuk memberikan nilai default jika nilai belum ada |
| **Bracket Notation** | Cara mengakses/membuat properti objek menggunakan `[]` |

---

## 🚀 Tips Penggunaan

1. **Normalisasi data** - Jika ingin menghitung tanpa memperhatikan huruf besar/kecil, convert dulu semua nama burung ke lowercase:
   ```javascript
   const normalizedObservations = observations.map(bird => bird.toLowerCase());
   const result = countBirds(normalizedObservations);
   ```

2. **Sorting hasil** - Untuk mengurutkan burung berdasarkan jumlah kemunculan:
   ```javascript
   const result = countBirds(observations);
   const sorted = Object.entries(result)
     .sort((a, b) => b[1] - a[1]);
   ```

3. **Validasi input** - Tambahkan pengecekan untuk memastikan input adalah array:
   ```javascript
   if (!Array.isArray(pondObservations)) {
     throw new Error("Input harus berupa array");
   }
   ```

---

## 📝 Lisensi & Kontributor

Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi `countBirds`.

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
