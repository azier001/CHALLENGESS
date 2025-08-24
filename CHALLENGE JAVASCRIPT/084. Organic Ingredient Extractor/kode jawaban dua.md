# 🌿 Dokumentasi Fungsi `getOrganicIngredients`

## 📋 Deskripsi Fungsi

Fungsi `getOrganicIngredients` adalah sebuah utilitas JavaScript yang digunakan untuk memfilter dan mengambil hanya bahan-bahan organik dari daftar bahan yang diberikan. Fungsi ini sangat berguna untuk aplikasi kuliner, inventori bahan makanan, atau sistem yang memerlukan kategorisasi bahan berdasarkan jenis organik.

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `ingredientsList` | `string` | String yang berisi daftar bahan-bahan yang dipisahkan dengan koma dan spasi (`, `) |

## 🎯 Return Value

- **Tipe**: `string`
- **Nilai**: String yang berisi bahan-bahan organik yang dipisahkan dengan koma dan spasi, atau string kosong jika tidak ada bahan organik yang ditemukan

## 📝 Source Code

```javascript
function getOrganicIngredients(ingredientsList) {
    // Memecah string bahan menjadi array
    const ingredients = ingredientsList.split(', ');
    
    // Memfilter bahan yang dimulai dengan kata "organic"
    const organicIngredients = ingredients.filter(ingredient => 
        ingredient.toLowerCase().startsWith('organic')
    );
    
    // Mengembalikan hasil sebagai string yang dipisahkan koma, 
    // atau string kosong jika tidak ditemukan
    return organicIngredients.join(', ');
}
```

## 🔍 Cara Kerja Fungsi

1. **Pemecahan String**: Fungsi memecah parameter `ingredientsList` menjadi array menggunakan `split(', ')`
2. **Filtering**: Menggunakan method `filter()` untuk mencari bahan yang dimulai dengan kata "organic" (case-insensitive)
3. **Penggabungan**: Hasil filtering digabungkan kembali menjadi string menggunakan `join(', ')`

## 📊 Contoh Penggunaan dan Output

### Contoh 1: Daftar dengan Bahan Organik
```javascript
const ingredients = "organic tomatoes, regular onions, organic carrots, salt, organic spinach";
const result = getOrganicIngredients(ingredients);
console.log(result);
```

**Output:**
```
organic tomatoes, organic carrots, organic spinach
```

### Contoh 2: Tidak Ada Bahan Organik
```javascript
const ingredients = "tomatoes, onions, carrots, salt, pepper";
const result = getOrganicIngredients(ingredients);
console.log(result);
```

**Output:**
```
(string kosong)
```

### Contoh 3: Case Insensitive
```javascript
const ingredients = "ORGANIC apples, Organic Bananas, regular grapes, ORGANIC berries";
const result = getOrganicIngredients(ingredients);
console.log(result);
```

**Output:**
```
ORGANIC apples, Organic Bananas, ORGANIC berries
```

### Contoh 4: String Kosong
```javascript
const ingredients = "";
const result = getOrganicIngredients(ingredients);
console.log(result);
```

**Output:**
```
(string kosong)
```

## ⚠️ Catatan Penting

- Fungsi ini **case-insensitive**, artinya akan mendeteksi "organic", "Organic", "ORGANIC", dll.
- Format input harus berupa string dengan pemisah koma dan spasi (`, `)
- Jika tidak ada bahan organik yang ditemukan, fungsi akan mengembalikan string kosong
- Fungsi ini hanya mendeteksi bahan yang **dimulai** dengan kata "organic"

## 🚀 Tips Penggunaan

- Pastikan format input konsisten dengan pemisah `, ` (koma diikuti spasi)
- Gunakan fungsi ini dalam aplikasi inventori makanan untuk kategorisasi otomatis
- Cocok untuk sistem filtering menu restoran berdasarkan preferensi organik
- Dapat dikombinasikan dengan fungsi lain untuk analisis nutrisi yang lebih kompleks
