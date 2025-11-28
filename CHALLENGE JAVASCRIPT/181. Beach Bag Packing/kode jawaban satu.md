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
  
  // Menggabungkan kedua array menjadi satu array baru
  let combinedItems = [...initialItems, ...friendRecommendations];
  
  // Menghapus item duplikat menggunakan Set
  let uniqueItems = [...new Set(combinedItems)];
  
  
  // Jika cuaca cerah, pastikan ada sunscreen
  if (weatherCondition === "sunny" && !uniqueItems.includes("sunscreen")) {
    uniqueItems.push("sunscreen");
  }
  
  
  // Jika cuaca berangin, pastikan ada topi
  if (weatherCondition === "windy" && !uniqueItems.includes("hat")) {
    uniqueItems.push("hat");
  }
  
  
  // Jika cuaca hujan, tambahkan payung dan hapus barang yang tidak tahan air
  if (weatherCondition === "rainy") {
    uniqueItems.push("umbrella");
    uniqueItems = uniqueItems.filter(item => item !== "camera" && item !== "book");
  }
  
  
  // Mengurutkan barang secara alfabetis dan mengembalikan hasilnya
  return uniqueItems.sort();
}
```

## 🔍 Cara Kerja Fungsi

### Langkah 1: Menggabungkan Array
Fungsi menggunakan spread operator (`...`) untuk menggabungkan `initialItems` dan `friendRecommendations` menjadi satu array yang disimpan dalam variabel `combinedItems`.

### Langkah 2: Menghapus Duplikat
Menggunakan `Set` untuk menghapus item yang sama/duplikat dari `combinedItems`, kemudian mengubahnya kembali menjadi array dan menyimpannya dalam `uniqueItems`.

### Langkah 3: Penyesuaian Cuaca
Berdasarkan `weatherCondition`, fungsi akan memeriksa setiap kondisi secara terpisah:
- **Sunny**: Menambahkan sunscreen hanya jika belum ada
- **Windy**: Menambahkan hat hanya jika belum ada
- **Rainy**: Menambahkan umbrella (selalu) dan menghapus camera & book

### Langkah 4: Mengurutkan dan Mengembalikan
Array `uniqueItems` diurutkan secara alfabetis menggunakan `.sort()` dan langsung dikembalikan sebagai hasil akhir.

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

### Contoh 4: Cuaca Cerah dengan Sunscreen Sudah Ada ☀️

```javascript
const myItems = ["towel", "sunscreen"];
const friendItems = ["hat", "water bottle"];
const weather = "sunny";

const result = packBeachBag(myItems, friendItems, weather);
console.log(result);
```

**Output:**
```javascript
["hat", "sunscreen", "towel", "water bottle"]
```

**Penjelasan:** 
- "sunscreen" tidak ditambahkan lagi karena sudah ada
- Semua item diurutkan alfabetis

---

## ⚠️ Catatan Penting

1. **Duplikat pada cuaca hujan**: Pada kondisi `"rainy"`, umbrella akan selalu ditambahkan bahkan jika sudah ada dalam daftar, sehingga bisa menghasilkan duplikat umbrella.

2. **Case sensitive**: Nama barang bersifat case-sensitive. `"Towel"` dan `"towel"` dianggap berbeda.

3. **Pengurutan alfabetis**: Huruf besar akan muncul lebih dulu dalam pengurutan (misal: "Book" sebelum "towel").

4. **Kondisi independen**: Kondisi cuaca tidak saling eksklusif dalam kode ini, namun dalam penggunaan normal hanya satu kondisi cuaca yang akan aktif.

## 🎓 Tips untuk Pemula

- **Spread Operator (`...`)**: Digunakan untuk "menyebarkan" isi array ke dalam array baru
- **Set**: Objek JavaScript yang hanya menyimpan nilai unik (tidak ada duplikat)
- **`.includes()`**: Method untuk mengecek apakah suatu nilai ada dalam array
- **`.push()`**: Method untuk menambahkan item ke akhir array
- **`.filter()`**: Method untuk menyaring array berdasarkan kondisi tertentu
- **`.sort()`**: Method untuk mengurutkan array secara alfabetis
- **`&&` (AND operator)**: Operator logika yang memastikan kedua kondisi bernilai true

## 🆚 Perbedaan dengan Versi Sebelumnya

Versi ini menggunakan struktur yang lebih ringkas dengan:
- Pemisahan kondisi `if` yang lebih jelas (tidak menggunakan `else if`)
- Nama variabel yang lebih deskriptif (`combinedItems` dan `uniqueItems`)
- Pengembalian nilai langsung dengan chaining `.sort()`

---

**Dibuat dengan ❤️ untuk membantu Anda mengemas tas pantai dengan sempurna!**
