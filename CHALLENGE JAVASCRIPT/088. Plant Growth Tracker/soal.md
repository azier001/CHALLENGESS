# 🌱 Plant Growth Tracker

## 📊 Overview Challenge

**Difficulty Level:** `Easy`  
**Domain:** Penelitian Pertanian & Embriologi Tanaman  
**Function Name:** `updatePlantGrowth`

---

## 🎯 Tujuan

Buatlah sistem yang melacak tahapan pertumbuhan berbagai tanaman untuk pusat penelitian pertanian. Para ilmuwan perlu memantau perkembangan tanaman dari benih hingga panen, dan function Anda akan membantu mengotomatisasi pelacakan progres tahapan.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function updatePlantGrowth(plantInfo)
```

### Parameters
- **`plantInfo`** *(string)*: Input string dalam format `"PlantName:Stage"`
  - `PlantName`: Nama tanaman yang dilacak
  - `Stage`: Angka satu digit (0-9) yang merepresentasikan tahap pertumbuhan saat ini

---

## ⚙️ Requirements Function

Function `updatePlantGrowth` harus melakukan operasi berikut:

1. **Extract Informasi**
   - Parse nama tanaman dari input string
   - Extract nomor tahap pertumbuhan saat ini

2. **Update Growth Stage**
   - Increment tahap pertumbuhan sebesar 1
   - **Pengecualian:** Jika stage sudah 9 (fully grown), tetap di 9

3. **Tambah Deskripsi Stage**
   - Mapping nomor stage baru ke deskripsi yang sesuai
   - Format output dengan informasi yang telah diupdate

4. **Return Result**
   - Return formatted string: `"PlantName:NewStage - Description"`

---

## 🌿 Referensi Growth Stage

| Stage | Description | Fase Perkembangan Tanaman |
|-------|-------------|---------------------------|
| **0** | Seed | Kondisi awal yang dorman |
| **1** | Germination | Benih mulai bertunas |
| **2** | Seedling | Tanaman muda muncul |
| **3** | Vegetative | Daun dan batang berkembang |
| **4** | Budding | Kuncup bunga terbentuk |
| **5** | Flowering | Bunga mekar |
| **6** | Pollination | Proses reproduksi |
| **7** | Fruit development | Buah mulai terbentuk |
| **8** | Ripening | Buah matang |
| **9** | Harvest-ready | Sepenuhnya matang, siap dipanen |

---

## 📝 Format Input/Output

### Format Input
```
"PlantName:Stage"
```

### Format Output
```
"PlantName:NewStage - Description"
```

### Contoh Flow
```
Input:  "Tomato:3"
Output: "Tomato:4 - Budding"
```

---

## 🧪 Skenario Testing

Pertimbangkan testing dengan skenario berikut:
- **Progres tahap awal:** `"Carrot:0"` → `"Carrot:1 - Germination"`
- **Perkembangan tahap menengah:** `"Rose:5"` → `"Rose:6 - Pollination"`
- **Handling stage maksimum:** `"Apple:9"` → `"Apple:9 - Harvest-ready"`
- **Nama tanaman beragam:** Spesies tanaman berbeda pada stage yang berbeda

---

## 🎯 Kriteria Sukses

Function Anda harus:
- ✅ Parse format input string dengan benar
- ✅ Handle logic progres stage dengan akurat
- ✅ Apply deskripsi stage yang tepat
- ✅ Maintain stage 9 sebagai maksimum (tidak overflow)
- ✅ Return output string dengan format yang benar
- ✅ Bekerja dengan kombinasi nama tanaman dan stage yang valid
