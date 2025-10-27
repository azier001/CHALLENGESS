# 🌻 Sunflower Growth Simulation

## Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

---

## 📖 Cerita

Bayangkan Anda sedang berjalan santai melalui ladang bunga matahari di sore hari yang berangin. Anda ditugaskan untuk memantau pertumbuhan bunga matahari dari waktu ke waktu. Function Anda akan mensimulasikan pertumbuhan ini berdasarkan posisi bunga matahari di ladang.

---

## 🎯 Tujuan

Buat sebuah function bernama **`sunflowerHeights`** yang menerima **`initialHeights`** dan **`days`** sebagai parameter-nya.

---

## 📋 Spesifikasi Function

### Nama Function
```
sunflowerHeights
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `initialHeights` | `array` | Array of integers yang merepresentasikan tinggi awal bunga matahari dalam centimeter |
| `days` | `number` | Integer yang merepresentasikan jumlah hari untuk mensimulasikan pertumbuhan |

### Return Value

- **Type:** `array`
- **Deskripsi:** Array of integers yang merepresentasikan tinggi bunga matahari setelah jumlah hari yang ditentukan berlalu

---

## 🌱 Aturan Pola Pertumbuhan

Bunga matahari tumbuh sesuai dengan posisi mereka di ladang:

- **Index genap** (0, 2, 4, dst.) → Tumbuh **1 cm** setiap hari
- **Index ganjil** (1, 3, 5, dst.) → Tumbuh **2 cm** setiap hari

---

## 💡 Contoh

### Input
```javascript
initialHeights = [10, 15, 20, 25]
days = 3
```

### Rincian Pertumbuhan

| Hari | Index 0 | Index 1 | Index 2 | Index 3 |
|-----|---------|---------|---------|---------|
| 0 (Initial) | 10 cm | 15 cm | 20 cm | 25 cm |
| 1 | 11 cm | 17 cm | 21 cm | 27 cm |
| 2 | 12 cm | 19 cm | 22 cm | 29 cm |
| 3 | 13 cm | 21 cm | 23 cm | 31 cm |

### Output
```javascript
[13, 21, 23, 31]
```

---

## 🔑 Poin Penting

- Bunga matahari di **posisi genap** tumbuh **lebih lambat** (1 cm/hari)
- Bunga matahari di **posisi ganjil** tumbuh **lebih cepat** (2 cm/hari)
- Pertumbuhan diterapkan secara kumulatif selama jumlah hari yang ditentukan
- Array original harus diupdate dengan tinggi yang baru

---

## ✅ Checklist Implementasi

- [ ] Buat function dengan nama dan parameter yang benar
- [ ] Lakukan iterasi melalui jumlah hari yang ditentukan
- [ ] Terapkan growth rate yang benar berdasarkan posisi index
- [ ] Return array tinggi yang telah diupdate
- [ ] Test dengan berbagai input case

---

**Semangat dengan simulasi ladang bunga matahari Anda! 🌻**
