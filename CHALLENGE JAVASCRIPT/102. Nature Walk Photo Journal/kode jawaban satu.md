# 📸 Fungsi organizePhotos

## 📝 Deskripsi

Fungsi `organizePhotos` adalah sebuah fungsi JavaScript yang digunakan untuk mengelompokkan foto-foto berdasarkan tag atau kategori tertentu. Fungsi ini akan mengambil dua array (daftar tag dan daftar foto) kemudian mengembalikan sebuah objek yang berisi foto-foto yang sudah dikelompokkan berdasarkan tag-nya.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `tags` | Array | Daftar tag/kategori untuk setiap foto (string) |
| `photos` | Array | Daftar nama file foto atau path foto (string) |

### ⚠️ Catatan Penting:
- Kedua array harus memiliki panjang yang sama
- Index array `tags` dan `photos` harus sesuai (foto ke-1 memiliki tag ke-1, dst.)

## 💻 Kode Fungsi

```javascript
function organizePhotos(tags, photos) {
  // Membuat objek kosong untuk menyimpan hasil pengelompokan
  const organizedPhotos = {};
  
  // Melakukan perulangan untuk setiap tag dan foto
  for (let i = 0; i < tags.length; i++) {
    const tag = tags[i];      // Mengambil tag pada index ke-i
    const photo = photos[i];  // Mengambil foto pada index ke-i
    
    // Jika tag sudah ada di objek, tambahkan foto ke array yang sudah ada
    if (organizedPhotos[tag]) {
      organizedPhotos[tag].push(photo);
    } else {
      // Jika tag belum ada, buat array baru dengan foto pertama
      organizedPhotos[tag] = [photo];
    }
  }
  
  // Mengembalikan objek hasil pengelompokan
  return organizedPhotos;
}
```

## 📋 Cara Kerja

1. **Inisialisasi**: Membuat objek kosong `organizedPhotos` untuk menyimpan hasil
2. **Iterasi**: Melakukan perulangan untuk setiap elemen dalam array `tags`
3. **Pengecekan**: Untuk setiap tag, cek apakah sudah ada dalam objek `organizedPhotos`
4. **Penambahan**: 
   - Jika tag sudah ada: tambahkan foto ke array yang sudah ada
   - Jika tag belum ada: buat array baru dengan foto sebagai elemen pertama
5. **Return**: Mengembalikan objek yang berisi foto-foto yang sudah dikelompokkan

## 🎯 Contoh Penggunaan

### Input:
```javascript
const tags = ["liburan", "kerja", "liburan", "keluarga", "kerja"];
const photos = ["pantai1.jpg", "meeting.jpg", "pantai2.jpg", "reunion.jpg", "office.jpg"];

const hasil = organizePhotos(tags, photos);
console.log(hasil);
```

### Output:
```javascript
{
  "liburan": ["pantai1.jpg", "pantai2.jpg"],
  "kerja": ["meeting.jpg", "office.jpg"],
  "keluarga": ["reunion.jpg"]
}
```

## 📊 Contoh Tabel Hasil

| Tag | Foto-foto |
|-----|-----------|
| liburan | pantai1.jpg, pantai2.jpg |
| kerja | meeting.jpg, office.jpg |
| keluarga | reunion.jpg |

## 🚀 Kegunaan Praktis

Fungsi ini sangat berguna untuk:
- 📁 Mengelompokkan file foto berdasarkan kategori
- 🏷️ Membuat sistem tagging sederhana
- 📱 Aplikasi galeri foto
- 🗂️ Sistem manajemen file multimedia
- 📈 Analisis data berbasis kategori

## ⚡ Tips Penggunaan

- Pastikan array `tags` dan `photos` memiliki panjang yang sama
- Gunakan tag yang konsisten (contoh: "liburan" bukan "Liburan" atau "LIBURAN")
- Fungsi ini bersifat case-sensitive untuk tag
- Cocok digunakan untuk dataset kecil hingga menengah

## 🔍 Kompleksitas

- **Time Complexity**: O(n) - dimana n adalah jumlah foto
- **Space Complexity**: O(n) - untuk menyimpan objek hasil

## 🔄 Perbedaan Implementasi

Implementasi ini menggunakan pendekatan yang lebih langsung:
- Menggunakan kondisi `if-else` untuk mengecek apakah tag sudah ada
- Langsung membuat array dengan foto pertama jika tag belum ada
- Nama variabel `organizedPhotos` lebih deskriptif dan jelas
