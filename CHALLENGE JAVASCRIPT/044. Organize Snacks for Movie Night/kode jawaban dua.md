# 🍿 Dokumentasi Fungsi `arrangeMovieNight`

## 📋 Deskripsi Fungsi

Fungsi `arrangeMovieNight` adalah sebuah fungsi JavaScript yang digunakan untuk mengatur camilan (snacks) untuk malam menonton film. Fungsi ini mengambil sebagian camilan dari array berdasarkan indeks yang ditentukan, kemudian mengurutkannya secara alfabetis.

## 🔧 Kode Fungsi

```javascript
function arrangeMovieNight(snacks, start, end) {
    // Menangani kasus edge untuk array kosong atau parameter yang tidak valid
    if (!snacks || snacks.length === 0) {
        return [];
    }
    
    // Menyesuaikan start dan end agar sesuai dengan batas array
    start = Math.max(0, Math.min(start, snacks.length));
    end = Math.max(start, Math.min(end, snacks.length));
    
    // Mengekstrak sebagian dari array snacks menggunakan slice
    const selectedSnacks = snacks.slice(start, end);
    
    // Mengurutkan bagian yang diekstrak secara alfabetis
    const sortedSnacks = selectedSnacks.sort();
    
    return sortedSnacks;
}
```

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `snacks` | Array | Array berisi daftar camilan (string) yang akan diatur |
| `start` | Number | Indeks awal untuk memilih camilan (inclusive) |
| `end` | Number | Indeks akhir untuk memilih camilan (exclusive) |

### 📌 Penjelasan Parameter

- **`snacks`**: Array yang berisi nama-nama camilan dalam bentuk string
- **`start`**: Posisi mulai pengambilan camilan (dimulai dari 0)
- **`end`**: Posisi akhir pengambilan camilan (tidak termasuk indeks ini)

## 🎯 Nilai Kembalian

Fungsi ini mengembalikan array baru yang berisi camilan yang telah diurutkan secara alfabetis dari bagian yang dipilih.

## 🔄 Cara Kerja Fungsi

1. **Validasi Input**: Memeriksa apakah array `snacks` valid dan tidak kosong
2. **Penyesuaian Indeks**: Memastikan `start` dan `end` berada dalam rentang yang valid
3. **Ekstraksi Data**: Mengambil sebagian array menggunakan method `slice()`
4. **Pengurutan**: Mengurutkan camilan secara alfabetis menggunakan method `sort()`
5. **Mengembalikan Hasil**: Mengembalikan array yang sudah diurutkan

## 📊 Contoh Penggunaan

### Contoh 1: Penggunaan Normal
```javascript
const snacks = ["Popcorn", "Nachos", "Candy", "Soda", "Chips"];
const result = arrangeMovieNight(snacks, 1, 4);
console.log(result);
// Output: ["Candy", "Nachos", "Soda"]
```

### Contoh 2: Menggunakan Seluruh Array
```javascript
const snacks = ["Pizza", "Ice Cream", "Cookies"];
const result = arrangeMovieNight(snacks, 0, 3);
console.log(result);
// Output: ["Cookies", "Ice Cream", "Pizza"]
```

### Contoh 3: Indeks Melebihi Batas
```javascript
const snacks = ["Chocolate", "Pretzels"];
const result = arrangeMovieNight(snacks, 0, 10);
console.log(result);
// Output: ["Chocolate", "Pretzels"]
```

### Contoh 4: Array Kosong
```javascript
const snacks = [];
const result = arrangeMovieNight(snacks, 0, 5);
console.log(result);
// Output: []
```

## 📋 Tabel Contoh Input/Output

| Input Snacks | Start | End | Output |
|--------------|-------|-----|--------|
| `["Popcorn", "Nachos", "Candy"]` | 0 | 2 | `["Nachos", "Popcorn"]` |
| `["Soda", "Chips", "Pizza", "Cookies"]` | 1 | 3 | `["Chips", "Pizza"]` |
| `["Apple", "Banana", "Cherry"]` | 0 | 3 | `["Apple", "Banana", "Cherry"]` |
| `[]` | 0 | 5 | `[]` |

## ⚠️ Catatan Penting

- Fungsi ini tidak mengubah array asli (`snacks`), melainkan membuat array baru
- Jika `start` atau `end` melebihi panjang array, fungsi akan otomatis menyesuaikan ke batas yang valid
- Pengurutan dilakukan secara alfabetis (case-sensitive)
- Jika array kosong atau parameter `snacks` tidak valid, fungsi akan mengembalikan array kosong

## 🚀 Tips Penggunaan

1. Pastikan array `snacks` berisi string untuk hasil pengurutan yang optimal
2. Gunakan indeks yang valid untuk menghindari hasil yang tidak diinginkan
3. Fungsi ini sangat berguna untuk mengatur daftar camilan berdasarkan preferensi urutan tertentu
