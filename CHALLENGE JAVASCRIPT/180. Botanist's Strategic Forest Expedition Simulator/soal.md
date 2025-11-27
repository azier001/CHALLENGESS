# 🌲 Simulator Ekspedisi Strategis Botanis di Hutan Kuno

> **Level Tantangan:** Medium

---

## 📋 Ringkasan

Buat sebuah function bernama `exploreAncientForest` yang mensimulasikan ekspedisi seorang botanis melalui hutan kuno. Tantangan ini menggabungkan teknik hashing tingkat lanjut, control flow, dan konsep game theory untuk memodelkan pengambilan keputusan strategis dalam manajemen resource dan eksplorasi.

---

## 🎯 Tujuan

Botanis harus membuat keputusan strategis tentang area mana yang akan dieksplorasi, menyeimbangkan keinginan untuk menemukan spesies langka dengan kebutuhan untuk menghemat resource dan menghindari potensi bahaya.

---

## 📝 Function Signature

```javascript
function exploreAncientForest(forestMap, energyLevel, maxDays, explorationStrategy) {
  // Implementasi Anda di sini
}
```

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `forestMap` | `Array<Array<string>>` | Array 2D yang merepresentasikan layout hutan, di mana setiap cell berisi informasi tentang terrain dan penemuan potensial |
| `energyLevel` | `number` | Integer yang merepresentasikan level energi awal botanis |
| `maxDays` | `number` | Integer yang merepresentasikan jumlah hari maksimum untuk ekspedisi |
| `explorationStrategy` | `string` | Strategi eksplorasi yang dipilih botanis: `'cautious'`, `'balanced'`, atau `'aggressive'` |

---

## 📤 Return Value

Function harus mengembalikan object dengan struktur berikut:

```javascript
{
  rareSpeciesDiscovered: number,      // Jumlah spesies langka yang ditemukan
  totalObservations: number,          // Total jumlah observasi yang dilakukan
  remainingEnergy: number,            // Level energi yang tersisa
  significantDiscoveries: string[]    // Array penemuan paling signifikan
}
```

---

## 🎮 Persyaratan Implementasi

### 1. **Manajemen Hash Table**
- Buat hash table (object) untuk menyimpan dan mengambil informasi tentang spesies yang ditemukan dan lokasinya secara efisien
- Gunakan hash table untuk lookup cepat dan menghindari penemuan duplikat

### 2. **Advanced Control Flow**
- Iterasi melalui forest map selama jumlah hari yang ditentukan atau hingga energi habis
- Implementasikan penggunaan strategis statement `break` dan `continue` untuk mengoptimalkan path eksplorasi
- Gunakan exploration strategy untuk menentukan prioritas movement dan observasi

### 3. **Konsep Game Theory**
- Modelkan pengambilan keputusan dengan mempertimbangkan:
  - Kelangkaan spesies
  - Konservasi energi
  - Potensi risiko
  - Expected value dari mengeksplorasi area berbeda

### 4. **Optimasi Path**
- Gunakan statement `break` dan `continue` untuk:
  - Melewati area berbahaya atau bernilai rendah
  - Memprioritaskan lokasi bernilai tinggi
  - Mengoptimalkan pengeluaran energi

### 5. **Pelacakan Data**
- Update counter untuk spesies yang ditemukan dan observasi yang dilakukan
- Lacak penemuan signifikan sepanjang ekspedisi
- Monitor level energi yang tersisa

---

## 💡 Konsep Kunci yang Harus Diterapkan

### 🗂️ Hashing
- Penyimpanan dan pengambilan data spesies yang efisien
- Deteksi duplikat yang cepat
- Indexing berbasis lokasi

### 🔄 Control Flow
- Manajemen loop yang strategis
- Path eksplorasi kondisional
- Kondisi terminasi dini

### 🎲 Game Theory
- Penilaian risiko vs reward
- Strategi alokasi resource
- Optimasi keputusan di bawah batasan

---

## 🎭 Strategi Eksplorasi

### 🛡️ Cautious (Hati-hati)
- Memprioritaskan konservasi energi
- Menghindari area berisiko tinggi
- Fokus pada penemuan yang terjamin

### ⚖️ Balanced (Seimbang)
- Menyeimbangkan risiko dan reward
- Pengeluaran energi moderat
- Campuran eksplorasi aman dan petualangan

### ⚔️ Aggressive (Agresif)
- Memaksimalkan potensi penemuan
- Mengambil risiko yang diperhitungkan
- Konsumsi energi lebih tinggi

---

## ⚠️ Catatan Penting

- Pastikan implementasi efisien dengan penggunaan hash table yang tepat
- Tangani edge case (energi nol, hutan kosong, dll.)
- Optimalkan untuk performa dengan forest map yang besar
- Buat keputusan strategis berdasarkan exploration strategy yang dipilih
- Jangan pernah mengakses cell yang undefined di forest map

---

## 🧪 Contoh Penggunaan

```javascript
const forestMap = [
  ['tree', 'rare_orchid', 'bush'],
  ['danger', 'common_fern', 'rare_moss'],
  ['tree', 'water', 'rare_mushroom']
];

const result = exploreAncientForest(forestMap, 100, 3, 'balanced');

console.log(result);
// Output:
// {
//   rareSpeciesDiscovered: 3,
//   totalObservations: 5,
//   remainingEnergy: 45,
//   significantDiscoveries: ['rare_orchid', 'rare_moss', 'rare_mushroom']
// }
```

---

## 🏆 Kriteria Sukses

✅ Mengimplementasikan hash table dengan benar untuk pelacakan spesies  
✅ Menggunakan statement control flow secara strategis  
✅ Menerapkan game theory dalam pengambilan keputusan  
✅ Mengembalikan hasil ekspedisi yang akurat  
✅ Menangani semua exploration strategy dengan tepat  
✅ Mengoptimalkan performa untuk input besar  

---

**Semoga sukses dengan ekspedisi Anda! 🌿🔍**
