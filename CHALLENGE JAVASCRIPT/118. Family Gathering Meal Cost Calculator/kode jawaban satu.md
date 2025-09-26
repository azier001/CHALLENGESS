# 🍽️ Dokumentasi Fungsi `calculateMealCost`

## 📝 Deskripsi

Fungsi `calculateMealCost` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung total biaya makanan berdasarkan jumlah tamu dan jenis makanan yang dipilih. Fungsi ini sangat berguna untuk perencanaan acara, katering, atau estimasi biaya makan dengan validasi yang lebih ketat untuk jenis makanan.

## ⚙️ Parameter

Fungsi ini menerima 2 parameter:

| Parameter | Tipe Data | Deskripsi | Contoh |
|-----------|-----------|-----------|---------|
| `guestCount` | Number | Jumlah tamu yang akan makan | `50`, `100`, `25` |
| `mealType` | String | Jenis makanan yang dipilih | `"vegetarian"` atau `"non-vegetarian"` |

## 💰 Tabel Harga per Orang

| Jenis Makanan | Harga per Orang | Status |
|---------------|-----------------|---------|
| Vegetarian | $10 | ✅ Didukung |
| Non-Vegetarian | $15 | ✅ Didukung |
| Lainnya | $0 | ❌ Tidak didukung |

## 📋 Kode Fungsi

```javascript
function calculateMealCost(guestCount, mealType) {
  // Inisialisasi harga per orang dengan nilai 0
  let costPerPerson = 0;
  
  // Memeriksa jenis makanan dan menentukan harga per orang
  if (mealType === "vegetarian") {
    costPerPerson = 10; // Harga untuk makanan vegetarian
  } else if (mealType === "non-vegetarian") {
    costPerPerson = 15; // Harga untuk makanan non-vegetarian
  }
  // Jika jenis makanan tidak dikenali, costPerPerson tetap 0
  
  // Menghitung total biaya dengan mengalikan harga per orang dengan jumlah tamu
  const totalCost = costPerPerson * guestCount;
  
  // Mengembalikan total biaya
  return totalCost;
}
```

## 🔄 Cara Kerja

1. **Inisialisasi**: Fungsi memulai dengan menetapkan `costPerPerson = 0`
2. **Pengecekan Jenis Makanan**: 
   - Jika `mealType` adalah `"vegetarian"` → harga per orang = $10
   - Jika `mealType` adalah `"non-vegetarian"` → harga per orang = $15
   - Jika tidak sesuai kedua kondisi di atas → harga per orang tetap $0
3. **Perhitungan Total**: Mengalikan `costPerPerson` dengan `guestCount`
4. **Return**: Mengembalikan total biaya

## 📊 Contoh Penggunaan dan Output

### Contoh 1: Makanan Vegetarian
```javascript
const totalCost1 = calculateMealCost(30, "vegetarian");
console.log(totalCost1); // Output: 300
```
**Penjelasan**: 30 tamu × $10 (vegetarian) = $300

### Contoh 2: Makanan Non-Vegetarian
```javascript
const totalCost2 = calculateMealCost(25, "non-vegetarian");
console.log(totalCost2); // Output: 375
```
**Penjelasan**: 25 tamu × $15 (non-vegetarian) = $375

### Contoh 3: Jenis Makanan Tidak Dikenali
```javascript
const totalCost3 = calculateMealCost(50, "seafood");
console.log(totalCost3); // Output: 0
```
**Penjelasan**: 50 tamu × $0 (jenis tidak dikenali) = $0

### Contoh 4: Input Kosong atau Salah
```javascript
const totalCost4 = calculateMealCost(40, "");
console.log(totalCost4); // Output: 0

const totalCost5 = calculateMealCost(35, "vegan");
console.log(totalCost5); // Output: 0
```
**Penjelasan**: Jenis makanan tidak sesuai dengan yang didukung, hasil = $0

## 🎯 Tips Penggunaan

- **Untuk Pemula**: Pastikan parameter `guestCount` berupa angka positif
- **Case Sensitive**: Parameter `mealType` harus tepat `"vegetarian"` atau `"non-vegetarian"` (huruf kecil semua)
- **Validasi Ketat**: Fungsi hanya mengenali 2 jenis makanan spesifik, selain itu akan menghasilkan biaya $0

## 🚨 Hal yang Perlu Diperhatikan

- **Validasi Input**: Fungsi tidak melakukan validasi untuk `guestCount`, pastikan input berupa angka positif
- **Jenis Makanan Terbatas**: Hanya menerima `"vegetarian"` dan `"non-vegetarian"` secara eksplisit
- **Return Value 0**: Jika jenis makanan tidak dikenali, fungsi akan mengembalikan $0
- **Typo Sensitive**: Kesalahan pengetikan pada `mealType` akan menghasilkan biaya $0

## ⚠️ Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Sebelumnya | Versi Saat Ini |
|-------|------------------|----------------|
| Default Behavior | Non-vegetarian ($15) | Return 0 jika tidak dikenali |
| Validasi | Lebih permisif | Lebih ketat |
| Error Handling | Implicit default | Explicit zero return |

## 📈 Contoh Implementasi dalam Konteks Nyata

```javascript
// Simulasi perhitungan untuk berbagai acara
const weddingCost = calculateMealCost(150, "non-vegetarian");
const birthdayCost = calculateMealCost(20, "vegetarian");
const invalidCost = calculateMealCost(80, "mixed"); // Akan menghasilkan 0

console.log(`Biaya katering pernikahan: $${weddingCost}`);     // $2,250
console.log(`Biaya katering ulang tahun: $${birthdayCost}`);   // $200
console.log(`Biaya katering tidak valid: $${invalidCost}`);    // $0

// Contoh dengan validasi tambahan
function safeMealCostCalculator(guestCount, mealType) {
  if (guestCount <= 0) {
    console.log("Error: Jumlah tamu harus lebih dari 0");
    return 0;
  }
  
  const cost = calculateMealCost(guestCount, mealType);
  
  if (cost === 0 && guestCount > 0) {
    console.log(`Warning: Jenis makanan "${mealType}" tidak dikenali`);
  }
  
  return cost;
}
```

## 🛠️ Rekomendasi Pengembangan

Untuk meningkatkan fungsi ini, pertimbangkan untuk:
- Menambahkan validasi input untuk `guestCount`
- Menambahkan lebih banyak jenis makanan
- Menambahkan error handling yang lebih baik
- Mengembalikan object dengan detail breakdown biaya
