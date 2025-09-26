# 🍽️ Dokumentasi Fungsi `calculateMealCost`

## 📝 Deskripsi

Fungsi `calculateMealCost` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung total biaya makanan berdasarkan jumlah tamu dan jenis makanan yang dipilih. Fungsi ini sangat berguna untuk perencanaan acara, katering, atau estimasi biaya makan.

## ⚙️ Parameter

Fungsi ini menerima 2 parameter:

| Parameter | Tipe Data | Deskripsi | Contoh |
|-----------|-----------|-----------|---------|
| `guestCount` | Number | Jumlah tamu yang akan makan | `50`, `100`, `25` |
| `mealType` | String | Jenis makanan yang dipilih | `"vegetarian"` atau selain itu |

## 💰 Tabel Harga per Orang

| Jenis Makanan | Harga per Orang |
|---------------|-----------------|
| Vegetarian | $10 |
| Non-Vegetarian (default) | $15 |

## 📋 Kode Fungsi

```javascript
function calculateMealCost(guestCount, mealType) {
    // Menentukan harga per orang berdasarkan jenis makanan
    // Jika vegetarian = $10, selain itu = $15
    const costPerPerson = mealType === "vegetarian" ? 10 : 15;
    
    // Menghitung total biaya dengan mengalikan jumlah tamu dengan harga per orang
    return guestCount * costPerPerson;
}
```

## 🔄 Cara Kerja

1. **Pengecekan Jenis Makanan**: Fungsi akan memeriksa apakah parameter `mealType` bernilai `"vegetarian"`
2. **Penentuan Harga**: 
   - Jika vegetarian → harga per orang = $10
   - Jika bukan vegetarian → harga per orang = $15
3. **Perhitungan Total**: Mengalikan jumlah tamu dengan harga per orang

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

### Contoh 3: Jenis Makanan Lainnya
```javascript
const totalCost3 = calculateMealCost(50, "seafood");
console.log(totalCost3); // Output: 750
```
**Penjelasan**: 50 tamu × $15 (default untuk non-vegetarian) = $750

## 🎯 Tips Penggunaan

- **Untuk Pemula**: Pastikan parameter `guestCount` berupa angka positif
- **Case Sensitive**: Parameter `mealType` harus tepat `"vegetarian"` (huruf kecil semua)
- **Default Behavior**: Jika `mealType` bukan `"vegetarian"`, otomatis dianggap non-vegetarian

## 🚨 Hal yang Perlu Diperhatikan

- Fungsi tidak melakukan validasi input, pastikan `guestCount` adalah angka positif
- Hanya mengenali `"vegetarian"` sebagai jenis makanan khusus
- Semua jenis makanan selain vegetarian akan dikenakan harga yang sama ($15)

## 📈 Contoh Implementasi dalam Konteks Nyata

```javascript
// Simulasi perhitungan untuk berbagai acara
const weddingCost = calculateMealCost(150, "non-vegetarian");
const birthdayCost = calculateMealCost(20, "vegetarian");
const corporateCost = calculateMealCost(80, "mixed");

console.log(`Biaya katering pernikahan: $${weddingCost}`);     // $2,250
console.log(`Biaya katering ulang tahun: $${birthdayCost}`);   // $200
console.log(`Biaya katering kantor: $${corporateCost}`);       // $1,200
```
