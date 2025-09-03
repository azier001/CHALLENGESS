# 🥾 Dokumentasi Fungsi `calculateHikeScore`

## 📋 Deskripsi

Fungsi `calculateHikeScore` adalah sebuah fungsi JavaScript yang menghitung skor total dari perjalanan hiking berdasarkan beberapa faktor seperti jumlah bukit yang didaki, jarak tempuh, respons terhadap peluit ranger, dan berbagai bonus serta penalti yang berlaku.

Fungsi ini sangat berguna untuk sistem penilaian atau gamifikasi dalam aplikasi hiking, outdoor adventure, atau tracking aktivitas pendakian gunung.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `hills` | `number` | Jumlah bukit yang berhasil didaki selama perjalanan |
| `distance` | `number` | Jarak total yang ditempuh dalam kilometer (km) |
| `whistleResponse` | `boolean` | Status respons terhadap peluit ranger (`true` = benar, `false` = salah) |

---

## 📊 Sistem Penilaian

### 🎯 Komponen Skor

| Kategori | Deskripsi | Nilai |
|----------|-----------|-------|
| **Skor Dasar** | Setiap bukit yang didaki | +10 poin |
| **Bonus Jarak** | Setiap kilometer penuh yang ditempuh | +5 poin |
| **Bonus Peluit** | Respons benar terhadap peluit ranger | +50 poin |
| **Bonus Daya Tahan** | Jika mendaki lebih dari 10 bukit | +100 poin |
| **Penalti Jarak Pendek** | Jika jarak tempuh kurang dari 5 km | -20 poin |

---

## 💾 Kode Sumber

```javascript
function calculateHikeScore(hills, distance, whistleResponse) {
  let score = 0;
  
  // Skor dasar: 10 poin untuk setiap bukit yang didaki
  score += hills * 10;
  
  // Bonus jarak: 5 poin untuk setiap kilometer penuh yang ditempuh
  score += Math.floor(distance) * 5;
  
  // Bonus peluit ranger: Jika pendaki merespons dengan benar terhadap peluit, tambah 50 poin
  if (whistleResponse) {
    score += 50;
  }
  
  // Bonus daya tahan: Jika jumlah bukit yang didaki lebih dari 10, tambah 100 poin ekstra
  if (hills > 10) {
    score += 100;
  }
  
  // Penalti hiking pendek: Jika total jarak yang ditempuh kurang dari 5 km, kurangi 20 poin
  if (distance < 5) {
    score -= 20;
  }
  
  return score;
}
```

---

## 🎯 Contoh Penggunaan & Output

### Contoh 1: Pendaki Pemula
```javascript
const skor1 = calculateHikeScore(3, 4.2, false);
console.log(skor1); // Output: 30
```

**Penjelasan:**
- Skor dasar: 3 × 10 = 30 poin
- Bonus jarak: Math.floor(4.2) × 5 = 20 poin
- Bonus peluit: Tidak dapat (0 poin)
- Bonus daya tahan: Tidak dapat (0 poin)
- Penalti jarak pendek: -20 poin
- **Total: 30 + 20 + 0 + 0 - 20 = 30 poin**

### Contoh 2: Pendaki Berpengalaman
```javascript
const skor2 = calculateHikeScore(12, 8.7, true);
console.log(skor2); // Output: 335
```

**Penjelasan:**
- Skor dasar: 12 × 10 = 120 poin
- Bonus jarak: Math.floor(8.7) × 5 = 40 poin
- Bonus peluit: +50 poin
- Bonus daya tahan: +100 poin (karena hills > 10)
- Penalti jarak pendek: Tidak ada (0 poin)
- **Total: 120 + 40 + 50 + 100 + 0 = 310 poin**

### Contoh 3: Pendaki Ahli
```javascript
const skor3 = calculateHikeScore(15, 12.5, true);
console.log(skor3); // Output: 360
```

**Penjelasan:**
- Skor dasar: 15 × 10 = 150 poin
- Bonus jarak: Math.floor(12.5) × 5 = 60 poin
- Bonus peluit: +50 poin
- Bonus daya tahan: +100 poin (karena hills > 10)
- Penalti jarak pendek: Tidak ada (0 poin)
- **Total: 150 + 60 + 50 + 100 + 0 = 360 poin**

### Contoh 4: Hiking Singkat Tanpa Respons
```javascript
const skor4 = calculateHikeScore(2, 3.8, false);
console.log(skor4); // Output: 15
```

**Penjelasan:**
- Skor dasar: 2 × 10 = 20 poin
- Bonus jarak: Math.floor(3.8) × 5 = 15 poin
- Bonus peluit: Tidak dapat (0 poin)
- Bonus daya tahan: Tidak dapat (0 poin)
- Penalti jarak pendek: -20 poin (karena distance < 5)
- **Total: 20 + 15 + 0 + 0 - 20 = 15 poin**

---

## 💡 Tips Penggunaan

1. **Input Validation**: Pastikan parameter `hills` dan `distance` berupa angka positif
2. **Boolean Parameter**: Parameter `whistleResponse` harus berupa boolean (`true` atau `false`)
3. **Desimal Jarak**: Fungsi menggunakan `Math.floor()` untuk jarak, jadi 4.9 km tetap dihitung sebagai 4 km
4. **Skor Minimum**: Skor bisa menjadi negatif jika hiking sangat singkat dengan parameter rendah

---

## 🚀 Return Value

Fungsi ini mengembalikan nilai bertipe `number` yang merupakan total skor hiking berdasarkan perhitungan semua komponen di atas.
