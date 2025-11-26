# 📋 Dokumentasi Fungsi `createObservationTags`

## 🎯 Deskripsi

Fungsi `createObservationTags` digunakan untuk membuat tag observasi dari daftar nama makhluk hidup. Fungsi ini akan mengambil 4 karakter pertama dari setiap nama makhluk dan mengubahnya menjadi huruf kapital (uppercase).

Fungsi ini sangat berguna untuk:
- Membuat kode identifikasi singkat
- Membuat label atau tag untuk sistem katalog
- Menyederhanakan nama panjang menjadi format yang lebih ringkas

---

## 📝 Sintaks

```javascript
createObservationTags(creatures)
```

---

## 🔧 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `creatures` | Array | ✅ Ya | Array yang berisi daftar nama makhluk hidup (string) |

### Detail Parameter:
- **creatures**: Array of strings - Setiap elemen array harus berupa string yang merepresentasikan nama makhluk hidup

---

## 🔄 Return Value

| Tipe | Deskripsi |
|------|-----------|
| Array | Array baru yang berisi tag observasi (4 karakter pertama dalam huruf kapital) |

---

## 💻 Kode Fungsi

```javascript
function createObservationTags(creatures) {
    // Melakukan iterasi pada setiap makhluk dalam array
    return creatures.map(creature => 
        // Mengambil 4 karakter pertama dan mengubahnya menjadi huruf kapital
        creature.slice(0, 4).toUpperCase()
    );
}
```

---

## 📊 Cara Kerja

1. **Input**: Menerima array yang berisi nama-nama makhluk
2. **Proses**: 
   - Menggunakan method `map()` untuk iterasi setiap elemen
   - Method `slice(0, 4)` mengambil 4 karakter pertama
   - Method `toUpperCase()` mengubah karakter menjadi huruf kapital
3. **Output**: Mengembalikan array baru dengan tag observasi

---

## 🎨 Contoh Penggunaan

### Contoh 1: Nama Hewan

```javascript
const animals = ['elephant', 'tiger', 'lion', 'giraffe'];
const tags = createObservationTags(animals);

console.log(tags);
// Output: ['ELEP', 'TIGE', 'LION', 'GIRA']
```

### Contoh 2: Nama Tumbuhan

```javascript
const plants = ['rose', 'tulip', 'orchid', 'sunflower'];
const tags = createObservationTags(plants);

console.log(tags);
// Output: ['ROSE', 'TULI', 'ORCH', 'SUNF']
```

### Contoh 3: Nama dengan Panjang Berbeda

```javascript
const creatures = ['cat', 'butterfly', 'ant', 'crocodile'];
const tags = createObservationTags(creatures);

console.log(tags);
// Output: ['CAT', 'BUTT', 'ANT', 'CROC']
```

---

## 📌 Catatan Penting

- ⚠️ Jika nama makhluk memiliki kurang dari 4 karakter, fungsi akan mengambil karakter yang ada saja
- ⚠️ Fungsi ini tidak mengubah array original, tetapi membuat array baru
- ⚠️ Pastikan input adalah array of strings untuk menghindari error

---

## 🔍 Tabel Contoh Konversi

| Input | Proses | Output |
|-------|--------|--------|
| `"elephant"` | Ambil 4 huruf pertama → kapital | `"ELEP"` |
| `"dog"` | Ambil 3 huruf (kurang dari 4) → kapital | `"DOG"` |
| `"butterfly"` | Ambil 4 huruf pertama → kapital | `"BUTT"` |
| `"bee"` | Ambil 3 huruf (kurang dari 4) → kapital | `"BEE"` |

---

## 🚀 Tips Penggunaan

1. **Gunakan untuk katalog**: Buat sistem kode unik untuk database makhluk hidup
2. **Kombinasikan dengan nomor**: Tambahkan nomor urut untuk membuat ID lengkap
3. **Filter data**: Gunakan tag untuk pengelompokan dan pencarian data

---

## 📚 Referensi Method JavaScript

- [`Array.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) - Membuat array baru dengan hasil pemanggilan fungsi
- [`String.slice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice) - Mengekstrak bagian dari string
- [`String.toUpperCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) - Mengubah string menjadi huruf kapital

---

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
