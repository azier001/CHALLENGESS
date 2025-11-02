# 🌊 Ocean Navigation Challenge

## Tingkat Kesulitan
**Easy** ⭐

---

## 📋 Deskripsi Challenge

Buat sebuah function bernama `navigateOcean` yang menentukan apakah sebuah kapal dapat melakukan perjalanan langsung dari posisi saat ini ke destinasi pada grid berbasis peta laut.

---

## 🗺️ Sistem Grid

Laut direpresentasikan sebagai **grid 5×5** di mana setiap posisi diidentifikasi dengan:

- **Huruf (A-E)**: Posisi vertikal (baris)
- **Angka (1-5)**: Posisi horizontal (kolom)

### Contoh Layout Grid

```
    1   2   3   4   5
  ┌───┬───┬───┬───┬───┐
A │ A1│ A2│ A3│ A4│ A5│
  ├───┼───┼───┼───┼───┤
B │ B1│ B2│ B3│ B4│ B5│
  ├───┼───┼───┼───┼───┤
C │ C1│ C2│ C3│ C4│ C5│
  ├───┼───┼───┼───┼───┤
D │ D1│ D2│ D3│ D4│ D5│
  ├───┼───┼───┼───┼───┤
E │ E1│ E2│ E3│ E4│ E5│
  └───┴───┴───┴───┴───┘
```

---

## 🎯 Aturan Navigasi

Kapal dapat melakukan perjalanan **langsung** jika bergerak sepanjang:

- ✅ **Garis horizontal yang sama** (angka yang sama) — *Contoh: A1 → E1*
- ✅ **Garis vertikal yang sama** (huruf yang sama) — *Contoh: A1 → A5*

Kapal **tidak dapat** melakukan perjalanan langsung jika:

- ❌ **Huruf DAN angka keduanya berubah** — *Contoh: A1 → B3*

---

## 📝 Spesifikasi Function

### Function Signature

```javascript
function navigateOcean(currentPosition, destination)
```

### Parameters

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `currentPosition` | `string` | Posisi kapal saat ini pada grid | `"A1"` |
| `destination` | `string` | Posisi destinasi yang diinginkan | `"B3"` |

### Return Value

| Tipe | Value | Kondisi |
|------|-------|---------|
| `boolean` | `true` | Perjalanan langsung **memungkinkan** (baris atau kolom sama) |
| `boolean` | `false` | Perjalanan langsung **tidak memungkinkan** (gerakan diagonal) |

---

## 💡 Contoh

### ✅ Perjalanan Langsung Valid

```javascript
navigateOcean("A1", "A5")  // true  → Baris yang sama (A)
navigateOcean("B2", "E2")  // true  → Kolom yang sama (2)
navigateOcean("C3", "C3")  // true  → Posisi yang sama
```

### ❌ Perjalanan Langsung Tidak Valid

```javascript
navigateOcean("A1", "B3")  // false → Baris DAN kolom berbeda
navigateOcean("D2", "E4")  // false → Gerakan diagonal
navigateOcean("A1", "E5")  // false → Gerakan diagonal
```

---

## 🚀 Tips Implementasi

1. Ekstrak **huruf** (vertikal) dan **angka** (horizontal) dari setiap posisi
2. Bandingkan kedua komponen antara posisi saat ini dan destinasi
3. Return `true` jika **salah satu** huruf **atau** angka cocok (atau keduanya)
4. Return `false` jika **keduanya** berbeda

---

## 🎓 Skills yang Dipraktikkan

- Manipulasi string
- Logika conditional
- Operasi boolean
- Pengenalan pola

---

**Semoga berhasil, Kapten!** ⚓
