# 🌱 Dokumentasi Fungsi updatePlantGrowth

## 📝 Deskripsi Fungsi

Fungsi `updatePlantGrowth()` digunakan untuk memperbarui tahap pertumbuhan tanaman. Fungsi ini akan menaikkan level pertumbuhan tanaman sebesar 1 tahap, dengan menggunakan `Math.min()` untuk memastikan tahap tidak melebihi batas maksimal (tahap 9 - siap panen).

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `plantInfo` | String | String yang berisi nama tanaman dan tahap pertumbuhan saat ini, dipisahkan dengan titik dua (`:`) |

### Format Input:
```
"namaTanaman:tahapSaatIni"
```

**Contoh:** `"Tomat:3"` atau `"Cabai:0"`

## 📊 Tabel Tahap Pertumbuhan

| Index | Tahap | Deskripsi | Penjelasan |
|-------|-------|-----------|------------|
| 0 | 0 | Seed | Benih/biji |
| 1 | 1 | Germination | Proses perkecambahan |
| 2 | 2 | Seedling | Bibit muda |
| 3 | 3 | Vegetative | Fase pertumbuhan daun |
| 4 | 4 | Budding | Mulai bertunas |
| 5 | 5 | Flowering | Fase berbunga |
| 6 | 6 | Pollination | Proses penyerbukan |
| 7 | 7 | Fruit development | Pembentukan buah |
| 8 | 8 | Ripening | Proses pematangan |
| 9 | 9 | Harvest-ready | Siap dipanen |

## 💻 Kode Fungsi

```javascript
function updatePlantGrowth(plantInfo) {
    // Ekstrak nama tanaman dan tahap saat ini dari string input
    const [plantName, currentStage] = plantInfo.split(':');
    
    // Hitung tahap baru dengan menambah 1, tapi maksimal 9 menggunakan Math.min
    let newStage = Math.min(parseInt(currentStage) + 1, 9);
    
    // Array deskripsi untuk setiap tahap pertumbuhan (menggunakan index array)
    const stageDescriptions = [
        "Seed",                // Index 0
        "Germination",         // Index 1
        "Seedling",           // Index 2
        "Vegetative",         // Index 3
        "Budding",            // Index 4
        "Flowering",          // Index 5
        "Pollination",        // Index 6
        "Fruit development",  // Index 7
        "Ripening",           // Index 8
        "Harvest-ready"       // Index 9
    ];
    
    // Ambil deskripsi berdasarkan index tahap yang baru
    const newDescription = stageDescriptions[newStage];
    
    // Kembalikan string yang sudah diperbarui sesuai format yang diperlukan
    return `${plantName}:${newStage} - ${newDescription}`;
}
```

## 📖 Cara Kerja Fungsi

1. **Parsing Input**: Fungsi memisahkan string input menggunakan titik dua (`:`) untuk mendapatkan nama tanaman dan tahap saat ini
2. **Kalkulasi Tahap Baru**: Menggunakan `Math.min(parseInt(currentStage) + 1, 9)` untuk menaikkan tahap sebesar 1, tetapi tidak melebihi 9
3. **Mapping Deskripsi**: Tahap baru digunakan sebagai index untuk mengakses array `stageDescriptions`
4. **Return**: Fungsi mengembalikan string dengan format `namaTanaman:tahapBaru - deskripsi`

## 🎯 Contoh Penggunaan & Output

### Contoh 1: Tanaman Normal (Belum Maksimal)
```javascript
// Input
updatePlantGrowth("Tomat:2");

// Output
"Tomat:3 - Vegetative"
```

### Contoh 2: Tanaman dari Benih
```javascript
// Input
updatePlantGrowth("Cabai:0");

// Output
"Cabai:1 - Germination"
```

### Contoh 3: Tanaman Siap Panen (Sudah Maksimal)
```javascript
// Input
updatePlantGrowth("Padi:9");

// Output
"Padi:9 - Harvest-ready"
```

### Contoh 4: Tanaman Hampir Siap Panen
```javascript
// Input
updatePlantGrowth("Jagung:8");

// Output
"Jagung:9 - Harvest-ready"
```

### Contoh 5: Tanaman di Tahap Tengah
```javascript
// Input
updatePlantGrowth("Mentimun:5");

// Output
"Mentimun:6 - Pollination"
```

## ⚠️ Catatan Penting

- Fungsi ini menggunakan `Math.min()` untuk memastikan tahap tidak melebihi 9 (Harvest-ready)
- Array `stageDescriptions` menggunakan index 0-9 yang sesuai dengan tahap pertumbuhan
- Format input harus tepat: `"namaTanaman:angka"` 
- Jika format input salah, fungsi mungkin tidak bekerja dengan benar
- Tahap pertumbuhan hanya bisa berupa angka 0-9

## 🔍 Perbedaan Kode

Versi ini menggunakan pendekatan yang lebih efisien:
- **`Math.min()`**: Menggantikan kondisi `if` untuk pembatasan maksimal
- **Array**: Menggunakan array dengan index daripada object untuk mapping deskripsi
- **Lebih Ringkas**: Kode lebih singkat dan mudah dibaca

## 🚀 Tips Penggunaan

- Gunakan fungsi ini dalam loop untuk mensimulasikan pertumbuhan tanaman dari waktu ke waktu
- Combine dengan fungsi lain untuk membuat sistem pertanian yang kompleks
- Pastikan input selalu mengikuti format yang benar untuk menghindari error
- `Math.min()` memberikan performa yang lebih baik dibandingkan kondisi `if` dalam kasus ini
