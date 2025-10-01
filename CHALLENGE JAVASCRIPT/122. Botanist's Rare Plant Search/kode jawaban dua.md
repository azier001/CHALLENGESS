# 🌿 Dokumentasi Fungsi `findRarePlant`

## 📋 Deskripsi

Fungsi `findRarePlant` digunakan untuk mencari tanaman langka dalam sebuah daftar nama tanaman. Fungsi ini memiliki keunikan karena dapat mendeteksi nama tanaman baik dalam bentuk normal maupun terbalik (reversed). Jika tanaman ditemukan, fungsi akan mengembalikan indeks posisinya dalam array. Jika tidak ditemukan, fungsi akan mengembalikan `-1`.

---

## 🎯 Kegunaan

- ✅ Mencari posisi tanaman langka dalam daftar
- ✅ Mendeteksi nama tanaman dalam bentuk normal
- ✅ Mendeteksi nama tanaman dalam bentuk terbalik
- ✅ Cocok untuk sistem inventaris atau database tanaman

---

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `plantNames` | Array | Daftar nama-nama tanaman yang akan dicari |
| `rarePlant` | String | Nama tanaman langka yang ingin dicari |

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
    
    // Buat versi terbalik dari nama tanaman langka
    const reversedRarePlant = reverseString(rarePlant);
    
    // Loop melalui setiap nama tanaman dalam daftar
    for (let i = 0; i < plantNames.length; i++) {
        
        // Cek apakah nama tanaman cocok dengan versi normal atau terbalik
        if (plantNames[i] === rarePlant || plantNames[i] === reversedRarePlant) {
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

2. **Membuat Versi Terbalik**: Fungsi membuat versi terbalik dari nama tanaman langka yang dicari

3. **Pencarian Linear**: Melakukan iterasi pada setiap elemen dalam array `plantNames`

4. **Pencocokan Ganda**: Membandingkan setiap nama tanaman dengan:
   - Versi normal dari `rarePlant`
   - Versi terbalik dari `rarePlant`

5. **Return**: Mengembalikan indeks jika ditemukan, atau `-1` jika tidak ada

---

## 🎨 Contoh Penggunaan

### Contoh 1: Tanaman Ditemukan (Normal)
```javascript
const plants = ['Mawar', 'Melati', 'Anggrek', 'Tulip'];
const result = findRarePlant(plants, 'Anggrek');

console.log(result);
// Output: 2
```

**Penjelasan**: Tanaman "Anggrek" ditemukan pada indeks ke-2 dalam array.

---

### Contoh 2: Tanaman Ditemukan (Terbalik)
```javascript
const plants = ['Mawar', 'tileM', 'Anggrek', 'Tulip'];
const result = findRarePlant(plants, 'Melati');

console.log(result);
// Output: 1
```

**Penjelasan**: Meskipun yang dicari adalah "Melati", fungsi menemukan "tileM" (Melati terbalik) pada indeks ke-1.

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

**Penjelasan**: Kata "civic" adalah palindrome (sama jika dibaca maju atau mundur), sehingga akan ditemukan pada indeks ke-1.

---

## 📊 Tabel Contoh Karakter Terbalik

| Input Normal | Output Terbalik |
|--------------|-----------------|
| Anggrek | kerggnA |
| Melati | italeM |
| Mawar | rawaM |
| Tulip | piluT |
| Kaktus | sutkaK |

---

## ⚠️ Catatan Penting

- 🔤 Fungsi ini **case-sensitive** (membedakan huruf besar dan kecil)
- 🔍 Pencarian dilakukan secara berurutan dari indeks 0
- 🎯 Jika ada duplikat, fungsi akan mengembalikan indeks kemunculan pertama
- ⏱️ Kompleksitas waktu: O(n) dimana n adalah jumlah elemen dalam array

---

## 🚀 Tips Penggunaan

1. Pastikan parameter `plantNames` berupa array yang valid
2. Parameter `rarePlant` harus berupa string
3. Gunakan return value `-1` untuk mengecek apakah tanaman tidak ditemukan
4. Cocok digunakan dalam aplikasi inventaris atau katalog tanaman

---

**Dibuat dengan 💚 untuk pecinta tanaman**
