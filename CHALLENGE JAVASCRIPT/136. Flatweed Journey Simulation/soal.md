# 🌾 Flatweed Journey Simulation

## Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan perjalanan melalui ladang flatweed yang misterius. Navigasi melalui medan dengan mengambil langkah di berbagai arah dan lacak posisi akhir Anda!

---

## 📋 Deskripsi Soal

Implementasikan function bernama **`flatweedJourney`** yang menerima dua parameter:

- **`steps`** (number): Jumlah langkah yang akan diambil dalam perjalanan
- **`direction`** (string): Arah dari setiap langkah

### Valid Directions
- `"north"` - Bergerak maju
- `"south"` - Bergerak mundur
- `"east"` - Gerakan horizontal
- `"west"` - Gerakan horizontal

---

## 🎯 Aturan & Mekanisme

### Aturan Pergerakan

| Direction | Efek pada Position |
|-----------|-------------------|
| `"north"` | **Tambah 1** ke posisi saat ini |
| `"south"` | **Kurangi 1** dari posisi saat ini |
| `"east"` | **Tidak ada perubahan** pada posisi |
| `"west"` | **Tidak ada perubahan** pada posisi |

### Aturan Khusus: The Multiple of 5 Barrier

> ⚠️ **Penting:** Jika posisi saat ini mencapai **kelipatan 5** (0, 5, 10, -5, -10, dll), langkah saat ini **diabaikan** dan Anda melanjutkan ke langkah berikutnya.

---

## 🔄 Function Signature

```javascript
function flatweedJourney(steps, direction) {
  // Implementasi Anda di sini
}
```

---

## 📊 Perilaku yang Diharapkan

1. **Mulai** dari posisi `0`
2. **Iterasi** melalui jumlah langkah yang ditentukan
3. **Terapkan** aturan direction untuk setiap langkah
4. **Cek** apakah posisi adalah kelipatan 5 sebelum menerapkan pergerakan
5. **Return** posisi akhir setelah semua langkah

---

## 💡 Contoh Skenario

### Contoh 1: Perjalanan North Sederhana
```javascript
flatweedJourney(3, "north")
// Steps: 0 → 1 → 2 → 3
// Result: 3
```

### Contoh 2: Bertemu Multiple of 5
```javascript
flatweedJourney(6, "north")
// Steps: 0 → 1 → 2 → 3 → 4 → (5 terblokir!) → 5
// Result: 5
```

### Contoh 3: Mixed Directions
```javascript
flatweedJourney(4, "south")
// Steps: 0 → -1 → -2 → -3 → -4
// Result: -4
```

### Contoh 4: Tidak Ada Perubahan Posisi
```javascript
flatweedJourney(5, "east")
// Steps: 0 → 0 → 0 → 0 → 0
// Result: 0
```

---

## ✅ Kriteria Keberhasilan

Function Anda harus:
- ✓ Menerima `steps` (number) dan `direction` (string) sebagai parameter
- ✓ Mengimplementasikan pergerakan dengan benar untuk keempat arah
- ✓ Melewati langkah ketika posisi adalah kelipatan 5
- ✓ Mengembalikan posisi akhir sebagai number
- ✓ Menangani posisi positif dan negatif

---

## 🚀 Tips Memulai

Pikirkan tentang:
1. Bagaimana cara melacak posisi saat ini
2. Bagaimana cara melakukan loop melalui steps
3. Bagaimana cara mengecek apakah sebuah angka adalah kelipatan 5
4. Urutan operasi (cek posisi KEMUDIAN terapkan pergerakan)

Selamat berpetualang melalui ladang flatweed! 🌾✨
