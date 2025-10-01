# 🌿 Dokumentasi Fungsi `findRarePlant`

## 📋 Deskripsi

Fungsi `findRarePlant` digunakan untuk mencari tanaman langka dalam sebuah daftar nama tanaman. Fungsi ini memiliki keunikan karena dapat mendeteksi nama tanaman baik dalam bentuk normal maupun terbalik (reversed). Fungsi akan memeriksa setiap nama tanaman dalam daftar, membandingkannya dengan nama yang dicari dalam bentuk normal, atau membalikkan nama dalam daftar untuk dicocokkan. Jika tanaman ditemukan, fungsi akan mengembalikan indeks posisinya dalam array. Jika tidak ditemukan, fungsi akan mengembalikan `-1`.

---

## 🎯 Kegunaan

- ✅ Mencari posisi tanaman langka dalam daftar
- ✅ Mendeteksi nama tanaman dalam bentuk normal
- ✅ Mendeteksi nama tanaman yang tersimpan dalam bentuk terbalik
- ✅ Cocok untuk sistem inventaris atau database tanaman dengan encoding khusus

---

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `plantNames` | Array | Daftar nama-nama tanaman yang akan dicari (dapat berisi nama normal atau terbalik) |
| `rarePlant` | String | Nama tanaman langka yang ingin dicari (dalam bentuk normal) |

---

## 🔄 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Number` | Indeks posisi tanaman jika ditemukan (0, 1, 2, ...) |
| `Number` | `-1` jika tanaman tidak ditemukan dalam daftar |

---

## 💻 Source Code

```javascript
function findRarePlant(plantNames, rarePlant) {
  
  // Fungsi helper untuk membalikkan string
  function reverseString(str) {
    return str.split('').reverse().join('');
  }
  
  // Loop melalui setiap nama tanaman dalam daftar
  for (let i = 0; i < plantNames.length; i++) {
    
    // Cek apakah nama tanaman cocok dengan yang dicari (normal)
    // ATAU versi terbalik dari nama tanaman cocok dengan yang dicari
    if (plantNames[i] === rarePlant || reverseString(plantNames[i]) === rarePlant) {
      return i; // Kembalikan indeks jika ditemukan
    }
  }
  
  // Kembalikan -1 jika tanaman tidak ditemukan
  return -1;
}
```

---

## 📚 Cara Kerja

1. **Fungsi Helper `reverseString`**: Mengubah string menjadi bentuk terbalik dengan cara:
   - Memecah string menjadi array karakter (`split('')`)
   - Membalikkan urutan array (`reverse()`)
   - Menggabungkan kembali menjadi string (`join('')`)

2. **Pencarian Linear**: Melakukan iterasi pada setiap elemen dalam array `plantNames`

3. **Pencocokan Ganda**: Untuk setiap nama tanaman dalam daftar, fungsi melakukan dua pengecekan:
   - Apakah nama tanaman **sama persis** dengan `rarePlant`?
   - Apakah nama tanaman **dalam bentuk terbalik** sama dengan `rarePlant`?

4. **Return Cepat**: Segera mengembalikan indeks ketika nama cocok ditemukan

5. **Return Default**: Mengembalikan `-1` jika tidak ada kecocokan ditemukan

---

## 🔄 Perbedaan Logika

**Penting**: Fungsi ini membalikkan **setiap nama dalam daftar** untuk dibandingkan dengan nama yang dicari (normal), bukan membalikkan nama yang dicari.

| Yang Dibalik | Contoh |
|--------------|--------|
| Nama dalam daftar | `reverseString(plantNames[i])` |
| Yang dicari tetap normal | `rarePlant` |

---

## 🎨 Contoh Penggunaan

### Contoh 1: Tanaman Ditemukan (Normal)
```javascript
const plants = ['Mawar', 'Melati', 'Anggrek', 'Tulip'];
const result = findRarePlant(plants, 'Anggrek');

console.log(result);
// Output: 2
```

**Penjelasan**: Tanaman "Anggrek" ditemukan pada indeks ke-2 dalam array (pencocokan normal).

---

### Contoh 2: Tanaman Ditemukan (Terbalik di Database)
```javascript
const plants = ['Mawar', 'italeM', 'Anggrek', 'Tulip'];
const result = findRarePlant(plants, 'Melati');

console.log(result);
// Output: 1
```

**Penjelasan**: Database menyimpan "italeM" (Melati terbalik) pada indeks ke-1. Fungsi membalikkan "italeM" menjadi "Melati" dan menemukan kecocokan.

---

### Contoh 3: Tanaman Tidak Ditemukan
```javascript
const plants = ['Mawar', 'Melati', 'Anggrek', 'Tulip'];
const result = findRarePlant(plants, 'Kaktus');

console.log(result);
// Output: -1
```

**Penjelasan**: Tanaman "Kaktus" tidak ditemukan dalam daftar, baik dalam bentuk normal maupun terbalik.

---

### Contoh 4: Palindrome
```javascript
const plants = ['Mawar', 'civic', 'Anggrek', 'Tulip'];
const result = findRarePlant(plants, 'civic');

console.log(result);
// Output: 1
```

**Penjelasan**: Kata "civic" adalah palindrome (sama jika dibaca maju atau mundur), sehingga akan cocok baik secara normal maupun terbalik.

---

### Contoh 5: Database dengan Encoding Terbalik
```javascript
const plants = ['rawaM', 'italeM', 'kerggnA', 'piluT'];
const result = findRarePlant(plants, 'Anggrek');

console.log(result);
// Output: 2
```

**Penjelasan**: Seluruh database menyimpan nama terbalik. Fungsi membalikkan "kerggnA" menjadi "Anggrek" dan menemukan kecocokan pada indeks ke-2.

---

## 📊 Tabel Contoh Pembalikan

| Nama di Database | Dibalik Menjadi | Cocok dengan Pencarian |
|------------------|-----------------|------------------------|
| Anggrek | kerggnA | ❌ (jika cari "Melati") |
| italeM | Melati | ✅ (jika cari "Melati") |
| Mawar | rawaM | ❌ (jika cari "Melati") |
| civic | civic | ✅ (jika cari "civic") |
| rawaM | Mawar | ✅ (jika cari "Mawar") |

---

## ⚙️ Algoritma Visual

```
Input: plantNames = ['rawaM', 'Melati', 'kerggnA'], rarePlant = 'Anggrek'

Iterasi 1 (i=0):
  plantNames[0] = 'rawaM'
  ❌ 'rawaM' === 'Anggrek'? Tidak
  ❌ reverse('rawaM') = 'Mawar' === 'Anggrek'? Tidak
  
Iterasi 2 (i=1):
  plantNames[1] = 'Melati'
  ❌ 'Melati' === 'Anggrek'? Tidak
  ❌ reverse('Melati') = 'italeM' === 'Anggrek'? Tidak
  
Iterasi 3 (i=2):
  plantNames[2] = 'kerggnA'
  ❌ 'kerggnA' === 'Anggrek'? Tidak
  ✅ reverse('kerggnA') = 'Anggrek' === 'Anggrek'? YA!
  
Return: 2
```

---

## ⚠️ Catatan Penting

- 🔤 Fungsi ini **case-sensitive** (membedakan huruf besar dan kecil)
- 🔍 Pencarian dilakukan secara berurutan dari indeks 0
- 🎯 Jika ada duplikat, fungsi akan mengembalikan indeks kemunculan pertama
- ⏱️ Kompleksitas waktu: O(n × m) dimana n = jumlah elemen, m = panjang rata-rata string
- 🔄 Fungsi ini membalikkan **nama di database**, bukan nama yang dicari
- 💡 Cocok untuk database yang mengenkripsi/encode nama dengan pembalikan string

---

## 🚀 Tips Penggunaan

1. Pastikan parameter `plantNames` berupa array yang valid
2. Parameter `rarePlant` harus berupa string dalam bentuk normal
3. Gunakan return value `-1` untuk mengecek apakah tanaman tidak ditemukan
4. Cocok untuk sistem dengan encoding/enkripsi sederhana menggunakan pembalikan string
5. Dapat digunakan untuk database dengan data yang tersimpan terbalik atau normal

---

## 🆚 Perbandingan dengan Versi Lain

| Aspek | Versi Ini | Versi Alternatif |
|-------|-----------|------------------|
| Yang dibalik | Nama dalam database | Nama yang dicari |
| Use case | Database dengan encoding terbalik | Pencarian fleksibel |
| Performa | Memanggil reverse setiap iterasi | Memanggil reverse sekali |
| Efisiensi | Kurang efisien (O(n×m)) | Lebih efisien (O(n)) |

---

**Dibuat dengan 💚 untuk pecinta tanaman dan database unik**
