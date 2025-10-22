# 📋 Dokumentasi Fungsi `benchQualityChecker`

## 🎯 Deskripsi

Fungsi `benchQualityChecker` digunakan untuk memeriksa kualitas lapisan coating pada bangku (bench) berdasarkan ketebalan coating dan tingkat lalu lintas (traffic) penggunaan bangku tersebut. Fungsi ini akan memberikan rekomendasi kondisi dan tindakan yang perlu dilakukan.

## 📝 Sintaks

```javascript
benchQualityChecker(coatingThickness, isHighTraffic)
```

## 🔧 Parameter

| Parameter | Tipe Data | Wajib | Deskripsi |
|-----------|-----------|-------|-----------|
| `coatingThickness` | Number | Ya | Ketebalan lapisan coating dalam mikrometer (μm). Nilai harus berupa angka positif. |
| `isHighTraffic` | Boolean | Ya | Menunjukkan apakah bangku berada di area dengan lalu lintas tinggi. `true` untuk area ramai, `false` untuk area sepi. |

## 📊 Tabel Kategori Kualitas

| Ketebalan (μm) | Kondisi Traffic | Status | Rekomendasi |
|----------------|-----------------|--------|-------------|
| < 50 | Semua kondisi | ❌ Terrible | Replace immediately! (Ganti segera!) |
| 50 - 100 | High Traffic | ⚠️ Poor | Needs recoating soon (Perlu dicat ulang segera) |
| 50 - 100 | Low Traffic | ✅ Acceptable | Monitor closely (Pantau dengan teliti) |
| 101 - 150 | Semua kondisi | ✅ Good | No action needed (Tidak perlu tindakan) |
| > 150 | Semua kondisi | 🌟 Excellent | Overcoated! (Terlalu tebal!) |

## 💡 Penjelasan Detail

### Kategori Kualitas:

1. **Terrible (< 50 μm)** 🔴
   - Coating terlalu tipis dan tidak aman
   - Bangku harus segera diganti
   - Tidak peduli tingkat lalu lintas, kondisi ini berbahaya

2. **Poor (50-100 μm, High Traffic)** 🟠
   - Coating masih cukup tipis untuk area ramai
   - Perlu dilakukan pengecatan ulang dalam waktu dekat
   - Risiko kerusakan lebih cepat karena banyak digunakan

3. **Acceptable (50-100 μm, Low Traffic)** 🟡
   - Coating cukup untuk area yang jarang digunakan
   - Perlu pemantauan berkala
   - Belum perlu tindakan segera

4. **Good (101-150 μm)** 🟢
   - Ketebalan coating ideal
   - Bangku dalam kondisi baik
   - Tidak perlu tindakan apapun

5. **Excellent (> 150 μm)** 💙
   - Coating terlalu tebal (overcoated)
   - Mungkin pemborosan material
   - Secara kualitas sangat baik, tapi tidak efisien

## 📄 Kode Lengkap

```javascript
function benchQualityChecker(coatingThickness, isHighTraffic) {
  
  // Jika ketebalan coating kurang dari 50 μm
  if (coatingThickness < 50) {
    return "Terrible - Replace immediately!";
  } 
  
  // Jika ketebalan coating antara 50-100 μm
  else if (coatingThickness >= 50 && coatingThickness <= 100) {
    
    // Cek apakah area dengan lalu lintas tinggi
    if (isHighTraffic) {
      return "Poor - Needs recoating soon";
    } else {
      return "Acceptable - Monitor closely";
    }
  } 
  
  // Jika ketebalan coating antara 101-150 μm
  else if (coatingThickness >= 101 && coatingThickness <= 150) {
    return "Good - No action needed";
  } 
  
  // Jika ketebalan coating lebih dari 150 μm
  else {
    return "Excellent - Overcoated!";
  }
}
```

## 🧪 Contoh Penggunaan

### Contoh 1: Coating Sangat Tipis
```javascript
const result1 = benchQualityChecker(30, false);
console.log(result1);
// Output: "Terrible - Replace immediately!"
```
**Penjelasan:** Ketebalan hanya 30 μm, terlalu tipis dan berbahaya.

---

### Contoh 2: Area Ramai dengan Coating Tipis
```javascript
const result2 = benchQualityChecker(75, true);
console.log(result2);
// Output: "Poor - Needs recoating soon"
```
**Penjelasan:** Ketebalan 75 μm di area ramai memerlukan perhatian segera.

---

### Contoh 3: Area Sepi dengan Coating Tipis
```javascript
const result3 = benchQualityChecker(80, false);
console.log(result3);
// Output: "Acceptable - Monitor closely"
```
**Penjelasan:** Ketebalan 80 μm di area sepi masih bisa diterima dengan pemantauan.

---

### Contoh 4: Coating Ideal
```javascript
const result4 = benchQualityChecker(125, true);
console.log(result4);
// Output: "Good - No action needed"
```
**Penjelasan:** Ketebalan 125 μm adalah kondisi ideal, tidak perlu tindakan.

---

### Contoh 5: Coating Terlalu Tebal
```javascript
const result5 = benchQualityChecker(200, false);
console.log(result5);
// Output: "Excellent - Overcoated!"
```
**Penjelasan:** Ketebalan 200 μm sangat baik namun mungkin berlebihan.

---

## 📌 Catatan Penting

- ⚠️ Fungsi ini mengasumsikan input `coatingThickness` berupa angka positif
- ⚠️ Parameter `isHighTraffic` harus berupa boolean (`true` atau `false`)
- 💡 Parameter `isHighTraffic` hanya berpengaruh pada ketebalan 50-100 μm
- 🔍 Untuk ketebalan < 50 μm, 101-150 μm, dan > 150 μm, tingkat traffic tidak mempengaruhi hasil

## 🎓 Tips untuk Pemula

1. **Boolean** adalah tipe data yang hanya memiliki dua nilai: `true` (benar) atau `false` (salah)
2. **μm (mikrometer)** adalah satuan ukuran yang sangat kecil, 1 μm = 0.001 mm
3. **Traffic** dalam konteks ini berarti seberapa sering bangku digunakan oleh orang
4. Fungsi ini menggunakan **conditional statement** (if-else) untuk membuat keputusan berdasarkan kondisi tertentu

## 🔗 Return Value

| Tipe | Deskripsi |
|------|-----------|
| String | Mengembalikan teks status dan rekomendasi dalam bahasa Inggris |

---

**Dibuat untuk:** Maintenance Tim dan Quality Control  
**Versi:** 1.0  
**Bahasa:** JavaScript
