# 🏖️ Dokumentasi Fungsi `packBeachBag`

## 📋 Deskripsi

Fungsi `packBeachBag` adalah fungsi JavaScript yang membantu Anda mengemas tas pantai dengan cerdas. Fungsi ini akan menggabungkan daftar barang yang Anda miliki dengan rekomendasi dari teman, menghapus barang duplikat, dan menyesuaikan isi tas berdasarkan kondisi cuaca.

## 🎯 Fitur Utama

- ✅ Menggabungkan dua daftar barang
- ✅ Menghapus barang duplikat secara otomatis
- ✅ Menyesuaikan barang berdasarkan kondisi cuaca
- ✅ Mengurutkan barang secara alfabetis
- ✅ Menghapus barang yang tidak sesuai kondisi cuaca

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `initialItems` | Array | Daftar barang awal yang ingin Anda bawa |
| `friendRecommendations` | Array | Daftar barang yang direkomendasikan oleh teman |
| `weatherCondition` | String | Kondisi cuaca: `"sunny"`, `"windy"`, atau `"rainy"` |

## 🌤️ Kondisi Cuaca

| Cuaca | Aksi |
|-------|------|
| **sunny** (cerah) | Menambahkan `"sunscreen"` jika belum ada |
| **windy** (berangin) | Menambahkan `"hat"` jika belum ada |
| **rainy** (hujan) | Menambahkan `"umbrella"` dan menghapus `"camera"` dan `"book"` |

## 💻 Kode Fungsi

```javascript
function packBeachBag(initialItems, friendRecommendations, weatherCondition) {
  
  // 1. Menggabungkan kedua array menjadi satu
  let items = [...initialItems, ...friendRecommendations];
  
  
  // 2. Menghapus item duplikat menggunakan Set
  items = [...new Set(items)];
  
  
  // 3. Memeriksa kondisi cuaca dan memodifikasi items sesuai kebutuhan
  if (weatherCondition === "sunny") {
    // Jika cuaca cerah, pastikan ada sunscreen
    if (!items.includes("sunscreen")) {
      items.push("sunscreen");
    }
    
  } else if (weatherCondition === "windy") {
    // Jika cuaca berangin, pastikan ada topi
    if (!items.includes("hat")) {
      items.push("hat");
    }
    
  } else if (weatherCondition === "rainy") {
    // Jika cuaca hujan, tambahkan payung (selalu ditambahkan)
    items.push("umbrella");
    
    // Hapus barang yang tidak tahan air
    items = items.filter(item => item !== "camera" && item !== "book");
  }
  
  
  // 4. Mengurutkan barang secara alfabetis (A-Z)
  items.sort();
  
  
  // 5. Mengembalikan array yang sudah diurutkan
  return items;
}
```

## 🔍 Cara Kerja Fungsi

### Langkah 1: Menggabungkan Array
Fungsi menggunakan spread operator (`...`) untuk menggabungkan `initialItems` dan `friendRecommendations` menjadi satu array.

### Langkah 2: Menghapus Duplikat
Menggunakan `Set` untuk menghapus item yang sama/duplikat, kemudian mengubahnya kembali menjadi array.

### Langkah 3: Penyesuaian Cuaca
Berdasarkan `weatherCondition`, fungsi akan:
- Menambahkan barang yang diperlukan
- Menghapus barang yang tidak sesuai

### Langkah 4: Mengurutkan
Semua barang diurutkan secara alfabetis menggunakan method `.sort()`.

### Langkah 5: Mengembalikan Hasil
Array yang sudah rapi dikembalikan sebagai hasil akhir.

## 📖 Contoh Penggunaan

### Contoh 1: Cuaca Cerah ☀️

```javascript
const myItems = ["towel", "water bottle", "snacks"];
const friendItems = ["frisbee", "towel", "sunglasses"];
const weather = "sunny";

const result = packBeachBag(myItems, friendItems, weather);
console.log(result);
```

**Output:**
```javascript
["frisbee", "snacks", "sunglasses", "sunscreen", "towel", "water bottle"]
```

**Penjelasan:** 
- Item "towel" yang duplikat dihapus
- "sunscreen" ditambahkan karena cuaca cerah
- Semua item diurutkan alfabetis

---

### Contoh 2: Cuaca Berangin 💨

```javascript
const myItems = ["towel", "sunglasses"];
const friendItems = ["frisbee", "water bottle"];
const weather = "windy";

const result = packBeachBag(myItems, friendItems, weather);
console.log(result);
```

**Output:**
```javascript
["frisbee", "hat", "sunglasses", "towel", "water bottle"]
```

**Penjelasan:** 
- "hat" ditambahkan karena cuaca berangin
- Semua item diurutkan alfabetis

---

### Contoh 3: Cuaca Hujan 🌧️

```javascript
const myItems = ["towel", "camera", "book"];
const friendItems = ["umbrella", "water bottle"];
const weather = "rainy";

const result = packBeachBag(myItems, friendItems, weather);
console.log(result);
```

**Output:**
```javascript
["towel", "umbrella", "umbrella", "water bottle"]
```

**Penjelasan:** 
- "camera" dan "book" dihapus karena tidak tahan air
- "umbrella" ditambahkan (meskipun sudah ada dari teman)
- Hasil akhir diurutkan alfabetis

---

## ⚠️ Catatan Penting

1. **Duplikat pada cuaca hujan**: Pada kondisi `"rainy"`, umbrella akan selalu ditambahkan bahkan jika sudah ada dalam daftar, sehingga bisa menghasilkan duplikat umbrella.

2. **Case sensitive**: Nama barang bersifat case-sensitive. `"Towel"` dan `"towel"` dianggap berbeda.

3. **Pengurutan alfabetis**: Huruf besar akan muncul lebih dulu dalam pengurutan (misal: "Book" sebelum "towel").

## 🎓 Tips untuk Pemula

- **Spread Operator (`...`)**: Digunakan untuk "menyebarkan" isi array
- **Set**: Objek JavaScript yang hanya menyimpan nilai unik (tidak ada duplikat)
- **`.includes()`**: Method untuk mengecek apakah suatu nilai ada dalam array
- **`.push()`**: Method untuk menambahkan item ke akhir array
- **`.filter()`**: Method untuk menyaring array berdasarkan kondisi tertentu
- **`.sort()`**: Method untuk mengurutkan array

---

**Dibuat dengan ❤️ untuk membantu Anda mengemas tas pantai dengan sempurna!**
