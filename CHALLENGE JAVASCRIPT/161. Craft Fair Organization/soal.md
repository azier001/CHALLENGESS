# 🎨 Craft Fair Organization

## Tingkat Kesulitan
**Easy** ⭐

---

## 📋 Gambaran Umum

Buat sebuah function `organizeFairSchedule` yang mengelola logistik craft fair dengan memperbarui jumlah display dan menggabungkan jadwal acara.

---

## 🎯 Spesifikasi Function

### Nama Function
```javascript
organizeFairSchedule(basketCount, textileCount, musicianSlots, belfryChimes)
```

### Deskripsi
Function ini melakukan dua operasi utama:
1. **Menambahkan** jumlah basket dan textile display sebanyak 1
2. **Menggabungkan** musician performance slots dengan belfry chime times menjadi satu array schedule terpadu

---

## 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `basketCount` | `number` | Jumlah basket display saat ini |
| `textileCount` | `number` | Jumlah textile display saat ini |
| `musicianSlots` | `array` | Array waktu performance musician |
| `belfryChimes` | `array` | Array waktu belfry chime |

---

## 📤 Return Value

**Type:** `Object`

**Struktur:**
```javascript
{
  baskets: number,
  textiles: number,
  schedule: array
}
```

### Properti Return Object

- **`baskets`** — Jumlah basket yang diperbarui (original + 1)
- **`textiles`** — Jumlah textile yang diperbarui (original + 1)
- **`schedule`** — Array gabungan dari musician slots dan belfry chimes

---

## 💡 Contoh Penggunaan

```javascript
// Input
organizeFairSchedule(5, 8, ["10:00", "14:00"], ["12:00", "16:00"])

// Output
{
  baskets: 6,
  textiles: 9,
  schedule: ["10:00", "14:00", "12:00", "16:00"]
}
```

---

## ✅ Persyaratan Utama

- ✓ Tambahkan `basketCount` dan `textileCount` tepat sebanyak 1
- ✓ Pertahankan urutan original saat menggabungkan array (musicians dulu, kemudian chimes)
- ✓ Return sebuah object dengan nama property yang tepat: `baskets`, `textiles`, `schedule`
- ✓ Pastikan schedule array mencakup semua elemen dari kedua input array

---

## 🔍 Catatan Implementasi

- Gunakan array concatenation methods untuk menggabungkan schedule array
- Pastikan immutability dengan tidak memodifikasi parameter input original
- Tangani edge case seperti empty array dengan baik

---

**Selamat mengerjakan! 🚀**
