# 📚 Library Book Organizer

## 🎯 Gambaran Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function yang mengorganisir dan memformat judul buku dari kategori yang berbeda ke dalam satu array yang terstruktur dengan baik.

---

## 📋 Spesifikasi Function

### Nama Function
```javascript
organizeLibrary(scienceBooks, philosophyBooks)
```

### 🔧 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `scienceBooks` | `Array<string>` | Array string yang merepresentasikan judul-judul buku sains |
| `philosophyBooks` | `Array<string>` | Array string yang merepresentasikan judul-judul buku filsafat |

### 🎯 Return Value
- **Type:** `Array<string>`
- **Deskripsi:** Array string dimana setiap string adalah judul buku yang telah diformat dengan benar

---

## 📝 Requirements

### 🔄 Urutan Pemrosesan
1. **Pertama:** Tambahkan semua buku sains ke result array
2. **Kedua:** Tambahkan semua buku filsafat ke result array

### 📖 Aturan Format Judul
Setiap judul buku harus diformat dengan:
- ✅ **Huruf pertama:** Uppercase
- ✅ **Huruf sisanya:** Lowercase
- ✅ **Diterapkan terlepas** dari format aslinya

### 🛠️ Requirements Teknis
- Gunakan **array concatenation** untuk menggabungkan array buku
- Gunakan **nested loops** untuk memformat setiap judul buku dengan benar
- Proses judul sebelum menambahkannya ke final array

---

## 💡 Contoh Formatting

```javascript
// Judul asli (kombinasi case apapun)
let title = "THE COSMOS";

// Teknik formatting yang benar
let formattedTitle = title.charAt(0).toUpperCase() + title.slice(1).toLowerCase();

// Hasil
console.log(formattedTitle); // Output: "The cosmos"
```

### 🔍 Breakdown Step-by-Step
1. `title.charAt(0).toUpperCase()` → Mengambil karakter pertama dan membuatnya uppercase
2. `title.slice(1).toLowerCase()` → Mengambil karakter sisanya dan membuatnya lowercase
3. Concatenate kedua bagian menggunakan operator `+`

---

## 🎪 Contoh Penggunaan

```javascript
// Sample input
const scienceBooks = ["PHYSICS FUNDAMENTALS", "chemistry basics", "BiOlOgY eSSenTiAlS"];
const philosophyBooks = ["ANCIENT WISDOM", "modern ethics", "PhIlOsOpHy Of MiNd"];

// Function call
const organizedBooks = organizeLibrary(scienceBooks, philosophyBooks);

// Expected output
console.log(organizedBooks);
/*
[
  "Physics fundamentals",
  "Chemistry basics", 
  "Biology essentials",
  "Ancient wisdom",
  "Modern ethics",
  "Philosophy of mind"
]
*/
```

---

## ✨ Poin Penting yang Perlu Diingat

> 🔑 **Penting:** Terapkan transformasi formatting pada **setiap judul buku** di kedua input array sebelum menambahkannya ke result array Anda.

- 📊 **Urutan penting:** Buku sains dulu, kemudian buku filsafat
- 🔤 **Format konsisten:** Huruf pertama uppercase, sisanya lowercase
- 🔧 **Gunakan method yang tepat:** Array concatenation dan nested loops
- 🎯 **Proses sebelum menambahkan:** Format judul selama proses organisasi

---

## 🏷️ Tags
`JavaScript` `Arrays` `String Manipulation` `Loops` `Easy Challenge`
