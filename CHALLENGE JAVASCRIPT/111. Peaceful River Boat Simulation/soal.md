# 🚤 Simulasi Perahu Sungai yang Damai

## 📋 Overview Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan pergerakan perahu-perahu di sepanjang sungai yang mengalir dengan tenang. Challenge ini menggabungkan manipulasi array, iterasi, dan pemikiran logis untuk memodelkan ekosistem sungai yang dinamis.

---

## 🎯 Spesifikasi Function

### Nama Function
```javascript
riverBoatSimulation(initialPositions, timeSteps)
```

### Deskripsi
Function ini mensimulasikan pergerakan perahu-perahu di sepanjang sungai yang damai dimana setiap perahu bergerak mengikuti arus dengan kecepatan yang berbeda, dan perahu baru secara berkala bergabung dalam perjalanan.

---

## 📐 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `initialPositions` | `Array<number>` | Sebuah array integer yang merepresentasikan posisi awal perahu-perahu di sungai (0 adalah titik start) |
| `timeSteps` | `number` | Jumlah time step yang akan disimulasikan |

---

## 🔄 Aturan Simulasi

### Mekanisme Pergerakan
- **Setiap perahu yang ada bergerak mengikuti arus** dengan menambahkan posisinya
- **Kecepatan perahu ditentukan oleh index-nya** dalam array ditambah 1:
  - Perahu ke-1 (index 0) → bergerak 1 unit per step
  - Perahu ke-2 (index 1) → bergerak 2 unit per step  
  - Perahu ke-3 (index 2) → bergerak 3 unit per step
  - Dan seterusnya...

### Spawn Perahu Baru
- **Setiap step bernomor genap** (termasuk step 0), perahu baru bergabung di posisi 0
- Step genap: `0, 2, 4, 6, 8, ...`

---

## 📤 Return Value

**Type:** `Array<number>`

Mengembalikan array integer yang merepresentasikan **posisi final dari semua perahu** setelah simulasi selesai.

---

## 💡 Contoh Walkthrough

```javascript
// Contoh: riverBoatSimulation([5, 10], 3)

State awal: [5, 10]
Step 0 (genap): Tambah perahu baru → [0, 5, 10]
            Gerakkan perahu → [0, 6, 12]

Step 1 (ganjil): Tidak ada perahu baru
            Gerakkan perahu → [1, 8, 15]

Step 2 (genap): Tambah perahu baru → [0, 1, 8, 15]
            Gerakkan perahu → [0, 2, 10, 18]

Step 3 (ganjil): Tidak ada perahu baru  
            Gerakkan perahu → [1, 4, 13, 22]

Hasil akhir: [1, 4, 13, 22]
```

---

## 🧠 Konsep Kunci

- **Manipulasi Array**: Menambah dan memodifikasi elemen
- **Logika Berbasis Index**: Menggunakan index array untuk kalkulasi kecepatan
- **Logika Kondisional**: Deteksi step genap/ganjil
- **Iterasi**: Memproses multiple time step
- **Simulasi**: Memodelkan pola pergerakan dunia nyata

---

## ✅ Checklist Implementasi

- [ ] Handle posisi perahu awal dengan benar
- [ ] Implementasi kalkulasi kecepatan yang tepat (index + 1)
- [ ] Tambah perahu baru hanya pada step bernomor genap
- [ ] Gerakkan semua perahu sesuai kecepatan masing-masing setiap step
- [ ] Return array posisi final
- [ ] Handle edge case (array awal kosong, zero time step)

---

*Selamat coding! 🌊*
