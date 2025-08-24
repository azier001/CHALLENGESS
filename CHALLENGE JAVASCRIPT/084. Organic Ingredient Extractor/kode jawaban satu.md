# 🌿 Dokumentasi Fungsi `getOrganicIngredients`

## 📋 Deskripsi Fungsi

Fungsi `getOrganicIngredients` adalah sebuah utilitas JavaScript yang digunakan untuk memfilter dan mengambil hanya bahan-bahan organik dari daftar bahan yang diberikan. Fungsi ini sangat berguna untuk aplikasi kuliner, inventori bahan makanan, atau sistem yang memerlukan kategorisasi bahan berdasarkan jenis organik.

## ⚙️ Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `ingredientsList` | `string` | Ya | String yang berisi daftar bahan-bahan yang dipisahkan dengan koma dan spasi (`, `) |

## 🎯 Return Value

- **Tipe**: `string`
- **Nilai**: String yang berisi bahan-bahan organik yang dipisahkan dengan koma dan spasi, atau string kosong jika tidak ada bahan organik yang ditemukan

## 📝 Source Code

```javascript
function getOrganicIngredients(ingredientsList) {
    // Memecah string bahan menjadi array
    const ingredients = ingredientsList.split(', ');
    
    // Memfilter bahan yang dimulai dengan kata "organic" (case-sensitive)
    const organicIngredients = ingredients.filter(ingredient => 
        ingredient.startsWith('organic')
    );
    
    // Mengembalikan hasil sebagai string yang dipisahkan koma, 
    // atau string kosong jika tidak ditemukan
    return organicIngredients.join(', ');
}
```

## 🔍 Cara Kerja Fungsi

Fungsi ini bekerja dalam tiga langkah utama:

1. **Pemecahan String**: Fungsi memecah parameter `ingredientsList` menjadi array menggunakan `split(', ')` dengan pemisah koma dan spasi
2. **Filtering**: Menggunakan method `filter()` untuk mencari bahan yang dimulai dengan kata "organic" menggunakan `startsWith()` yang case-sensitive
3. **Penggabungan**: Hasil filtering digabungkan kembali menjadi string menggunakan `join(', ')` dengan format yang sama seperti input

## 🧪 Contoh Penggunaan dan Output

### Contoh 1: Daftar dengan Bahan Organik
```javascript
const ingredients = "organic tomatoes, regular onions, organic carrots, salt, organic spinach";
const result = getOrganicIngredients(ingredients);
console.log(result);
// Output: "organic tomatoes, organic carrots, organic spinach"
```

### Contoh 2: Tidak Ada Bahan Organik
```javascript
const ingredients = "tomatoes, onions, carrots, salt, pepper";
const result = getOrganicIngredients(ingredients);
console.log(result);
// Output: "" (string kosong)
```

### Contoh 3: Case Sensitive (Hanya Huruf Kecil)
```javascript
const ingredients = "organic apples, Organic Bananas, regular grapes, ORGANIC berries";
const result = getOrganicIngredients(ingredients);
console.log(result);
// Output: "organic apples" (hanya yang huruf kecil semua)
```

### Contoh 4: String Kosong
```javascript
const ingredients = "";
const result = getOrganicIngredients(ingredients);
console.log(result);
// Output: "" (string kosong)
```

### Contoh 5: Satu Bahan Saja
```javascript
const ingredients = "organic lettuce";
const result = getOrganicIngredients(ingredients);
console.log(result);
// Output: "organic lettuce"
```

## 📊 Tabel Perbandingan Input dan Output

| Input | Output | Keterangan |
|-------|--------|------------|
| `"organic milk, sugar, organic eggs"` | `"organic milk, organic eggs"` | Memfilter 2 dari 3 bahan |
| `"flour, water, salt"` | `""` | Tidak ada bahan organik |
| `"Organic flour, organic sugar"` | `"organic sugar"` | Case-sensitive, hanya huruf kecil |
| `"organic"` | `"organic"` | Satu kata saja |

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive**, artinya hanya akan mendeteksi "organic" dengan huruf kecil semua
- Format input harus berupa string dengan pemisah koma dan spasi (`, `)
- Jika tidak ada bahan organik yang ditemukan, fungsi akan mengembalikan string kosong
- Fungsi ini hanya mendeteksi bahan yang **dimulai** dengan kata "organic"
- "Organic" atau "ORGANIC" tidak akan terdeteksi karena case-sensitive

## 🚀 Tips Penggunaan

- Pastikan format input konsisten dengan pemisah `, ` (koma diikuti spasi)
- Pastikan kata "organic" ditulis dengan huruf kecil semua untuk terdeteksi
- Gunakan fungsi ini dalam aplikasi inventori makanan untuk kategorisasi otomatis
- Cocok untuk sistem filtering menu restoran berdasarkan preferensi organik
- Dapat dikombinasikan dengan fungsi lain untuk analisis nutrisi yang lebih kompleks

## 🔧 Saran Pengembangan

Untuk meningkatkan fleksibilitas fungsi, pertimbangkan modifikasi berikut:

```javascript
// Versi case-insensitive
ingredient.toLowerCase().startsWith('organic')

// Versi yang mendeteksi kata "organic" di mana saja
ingredient.toLowerCase().includes('organic')
```
