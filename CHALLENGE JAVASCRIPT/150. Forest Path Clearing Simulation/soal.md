# 🌲 Forest Path Clearing Simulation

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan seorang gardener membersihkan jalur melalui hutan dengan pola spiral. Gardener bergerak melalui hutan dan membersihkan area 3×3 di sekitar posisinya pada setiap step.

---

## 🎯 Tujuan

Implementasikan function `clearForestPaths` yang menerima empat parameter dan mengembalikan array 2D yang telah dimodifikasi yang merepresentasikan hutan setelah gardener menyelesaikan semua langkah pembersihan.

---

## 📥 Function Signature

```javascript
function clearForestPaths(forest, startRow, startCol, steps)
```

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `forest` | `Array<Array<string>>` | Array 2D yang merepresentasikan grid hutan |
| `startRow` | `number` | Posisi baris awal (0-indexed) |
| `startCol` | `number` | Posisi kolom awal (0-indexed) |
| `steps` | `number` | Jumlah langkah yang diambil gardener |

---

## 🗺️ Representasi Forest

Forest direpresentasikan oleh array 2D di mana setiap cell berisi salah satu dari tiga karakter:

- **`'T'`** - Tree (dapat dibersihkan)
- **`'P'`** - Path (sudah dibersihkan)
- **`'C'`** - Clearing (area terbuka)

---

## 🌀 Pola Pergerakan

Gardener mengikuti **pola spiral**:

1. **Right** →
2. **Down** ↓
3. **Left** ←
4. **Up** ↑
5. Ulangi...

---

## ✂️ Mekanisme Clearing

Pada setiap step:

1. **Bersihkan** area 3×3 yang berpusat pada posisi saat ini
2. Ganti semua `'T'` (trees) dengan `'P'` (paths) di area ini
3. **Bergerak** ke posisi berikutnya mengikuti pola spiral

### Area Clearing 3×3

```
[ ][ ][ ]
[ ][G][ ]  ← G = Posisi Gardener
[ ][ ][ ]
```

---

## ⚠️ Constraint Penting

- **Penanganan boundary:** Jangan modifikasi posisi di luar batas forest
- Jika area 3×3 melampaui tepi, hanya bersihkan posisi yang valid di dalam forest
- Hanya cell `'T'` yang harus dikonversi menjadi `'P'`
- Cell `'P'` dan `'C'` tetap tidak berubah

---

## 📤 Return Value

Mengembalikan array 2D yang telah dimodifikasi (`Array<Array<string>>`) yang merepresentasikan forest setelah semua langkah pembersihan selesai.

---

## 💡 Contoh Skenario

**Forest Awal:**
```
T T T T T
T T T T T
T T T T T
T T T T T
```

**Setelah clearing dari posisi (1, 1) dengan 2 steps:**
```
T P P P T
T P P P T
T P P T T
T T T T T
```

---

## 🎓 Tips

- Track arah saat ini (right, down, left, up)
- Ubah arah setelah bergerak dalam pola spiral
- Gunakan boundary checks sebelum membersihkan setiap cell di area 3×3
- Pertimbangkan edge cases di mana posisi awal berada dekat dengan boundaries

---

**Semangat untuk implementasinya! 🚀**
