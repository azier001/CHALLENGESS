# 🌲 Dokumentasi Fungsi `exploreAncientForest`

## 📋 Deskripsi

Fungsi `exploreAncientForest` adalah sebuah fungsi untuk menjelajahi hutan kuno dan menemukan berbagai spesies. Fungsi ini mensimulasikan ekspedisi penelitian dengan berbagai strategi penjelajahan yang mempengaruhi konsumsi energi dan hasil observasi.

Fungsi akan menelusuri peta hutan (`forestMap`) selama beberapa hari dengan strategi yang dipilih, sambil memperhatikan tingkat energi yang tersisa. Semakin agresif strategi eksplorasi, semakin banyak energi yang digunakan tetapi juga semakin banyak nilai observasi yang didapat.

---

## 🎯 Fitur Utama

- ✅ Eksplorasi peta hutan 2D
- ✅ Tiga strategi eksplorasi (cautious, balanced, aggressive)
- ✅ Sistem manajemen energi
- ✅ Deteksi spesies langka
- ✅ Pencatatan penemuan signifikan
- ✅ Penghindaran area berbahaya

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `forestMap` | `Array<Array<string>>` | Peta hutan 2D yang berisi nama-nama spesies. Setiap elemen adalah string yang mewakili spesies di lokasi tersebut. |
| `energyLevel` | `number` | Jumlah energi awal yang dimiliki penjelajah. Energi akan berkurang setiap kali melakukan observasi. |
| `maxDays` | `number` | Jumlah maksimal hari untuk melakukan eksplorasi. |
| `explorationStrategy` | `string` | Strategi eksplorasi yang digunakan: `"cautious"`, `"balanced"`, atau `"aggressive"`. |

---

## 🎮 Strategi Eksplorasi

| Strategi | Biaya Energi | Nilai Observasi | Karakteristik |
|----------|--------------|-----------------|---------------|
| **cautious** 🐢 | 10 | 1.0 | Menghindari semua area berbahaya, berhenti setelah 5 penemuan signifikan |
| **balanced** ⚖️ | 15 | 1.5 | Menghindari 50% area berbahaya (acak), nilai observasi sedang |
| **aggressive** 🦅 | 20 | 2.0 | Tidak menghindari area berbahaya, nilai observasi tertinggi |

---

## 📤 Return Value

Fungsi mengembalikan objek dengan properti berikut:

| Properti | Tipe | Deskripsi |
|----------|------|-----------|
| `rareSpeciesDiscovered` | `number` | Jumlah total spesies langka yang ditemukan |
| `totalObservations` | `number` | Total nilai observasi (dibulatkan ke bawah) |
| `remainingEnergy` | `number` | Sisa energi setelah eksplorasi selesai (minimum 0) |
| `significantDiscoveries` | `Array<string>` | Array berisi maksimal 5 spesies signifikan pertama yang ditemukan |

---

## 💻 Code Fungsi

```javascript
function exploreAncientForest(forestMap, energyLevel, maxDays, explorationStrategy) {
  // Objek untuk menyimpan spesies yang ditemukan beserta lokasinya
  const discoveredSpecies = {};
  
  // Counter untuk spesies langka
  let rareSpeciesDiscovered = 0;
  
  // Total nilai observasi
  let totalObservations = 0;
  
  // Array untuk menyimpan penemuan signifikan
  let significantDiscoveries = [];
  
  // Biaya energi untuk setiap strategi
  const energyCost = {
    cautious: 10,
    balanced: 15,
    aggressive: 20
  };
  
  // Nilai observasi untuk setiap strategi
  const observationValue = {
    cautious: 1,
    balanced: 1.5,
    aggressive: 2
  };
  
  // Fungsi helper untuk mengecek apakah spesies langka
  const isRare = (species) => species.includes("rare");
  
  // Loop untuk setiap hari eksplorasi
  for (let day = 0; day < maxDays && energyLevel > 0; day++) {
    
    // Loop untuk setiap baris di peta hutan
    for (let i = 0; i < forestMap.length && energyLevel > 0; i++) {
      
      // Loop untuk setiap kolom di peta hutan
      for (let j = 0; j < forestMap[i].length && energyLevel > 0; j++) {
        const currentSpecies = forestMap[i][j];
        
        // Penanganan area berbahaya berdasarkan strategi
        if (currentSpecies === "dangerous") {
          if (explorationStrategy === "cautious") {
            continue; // Lewati area berbahaya
          } else if (explorationStrategy === "balanced" && Math.random() < 0.5) {
            continue; // 50% kemungkinan melewati area berbahaya
          }
        }
        
        // Kurangi energi sesuai strategi
        energyLevel -= energyCost[explorationStrategy];
        
        // Hentikan jika energi habis
        if (energyLevel <= 0) break;
        
        // Catat spesies yang ditemukan
        if (!discoveredSpecies[currentSpecies]) {
          discoveredSpecies[currentSpecies] = [];
        }
        discoveredSpecies[currentSpecies].push([i, j]);
        
        // Tambah nilai observasi
        totalObservations += observationValue[explorationStrategy];
        
        // Cek apakah spesies langka
        if (isRare(currentSpecies)) {
          rareSpeciesDiscovered++;
          significantDiscoveries.push(currentSpecies);
        }
        
        // Berhenti jika strategi cautious dan sudah menemukan 5 penemuan signifikan
        if (significantDiscoveries.length >= 5 && explorationStrategy === "cautious") {
          break;
        }
      }
    }
  }
  
  // Batasi penemuan signifikan maksimal 5
  significantDiscoveries = significantDiscoveries.slice(0, 5);
  
  // Return hasil eksplorasi
  return {
    rareSpeciesDiscovered,
    totalObservations: Math.floor(totalObservations),
    remainingEnergy: Math.max(0, energyLevel),
    significantDiscoveries
  };
}
```

---

## 📝 Contoh Penggunaan

### Contoh 1: Strategi Cautious

```javascript
const forestMap = [
  ["oak", "rare_bird", "dangerous"],
  ["pine", "rare_flower", "oak"],
  ["dangerous", "rare_deer", "pine"]
];

const result = exploreAncientForest(forestMap, 100, 2, "cautious");

console.log(result);
```

**Output:**
```javascript
{
  rareSpeciesDiscovered: 3,
  totalObservations: 5,
  remainingEnergy: 50,
  significantDiscoveries: ["rare_bird", "rare_flower", "rare_deer"]
}
```

**Penjelasan:**
- Strategi `cautious` melewati area "dangerous"
- Biaya energi per observasi: 10
- Nilai observasi per lokasi: 1
- Menemukan 3 spesies langka: rare_bird, rare_flower, rare_deer
- Berhenti setelah menemukan 5 observasi karena strategi cautious

---

### Contoh 2: Strategi Aggressive

```javascript
const forestMap = [
  ["oak", "rare_bird", "dangerous"],
  ["pine", "rare_flower", "oak"]
];

const result = exploreAncientForest(forestMap, 100, 1, "aggressive");

console.log(result);
```

**Output:**
```javascript
{
  rareSpeciesDiscovered: 2,
  totalObservations: 12,
  remainingEnergy: 0,
  significantDiscoveries: ["rare_bird", "rare_flower"]
}
```

**Penjelasan:**
- Strategi `aggressive` tidak melewati area "dangerous"
- Biaya energi per observasi: 20
- Nilai observasi per lokasi: 2
- Total lokasi: 6 × 2 = 12 observasi
- Energi habis setelah 5 lokasi (100 - 5×20 = 0)

---

### Contoh 3: Strategi Balanced

```javascript
const forestMap = [
  ["rare_butterfly", "oak"],
  ["dangerous", "rare_orchid"]
];

const result = exploreAncientForest(forestMap, 50, 1, "balanced");

console.log(result);
```

**Output (dapat bervariasi):**
```javascript
{
  rareSpeciesDiscovered: 2,
  totalObservations: 4,
  remainingEnergy: 5,
  significantDiscoveries: ["rare_butterfly", "rare_orchid"]
}
```

**Penjelasan:**
- Strategi `balanced` memiliki 50% kemungkinan melewati "dangerous"
- Biaya energi per observasi: 15
- Nilai observasi per lokasi: 1.5
- Output dapat bervariasi karena random pada penghindaran area berbahaya

---

## 🔍 Catatan Penting

1. **Spesies Langka**: Spesies dianggap langka jika nama spesies mengandung kata "rare" (contoh: "rare_bird", "rare_flower")

2. **Area Berbahaya**: Lokasi dengan nilai "dangerous" akan ditangani berbeda tergantung strategi:
   - Cautious: Selalu dihindari
   - Balanced: 50% kemungkinan dihindari
   - Aggressive: Tidak dihindari

3. **Pemberhentian Dini**: Strategi cautious akan berhenti lebih awal setelah menemukan 5 penemuan signifikan

4. **Energi Minimum**: Sisa energi tidak akan pernah negatif (minimum 0)

5. **Pembulatan**: Total observasi dibulatkan ke bawah menggunakan `Math.floor()`

---

## 🎓 Tips Penggunaan

- 🔋 **Kelola Energi**: Pilih strategi sesuai dengan energi yang tersedia
- 🎯 **Eksplorasi Efisien**: Gunakan strategi `cautious` jika hanya butuh penemuan cepat
- 💪 **Maksimalkan Hasil**: Gunakan strategi `aggressive` jika ingin nilai observasi tinggi
- ⚖️ **Seimbang**: Strategi `balanced` cocok untuk situasi standar

---

## 📊 Perbandingan Strategi

| Aspek | Cautious | Balanced | Aggressive |
|-------|----------|----------|------------|
| Keamanan | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐ |
| Efisiensi Energi | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐ |
| Nilai Observasi | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Kecepatan | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ |

---

**Dibuat dengan ❤️ untuk membantu pemula memahami fungsi JavaScript**
