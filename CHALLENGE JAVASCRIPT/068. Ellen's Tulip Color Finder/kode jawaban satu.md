# 🌷 Dokumentasi Fungsi `findTulipColor`

## 📝 Deskripsi Fungsi

Fungsi `findTulipColor` adalah sebuah fungsi JavaScript yang digunakan untuk mencari warna tulip pada posisi tertentu di dalam taman (garden). Fungsi ini membantu Ellen untuk mengetahui warna tulip yang berada pada posisi yang diinginkan dalam array taman tulipnya.

## 🔧 Parameter

Fungsi ini menerima 2 parameter:

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `garden` | Array | Array yang berisi warna-warna tulip dalam taman |
| `position` | Number | Posisi tulip yang ingin dicari (dimulai dari 1, bukan 0) |

## 📋 Nilai Kembalian (Return Value)

Fungsi ini dapat mengembalikan 3 jenis nilai:

| Kondisi | Return Value |
|---------|--------------|
| Posisi < 1 | `"Oh no! That's not a valid tulip position, Ellen!"` |
| Posisi > ukuran taman | `"Oops! Your garden isn't that big, Ellen!"` |
| Posisi valid | Warna tulip pada posisi tersebut |

## 💻 Kode Fungsi

```javascript
function findTulipColor(garden, position) {
    // Periksa apakah posisi kurang dari 1
    if (position < 1) {
        return "Oh no! That's not a valid tulip position, Ellen!";
    }
    
    // Periksa apakah posisi lebih besar dari ukuran taman
    if (position > garden.length) {
        return "Oops! Your garden isn't that big, Ellen!";
    }
    
    // Kembalikan warna tulip pada posisi yang ditentukan (ubah ke indeks berbasis 0)
    return garden[position - 1];
}
```

## 📊 Cara Kerja Fungsi

1. **Validasi Posisi Minimum**: Fungsi pertama-tama memeriksa apakah posisi yang diminta kurang dari 1. Jika ya, fungsi mengembalikan pesan error.

2. **Validasi Posisi Maksimum**: Selanjutnya fungsi memeriksa apakah posisi yang diminta melebihi ukuran taman. Jika ya, fungsi mengembalikan pesan error.

3. **Mengambil Data**: Jika validasi berhasil, fungsi mengambil warna tulip pada posisi yang diminta dengan mengubah posisi dari sistem 1-based menjadi 0-based index (position - 1).

## 🎯 Contoh Penggunaan

```javascript
// Membuat taman tulip Ellen
const ellenGarden = ["merah", "kuning", "pink", "putih", "ungu"];

// Contoh penggunaan yang berhasil
console.log(findTulipColor(ellenGarden, 1));
// Output: "merah"

console.log(findTulipColor(ellenGarden, 3));
// Output: "pink"

console.log(findTulipColor(ellenGarden, 5));
// Output: "ungu"

// Contoh penggunaan dengan error
console.log(findTulipColor(ellenGarden, 0));
// Output: "Oh no! That's not a valid tulip position, Ellen!"

console.log(findTulipColor(ellenGarden, -1));
// Output: "Oh no! That's not a valid tulip position, Ellen!"

console.log(findTulipColor(ellenGarden, 10));
// Output: "Oops! Your garden isn't that big, Ellen!"
```

## 📚 Penjelasan untuk Pemula

### Apa itu Array?
Array adalah kumpulan data yang disimpan dalam satu variabel. Dalam contoh ini, `garden` adalah array yang berisi warna-warna tulip.

### Mengapa Index Dimulai dari 0?
Dalam pemrograman, array biasanya dimulai dari index 0. Namun fungsi ini dirancang agar user bisa menggunakan posisi yang dimulai dari 1 (lebih natural untuk manusia), sehingga di dalam fungsi kita perlu mengurangi 1 dari posisi yang diminta.

### Error Handling
Fungsi ini menggunakan "error handling" atau penanganan kesalahan untuk memberikan pesan yang ramah kepada user ketika terjadi kesalahan input.

## ⚠️ Catatan Penting

- Posisi tulip dimulai dari **1**, bukan 0
- Fungsi ini case-sensitive terhadap array yang diberikan
- Pastikan parameter `garden` adalah array yang valid
- Pastikan parameter `position` adalah angka positif

## 🎨 Tips Penggunaan

1. **Selalu periksa ukuran taman terlebih dahulu** sebelum mencari posisi tulip
2. **Gunakan posisi mulai dari 1** untuk kemudahan
3. **Siapkan penanganan error** saat menggunakan fungsi ini dalam aplikasi yang lebih besar
