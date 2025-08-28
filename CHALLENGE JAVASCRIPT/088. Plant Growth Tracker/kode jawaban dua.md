# 🌱 Dokumentasi Fungsi updatePlantGrowth

## 📝 Deskripsi Fungsi

Fungsi `updatePlantGrowth()` digunakan untuk memperbarui tahap pertumbuhan tanaman. Fungsi ini akan menaikkan level pertumbuhan tanaman sebesar 1 tahap, kecuali jika tanaman sudah mencapai tahap maksimal (tahap 9 - siap panen).

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

| Tahap | Deskripsi | Penjelasan |
|-------|-----------|------------|
| 0 | Seed | Benih/biji |
| 1 | Germination | Proses perkecambahan |
| 2 | Seedling | Bibit muda |
| 3 | Vegetative | Fase pertumbuhan daun |
| 4 | Budding | Mulai bertunas |
| 5 | Flowering | Fase berbunga |
| 6 | Pollination | Proses penyerbukan |
| 7 | Fruit development | Pembentukan buah |
| 8 | Ripening | Proses pematangan |
| 9 | Harvest-ready | Siap dipanen |

## 💻 Kode Fungsi

```javascript
function updatePlantGrowth(plantInfo) {
    // Ekstrak nama tanaman dan tahap saat ini dari string input
    const [plantName, currentStage] = plantInfo.split(':');
    
    // Konversi tahap saat ini menjadi angka
    let stage = parseInt(currentStage);
    
    // Naikkan tahap pertumbuhan sebesar 1, kecuali jika sudah di tahap 9
    if (stage < 9) {
        stage += 1;
    }
    
    // Definisi deskripsi untuk setiap tahap pertumbuhan
    const stageDescriptions = {
        0: "Seed",
        1: "Germination", 
        2: "Seedling",
        3: "Vegetative",
        4: "Budding",
        5: "Flowering",
        6: "Pollination",
        7: "Fruit development",
        8: "Ripening",
        9: "Harvest-ready"
    };
    
    // Ambil deskripsi untuk tahap yang baru
    const description = stageDescriptions[stage];
    
    // Kembalikan string yang sudah diperbarui sesuai format yang diperlukan
    return `${plantName}:${stage} - ${description}`;
}
```

## 📖 Cara Kerja Fungsi

1. **Parsing Input**: Fungsi memisahkan string input menggunakan titik dua (`:`) untuk mendapatkan nama tanaman dan tahap saat ini
2. **Konversi**: Tahap pertumbuhan dikonversi dari string menjadi number menggunakan `parseInt()`
3. **Update Tahap**: Jika tahap saat ini kurang dari 9, maka tahap akan dinaikkan sebesar 1
4. **Mapping Deskripsi**: Tahap baru dipetakan ke deskripsi yang sesuai menggunakan objek `stageDescriptions`
5. **Return**: Fungsi mengembalikan string dengan format `namaTanaman:tahapBaru - deskripsi`

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

## ⚠️ Catatan Penting

- Fungsi ini **tidak akan** menaikkan tahap jika tanaman sudah berada di tahap 9 (Harvest-ready)
- Format input harus tepat: `"namaTanaman:angka"` 
- Jika format input salah, fungsi mungkin tidak bekerja dengan benar
- Tahap pertumbuhan hanya bisa berupa angka 0-9

## 🚀 Tips Penggunaan

- Gunakan fungsi ini dalam loop untuk mensimulasikan pertumbuhan tanaman dari waktu ke waktu
- Combine dengan fungsi lain untuk membuat sistem pertanian yang kompleks
- Pastikan input selalu mengikuti format yang benar untuk menghindari error
