# 📚 Monastery Library Section Sorter

## 🎯 Ringkasan Tantangan

**Level Kesulitan:** `Easy`

Bantu para monk mengatur perpustakaan kuno mereka dengan membuat function sorting khusus! Tantangan ini mengharuskan Anda mengimplementasikan sebuah function yang dapat mengurutkan bagian tertentu dari koleksi buku monastery sambil mempertahankan urutan buku di luar bagian tersebut.

---

## 📋 Deskripsi Masalah

Buat sebuah function bernama `sortMonasteryBooks` yang membantu para monk mengurutkan bagian tertentu dari buku-buku perpustakaan mereka secara alfabetis sambil menjaga bagian koleksi lainnya tetap tidak berubah.

### Function Signature

```javascript
function sortMonasteryBooks(books, startIndex, endIndex)
```

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `books` | `Array<string>` | Sebuah array yang berisi judul-judul buku di perpustakaan |
| `startIndex` | `number` | Index awal (inclusive) dari bagian yang akan diurutkan |
| `endIndex` | `number` | Index akhir (inclusive) dari bagian yang akan diurutkan |

---

## 📤 Return Value

- **Tipe:** `Array<string>`
- **Deskripsi:** Array baru dengan bagian tertentu diurutkan secara alfabetis, sementara semua buku lainnya tetap pada posisi aslinya

---

## 🎯 Requirements

- ✅ Urutkan hanya buku-buku dalam rentang index yang ditentukan
- ✅ Pertahankan urutan alfabetis untuk bagian yang diurutkan
- ✅ Jaga semua buku lainnya pada posisi aslinya
- ✅ Return array baru (jangan modify array asli)

---

## 📏 Constraints

| Constraint | Nilai/Aturan |
|------------|------------|
| **Panjang Array** | Maksimal 10 buku |
| **Judul Buku** | Hanya huruf bahasa Inggris, spasi, dan tanda baca |
| **Validitas Index** | `startIndex` dan `endIndex` akan selalu berupa index array yang valid |
| **Hubungan Index** | `startIndex` ≤ `endIndex` |

---

## 💡 Contoh Penggunaan

```javascript
// Contoh input
const books = [
    "Divine Comedy", 
    "Zealot's Guide", 
    "Ancient Prayers", 
    "Book of Hours", 
    "Sacred Texts"
];

// Urutkan buku dari index 1 sampai 3
const result = sortMonasteryBooks(books, 1, 3);

// Output yang diharapkan:
// [
//     "Divine Comedy",     // tidak berubah (index 0)
//     "Ancient Prayers",   // diurutkan (sebelumnya di index 2)
//     "Book of Hours",     // diurutkan (sebelumnya di index 3)
//     "Zealot's Guide",    // diurutkan (sebelumnya di index 1)
//     "Sacred Texts"       // tidak berubah (index 4)
// ]
```

---

## 🧠 Petunjuk Pendekatan

1. **Extract** bagian yang akan diurutkan
2. **Sort** bagian yang diekstrak secara alfabetis
3. **Rekonstruksi** array dengan bagian yang sudah diurutkan pada tempatnya
4. **Pertahankan** posisi asli buku-buku di luar rentang

---

## 🏷️ Tags

`#arrays` `#sorting` `#string-manipulation` `#beginner-friendly`

---

*Semoga code Anda membawa keteraturan pada pengetahuan suci monastery! 📜✨*
