# 🌱 Dokumentasi Fungsi `gardenStatus`

## 📖 Deskripsi Fungsi

Fungsi `gardenStatus` adalah sebuah fungsi JavaScript yang digunakan untuk menentukan status pertumbuhan tanaman berdasarkan jenis tanaman dan jumlah hari yang telah berlalu sejak penanaman. Fungsi ini sangat berguna untuk aplikasi berkebun atau game farming yang ingin memberikan feedback kepada pengguna tentang perkembangan tanaman mereka.

## 🔧 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `plantType` | String | Nama jenis tanaman (contoh: "tomat", "wortel", "cabai") |
| `daysGrown` | Number | Jumlah hari sejak tanaman ditanam (harus angka positif atau 0) |

## 📊 Tabel Status Pertumbuhan

| Rentang Hari | Status | Deskripsi |
|---------------|--------|-----------|
| < 0 | Invalid | Input tidak valid |
| 0 | Baru Ditanam | Benih baru saja ditanam |
| 1-10 | Berkecambah | Bibit mulai tumbuh |
| 11-20 | Tumbuh Stabil | Tanaman berkembang dengan baik |
| 21-30 | Dewasa | Tanaman sudah matang dan berkembang |
| > 30 | Siap Panen | Tanaman siap untuk dipanen |

## 💻 Kode Fungsi

```javascript
function gardenStatus(plantType, daysGrown) {
    // Validasi input: pastikan jumlah hari tidak negatif
    if (daysGrown < 0) {
        return "Invalid number of days.";
    }
    
    // Status: Benih baru ditanam (hari ke-0)
    if (daysGrown === 0) {
        return `The ${plantType} seed is just planted.`;
    }
    
    // Status: Fase berkecambah (hari 1-10)
    if (daysGrown >= 1 && daysGrown <= 10) {
        return `The ${plantType} seedling is sprouting.`;
    }
    
    // Status: Fase pertumbuhan stabil (hari 11-20)
    if (daysGrown >= 11 && daysGrown <= 20) {
        return `The ${plantType} plant is growing steadily.`;
    }
    
    // Status: Fase dewasa dan berkembang (hari 21-30)
    if (daysGrown >= 21 && daysGrown <= 30) {
        return `The ${plantType} plant is mature and thriving.`;
    }
    
    // Status: Siap dipanen (hari > 30)
    if (daysGrown > 30) {
        return `The ${plantType} plant is ready for harvest!`;
    }
}
```

## 🚀 Contoh Penggunaan

```javascript
// Contoh 1: Tanaman baru ditanam
console.log(gardenStatus("tomat", 0));
// Output: "The tomat seed is just planted."

// Contoh 2: Tanaman sedang berkecambah
console.log(gardenStatus("wortel", 5));
// Output: "The wortel seedling is sprouting."

// Contoh 3: Tanaman tumbuh stabil
console.log(gardenStatus("cabai", 15));
// Output: "The cabai plant is growing steadily."

// Contoh 4: Tanaman dewasa
console.log(gardenStatus("selada", 25));
// Output: "The selada plant is mature and thriving."

// Contoh 5: Tanaman siap panen
console.log(gardenStatus("bayam", 35));
// Output: "The bayam plant is ready for harvest!"

// Contoh 6: Input tidak valid
console.log(gardenStatus("jagung", -5));
// Output: "Invalid number of days."
```

## 📝 Contoh Output

| Input | Output |
|-------|--------|
| `gardenStatus("tomat", 0)` | `"The tomat seed is just planted."` |
| `gardenStatus("wortel", 7)` | `"The wortel seedling is sprouting."` |
| `gardenStatus("cabai", 18)` | `"The cabai plant is growing steadily."` |
| `gardenStatus("selada", 28)` | `"The selada plant is mature and thriving."` |
| `gardenStatus("bayam", 40)` | `"The bayam plant is ready for harvest!"` |
| `gardenStatus("jagung", -3)` | `"Invalid number of days."` |

## 💡 Tips Penggunaan

1. **Validasi Input**: Fungsi ini sudah memiliki validasi untuk input negatif, namun pastikan parameter `plantType` selalu berupa string.

2. **Fleksibilitas**: Anda dapat menggunakan nama tanaman dalam bahasa Indonesia atau bahasa lain sesuai kebutuhan aplikasi.

3. **Pengembangan**: Fungsi ini dapat dikembangkan lebih lanjut dengan menambahkan:
   - Status khusus untuk jenis tanaman tertentu
   - Perhitungan berdasarkan kondisi cuaca
   - Sistem level atau XP untuk game

## 🎯 Kasus Penggunaan

- **Aplikasi Berkebun**: Membantu pengguna melacak perkembangan tanaman di kebun mereka
- **Game Farming**: Memberikan feedback visual tentang progress tanaman dalam game
- **Sistem Edukasi**: Mengajarkan siklus pertumbuhan tanaman kepada anak-anak
- **Dashboard Pertanian**: Monitoring status tanaman dalam skala yang lebih besar
