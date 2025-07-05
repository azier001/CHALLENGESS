# 🌿 Tantangan Nature's Energy Sequence

## 📋 Gambaran Umum Challenge

**Tingkat Kesulitan:** `Easy`

Sebagai ilmuwan yang menjelajahi sudut-sudut tersembunyi alam, Anda telah mengembangkan sistem untuk melacak level energi saat mengamati berbagai elemen alam. Tugas Anda adalah mengimplementasikan sistem pelacakan energi ini dalam kode.

## 🎯 Objektif

Buat function bernama `exploreNatureSequence` yang memproses sequence elemen alam dan menghitung level energi akhir berdasarkan aturan tertentu.

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function exploreNatureSequence(sequence, energy)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `sequence` | `string` | String yang merepresentasikan sequence elemen alam |
| `energy` | `number` | Integer yang merepresentasikan level energi awal ilmuwan |

### Elemen Alam

Sequence terdiri dari karakter-karakter berikut, masing-masing merepresentasikan elemen alam yang berbeda:

- **🌸 `F`** - Flower (Bunga)
- **🪨 `R`** - Rock (Batu)  
- **🌳 `T`** - Tree (Pohon)
- **🍃 `L`** - Leaf (Daun)

## ⚡ Aturan Perhitungan Energi

Function memproses sequence dan memodifikasi level energi sesuai dengan aturan berikut:

### 1. Perbandingan Elemen Bersebelahan
- **Elemen sama:** `energy + 1`
- **Elemen berbeda:** `energy - 1`

### 2. Bonus Flower
- **Elemen Flower (`F`):** `energy + 2`

> **Catatan:** Aturan-aturan ini diterapkan saat Anda menjelajahi sequence, membandingkan setiap elemen dengan tetangganya yang berdekatan.

## 📤 Return Value

Function mengembalikan **number** yang merepresentasikan level energi akhir setelah menjelajahi seluruh sequence.

## 💡 Contoh Walkthrough

```javascript
// Contoh sequence: "FRT"
// Energi awal: 10

// Langkah 1: F (Flower) → energy + 2 = 12
// Langkah 2: F vs R (berbeda) → energy - 1 = 11  
// Langkah 3: R vs T (berbeda) → energy - 1 = 10
// Energi akhir: 10
```

## 🎨 Tips Implementasi

- Proses sequence karakter demi karakter
- Lacak elemen sebelumnya untuk perbandingan
- Terapkan bonus flower setiap kali bertemu dengan 'F'
- Tangani edge case (sequence kosong, elemen tunggal)

## 🧪 Pertimbangan Testing

Pertimbangkan untuk testing dengan:
- Sequence kosong
- Sequence dengan elemen tunggal
- Sequence dengan elemen berulang
- Sequence dengan semua elemen berbeda
- Sequence yang mengandung multiple flower

---

*Selamat coding, penjelajah alam! 🌲✨*
