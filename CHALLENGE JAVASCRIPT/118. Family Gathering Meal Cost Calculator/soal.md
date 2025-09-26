# 🍽️ Kalkulator Biaya Makanan Acara Keluarga

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Buat sebuah function yang menghitung total biaya makanan untuk acara keluarga berdasarkan jumlah tamu dan preferensi makanan.

---

## 🎯 Tujuan

Implementasikan function bernama `calculateMealCost` yang menghitung total biaya makanan untuk acara keluarga.

## 📝 Spesifikasi Function

### Nama Function
```javascript
calculateMealCost(guestCount, mealType)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `guestCount` | `number` | Jumlah total tamu yang hadir |
| `mealType` | `string` | Jenis makanan: `"vegetarian"` atau `"non-vegetarian"` |

### Return Value

- **Type:** `number`
- **Deskripsi:** Total biaya untuk semua makanan

---

## 💰 Struktur Harga

| Jenis Makanan | Biaya per Orang |
|---------------|----------------|
| 🥗 **Vegetarian** | `$10` |
| 🍖 **Non-Vegetarian** | `$15` |

---

## 🔧 Persyaratan Implementasi

1. **Logika Function:**
   - Tentukan biaya per orang berdasarkan `mealType`
   - Kalikan biaya per orang dengan `guestCount`
   - Return total biaya yang telah dihitung

2. **Formula Perhitungan:**
   ```
   Total Biaya = Biaya per Orang × Jumlah Tamu
   ```

---

## 💡 Contoh Penggunaan

```javascript
// Makanan vegetarian untuk 8 tamu
calculateMealCost(8, "vegetarian");
// Hasil yang diharapkan: 80

// Makanan non-vegetarian untuk 12 tamu
calculateMealCost(12, "non-vegetarian");
// Hasil yang diharapkan: 180
```

---

## ✅ Kriteria Keberhasilan

- [ ] Function menerima dua parameter dengan benar
- [ ] Menangani harga vegetarian dengan tepat ($10/orang)
- [ ] Menangani harga non-vegetarian dengan tepat ($15/orang)
- [ ] Mengembalikan perhitungan total biaya yang akurat
- [ ] Nama function sesuai dengan spesifikasi

---

*Semoga berhasil dengan implementasi Anda! 🚀*
