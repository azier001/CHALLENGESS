# 🌸 Dokumentasi Fungsi `flowerGardenComposer`

## 📝 Deskripsi

Fungsi `flowerGardenComposer` adalah sebuah fungsi JavaScript yang digunakan untuk membuat komposisi taman bunga virtual. Fungsi ini menggabungkan nama-nama bunga dengan warna-warna cantik secara berurutan, kemudian menyusunnya menjadi satu string yang indah seperti deskripsi taman bunga.

## 🎨 Cara Kerja

Fungsi ini bekerja dengan cara:
1. Mengambil daftar nama bunga yang diberikan
2. Memberikan warna pada setiap bunga secara berurutan (merah, kuning, pink, biru, ungu)
3. Menggabungkan semua bunga berwarna tersebut dengan pemisah yang ditentukan
4. Menghasilkan string deskripsi taman bunga yang cantik

## 📋 Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `flowerNames` | Array | Daftar nama-nama bunga yang akan disusun | `["rose", "tulip", "lily"]` |
| `separator` | String | Karakter atau teks pemisah antar bunga | `", "` atau `" - "` |

## 🌈 Tabel Warna yang Digunakan

| Urutan | Warna | Kode Warna | Emoji |
|--------|-------|------------|-------|
| 1 | red | Merah | 🔴 |
| 2 | yellow | Kuning | 🟡 |
| 3 | pink | Pink | 🟣 |
| 4 | blue | Biru | 🔵 |
| 5 | purple | Ungu | 🟣 |

> **Catatan:** Jika jumlah bunga lebih dari 5, warna akan berulang dari awal (siklik).

## 💻 Kode Fungsi

```javascript
function flowerGardenComposer(flowerNames, separator) {
    // Define the list of colors
    const colors = ["red", "yellow", "pink", "blue", "purple"];
    
    // Create an empty string variable to store the final result
    let result = "";
    
    // Iterate through each flower name in the flowerNames array
    for (let i = 0; i < flowerNames.length; i++) {
        // Determine the associated color using index modulo the number of colors
        const color = colors[i % colors.length];
        
        // Concatenate the color, space, and flower name to the result string
        result += color + " " + flowerNames[i];
        
        // If the current flower is not the last one, append the separator
        if (i < flowerNames.length - 1) {
            result += separator;
        }
    }
    
    // Return the final result string
    return result;
}
```

## 🌟 Contoh Penggunaan dan Output

### Contoh 1: Taman Bunga Sederhana
```javascript
const bunga = ["rose", "tulip", "lily"];
const hasil = flowerGardenComposer(bunga, ", ");
console.log(hasil);
```

**Output:**
```
red rose, yellow tulip, pink lily
```

### Contoh 2: Dengan Pemisah Berbeda
```javascript
const bunga = ["mawar", "melati", "anggrek"];
const hasil = flowerGardenComposer(bunga, " - ");
console.log(hasil);
```

**Output:**
```
red mawar - yellow melati - pink anggrek
```

### Contoh 3: Lebih dari 5 Bunga (Warna Berulang)
```javascript
const bunga = ["rose", "tulip", "lily", "daisy", "orchid", "sunflower", "jasmine"];
const hasil = flowerGardenComposer(bunga, " | ");
console.log(hasil);
```

**Output:**
```
red rose | yellow tulip | pink lily | blue daisy | purple orchid | red sunflower | yellow jasmine
```

## 🔍 Penjelasan Detail untuk Pemula

### Apa itu Modulo (`%`)?
Operator modulo (`%`) memberikan sisa hasil bagi. Dalam fungsi ini:
- `0 % 5 = 0` → warna ke-0 (red)
- `1 % 5 = 1` → warna ke-1 (yellow)
- `5 % 5 = 0` → kembali ke warna ke-0 (red)
- `6 % 5 = 1` → kembali ke warna ke-1 (yellow)

Ini membuat warna berulang secara siklik ketika jumlah bunga lebih banyak dari jumlah warna.

### Mengapa Menggunakan Loop?
Loop `for` digunakan untuk mengiterasi setiap bunga dalam array, sehingga setiap bunga mendapat warna dan digabungkan ke dalam hasil akhir.

### Kapan Separator Ditambahkan?
Separator hanya ditambahkan di antara bunga, bukan di akhir. Kondisi `if (i < flowerNames.length - 1)` memastikan separator tidak ditambahkan setelah bunga terakhir.

## ✨ Tips Penggunaan

- Gunakan separator yang mudah dibaca seperti `", "` atau `" - "`
- Nama bunga bisa dalam bahasa Indonesia atau Inggris
- Fungsi ini sangat berguna untuk membuat deskripsi taman, katalog bunga, atau game berkebun
- Warna akan selalu konsisten untuk posisi yang sama (bunga pertama selalu merah, kedua selalu kuning, dst.)
