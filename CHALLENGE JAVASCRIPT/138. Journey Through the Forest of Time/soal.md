# 🌲 Journey Through the Forest of Time

## Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Mulailah perjalanan mistis melalui hutan pohon cemara berwarna biru kuno, di mana setiap pohon menyimpan kebijaksanaan dari berbagai zaman. Misi Anda adalah melintasi hutan yang memesona ini, mengumpulkan kisah-kisah waktu saat Anda berjalan.

---

## 📋 Deskripsi Tugas

Buat sebuah function bernama **`forestJourney`** yang menghitung jumlah usia pohon yang ditemui sepanjang perjalanan Anda melalui hutan.

### Function Signature

```javascript
function forestJourney(forest, startCoordinate)
```

---

## 🎯 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `forest` | `Array<Array<number>>` | Array 2D yang merepresentasikan hutan, di mana setiap cell berisi usia pohon |
| `startCoordinate` | `Array<number>` | Posisi awal dalam format `[row, column]` |

---

## 🎁 Return Value

- **Type:** `number`
- **Deskripsi:** Jumlah total usia pohon yang ditemui selama perjalanan dari awal hingga akhir

---

## 🧭 Aturan Perjalanan

> **Batasan Pergerakan:**
> - ✅ Anda dapat bergerak ke **KANAN** (→)
> - ✅ Anda dapat bergerak ke **BAWAH** (↓)
> - ❌ Anda tidak dapat bergerak ke kiri atau atas

> **Ketentuan Path:**
> - 🚀 Perjalanan dimulai dari `startCoordinate`
> - 🏁 Perjalanan berakhir di **pojok kanan bawah** hutan
> - 📍 Sertakan usia pohon di **kedua** titik awal dan akhir dalam jumlah total Anda

---

## 💡 Contoh

### Peta Hutan

```javascript
const forest = [
    [5, 3, 4],
    [2, 1, 7],
    [8, 6, 9]
];

const startCoordinate = [0, 1];  // Dimulai dari pohon kedua di baris pertama
```

### Representasi Visual

```
    0   1   2
  ┌───┬───┬───┐
0 │ 5 │ 3*│ 4 │  * = Titik Awal (Starting Point)
  ├───┼───┼───┤
1 │ 2 │ 1 │ 7 │
  ├───┼───┼───┤
2 │ 8 │ 6 │ 9■│  ■ = Titik Akhir (Ending Point)
  └───┴───┴───┘
```

### Sample Path

Salah satu kemungkinan path perjalanan:

```
3 → 4 → 7 → 9
```

**Hasil:** `3 + 4 + 7 + 9 = 23`

---

## 🎨 Catatan Implementasi

Tugas Anda adalah mengimplementasikan function `forestJourney` yang:
1. Menavigasi melalui hutan mistis
2. Menghitung jumlah usia pohon sepanjang path
3. Mengembalikan total sum yang merepresentasikan perjalanan kontemplatif Anda melalui waktu

---

## 🌟 Semoga Berhasil!

Semoga perjalanan Anda melalui Forest of Time dipenuhi dengan kebijaksanaan dan penemuan! 🌲✨
