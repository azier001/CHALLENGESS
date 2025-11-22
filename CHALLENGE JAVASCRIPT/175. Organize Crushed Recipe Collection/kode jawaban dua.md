# 📚 Dokumentasi Fungsi `organizeRecipes`

## 📝 Deskripsi

Fungsi `organizeRecipes` adalah fungsi yang digunakan untuk **mengorganisir daftar resep** berdasarkan tipenya. Fungsi ini akan mengelompokkan nama-nama resep ke dalam kategori sesuai dengan tipe masakan masing-masing (misalnya: makanan pembuka, makanan utama, dessert, dll).

Selain itu, fungsi ini juga secara otomatis memberikan waktu memasak default **30 menit** untuk resep yang belum memiliki informasi waktu memasak.

---

## 🔧 Parameter

### Input

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `recipes` | Array of Objects | Array yang berisi objek-objek resep. Setiap objek harus memiliki properti `name` (nama resep) dan `type` (tipe resep), serta opsional `cookingTime` (waktu memasak dalam menit) |

### Struktur Objek Resep

| Properti | Tipe | Wajib? | Deskripsi |
|----------|------|--------|-----------|
| `name` | String | ✅ Ya | Nama resep masakan |
| `type` | String | ✅ Ya | Kategori/tipe masakan (contoh: "appetizer", "main course", "dessert") |
| `cookingTime` | Number | ❌ Tidak | Waktu memasak dalam menit (akan diisi 30 jika tidak ada) |

### Output

| Tipe | Deskripsi |
|------|-----------|
| Object | Objek yang berisi pengelompokan nama resep berdasarkan tipe. Key adalah tipe resep, value adalah array berisi nama-nama resep |

---

## 💻 Kode Fungsi

```javascript
function organizeRecipes(recipes) {
  // Membuat objek kosong untuk menyimpan hasil pengelompokan
  const result = {};
  
  // Melakukan iterasi untuk setiap resep dalam array
  for (const recipe of recipes) {
    // Jika resep tidak memiliki waktu memasak, set default 30 menit
    if (recipe.cookingTime === undefined) {
      recipe.cookingTime = 30;
    }
    
    // Jika tipe resep belum ada dalam result, buat array kosong
    if (!result[recipe.type]) {
      result[recipe.type] = [];
    }
    
    // Tambahkan nama resep ke dalam array sesuai tipenya
    result[recipe.type].push(recipe.name);
  }
  
  // Mengembalikan objek hasil pengelompokan
  return result;
}
```

---

## 🎯 Cara Kerja

1. **Inisialisasi**: Membuat objek kosong `result` untuk menyimpan hasil pengelompokan
2. **Iterasi**: Melakukan loop untuk setiap resep dalam array input
3. **Set Default**: Jika resep tidak memiliki `cookingTime`, otomatis diisi dengan nilai 30
4. **Pengecekan Kategori**: Jika kategori/tipe belum ada dalam `result`, buat array baru
5. **Pengelompokan**: Tambahkan nama resep ke dalam array sesuai kategorinya
6. **Return**: Mengembalikan objek yang sudah terorganisir

---

## 📖 Contoh Penggunaan

### Input

```javascript
const resepMasakan = [
  { name: "Spaghetti Carbonara", type: "main course", cookingTime: 25 },
  { name: "Caesar Salad", type: "appetizer" },
  { name: "Chocolate Cake", type: "dessert", cookingTime: 45 },
  { name: "Grilled Chicken", type: "main course" },
  { name: "Bruschetta", type: "appetizer", cookingTime: 15 }
];

const hasil = organizeRecipes(resepMasakan);
console.log(hasil);
```

### Output

```javascript
{
  "main course": ["Spaghetti Carbonara", "Grilled Chicken"],
  "appetizer": ["Caesar Salad", "Bruschetta"],
  "dessert": ["Chocolate Cake"]
}
```

### Penjelasan Output

- Resep **"Caesar Salad"** dan **"Grilled Chicken"** yang awalnya tidak memiliki `cookingTime` sekarang memiliki nilai default 30 menit
- Semua resep telah dikelompokkan berdasarkan `type`:
  - **main course**: 2 resep
  - **appetizer**: 2 resep  
  - **dessert**: 1 resep
- Output hanya menampilkan **nama resep**, bukan objek lengkapnya

---

## ⚠️ Catatan Penting

- Fungsi ini **memodifikasi** array input dengan menambahkan `cookingTime` default pada resep yang belum memilikinya
- Urutan resep dalam hasil pengelompokan mengikuti urutan kemunculan dalam array input
- Fungsi ini case-sensitive untuk `type`, jadi "Dessert" dan "dessert" akan dianggap berbeda
- Fungsi akan mengembalikan objek kosong `{}` jika array input kosong

---

## 🚀 Tips Penggunaan

1. **Pastikan setiap resep memiliki properti `name` dan `type`** agar fungsi bekerja dengan baik
2. Gunakan **penamaan tipe yang konsisten** (misalnya selalu lowercase) untuk menghindari duplikasi kategori
3. Jika ingin mempertahankan informasi lengkap resep (bukan hanya nama), modifikasi baris `result[recipe.type].push(recipe.name)` menjadi `result[recipe.type].push(recipe)`

---

**Dibuat dengan ❤️ untuk memudahkan pengelolaan resep masakan**
