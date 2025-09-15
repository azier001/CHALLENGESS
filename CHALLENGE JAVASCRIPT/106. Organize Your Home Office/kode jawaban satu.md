# 📂 Dokumentasi Fungsi `organizeWorkspace`

## 📋 Deskripsi

Fungsi `organizeWorkspace` adalah sebuah utility yang membantu mengorganisir berbagai item di ruang kerja dengan mengelompokkannya berdasarkan kategori. Fungsi ini sangat berguna untuk manajemen inventaris atau sistem organisasi digital yang memerlukan pengelompokan barang secara otomatis.

## 🔧 Parameter

| Parameter | Tipe   | Wajib | Deskripsi |
|-----------|--------|-------|-----------|
| `items`   | Array  | ✅     | Array yang berisi nama-nama item yang ingin diorganisir |

## 📊 Kategori Item yang Didukung

### 🔌 Elektronik
| Item | Item | Item | Item | Item |
|------|------|------|------|------|
| laptop | phone | tablet | computer | mouse |
| keyboard | monitor | printer | scanner | charger |

### ✏️ Alat Tulis
| Item | Item | Item | Item | Item |
|------|------|------|------|------|
| pen | pencil | notebook | paper | stapler |
| scissors | tape | glue | ruler | eraser |

### 📚 Buku & Publikasi
| Item | Item | Item | Item | Item |
|------|------|------|------|------|
| book | magazine | journal | kindle | textbook |
| novel | dictionary | encyclopedia | manual | guide |

## 💻 Kode Fungsi

```javascript
function organizeWorkspace(items) {
  // Daftar kategori elektronik
  const electronics = [
    "laptop", "phone", "tablet", "computer", "mouse", 
    "keyboard", "monitor", "printer", "scanner", "charger"
  ];

  // Daftar kategori alat tulis
  const stationery = [
    "pen", "pencil", "notebook", "paper", "stapler", 
    "scissors", "tape", "glue", "ruler", "eraser"
  ];

  // Daftar kategori buku dan publikasi
  const books = [
    "book", "magazine", "journal", "kindle", "textbook", 
    "novel", "dictionary", "encyclopedia", "manual", "guide"
  ];

  // Inisialisasi array untuk menyimpan item yang sudah dikelompokkan
  // Index 0: elektronik, Index 1: alat tulis, Index 2: buku
  const organizedItems = [[], [], []];

  // Melakukan iterasi setiap item dan mengelompokkan berdasarkan kategorinya
  for (const item of items) {
    if (electronics.includes(item)) {
      organizedItems[0].push(item);  // Tambahkan ke kategori elektronik
    } else if (stationery.includes(item)) {
      organizedItems[1].push(item);  // Tambahkan ke kategori alat tulis
    } else if (books.includes(item)) {
      organizedItems[2].push(item);  // Tambahkan ke kategori buku
    }
    // Item yang tidak dikenali akan diabaikan
  }

  // Mengembalikan hasil dalam bentuk array berisi 3 kategori
  return organizedItems;
}
```

## 🔄 Return Value

Fungsi ini mengembalikan sebuah **Array** yang berisi 3 sub-array:

1. **Index 0**: Array item elektronik
2. **Index 1**: Array item alat tulis  
3. **Index 2**: Array item buku & publikasi

## 📝 Contoh Penggunaan

```javascript
// Contoh daftar item yang ingin diorganisir
const myItems = [
    "laptop", "pen", "book", "mouse", 
    "notebook", "phone", "scissors", 
    "novel", "keyboard", "ruler"
];

// Memanggil fungsi organizeWorkspace
const organizedItems = organizeWorkspace(myItems);

console.log(organizedItems);
```

## 🎯 Contoh Output

```javascript
[
    ["laptop", "mouse", "phone", "keyboard"],    // Elektronik
    ["pen", "notebook", "scissors", "ruler"],    // Alat tulis
    ["book", "novel"]                            // Buku & publikasi
]
```

### Penjelasan Output:
- **Array pertama**: Berisi 4 item elektronik (laptop, mouse, phone, keyboard)
- **Array kedua**: Berisi 4 item alat tulis (pen, notebook, scissors, ruler)
- **Array ketiga**: Berisi 2 item buku (book, novel)

## ⚡ Keunggulan Implementasi

Versi ini menggunakan beberapa optimasi:

- **For...of loop**: Lebih efisien dan mudah dibaca dibandingkan forEach
- **Array pre-initialized**: Menggunakan `[[], [], []]` untuk inisialisasi langsung
- **Direct indexing**: Akses langsung ke index array untuk performa yang lebih baik

## ⚠️ Catatan Penting

- Item yang tidak termasuk dalam kategori yang didukung akan **diabaikan** dan tidak muncul dalam hasil
- Fungsi ini **case-sensitive**, jadi pastikan nama item ditulis dengan huruf kecil
- Urutan item dalam hasil mengikuti urutan kemunculan dalam array input

## 🚀 Tips Penggunaan

1. **Validasi Input**: Selalu pastikan parameter `items` adalah array yang valid
2. **Standarisasi Nama**: Gunakan nama item yang sudah terdefined dalam kategori
3. **Destructuring**: Gunakan destructuring untuk mengakses hasil yang lebih mudah:

```javascript
const [electronics, stationery, books] = organizeWorkspace(items);
```

4. **Error Handling**: Tambahkan pengecekan untuk input yang tidak valid:

```javascript
// Contoh penggunaan dengan error handling
function safeOrganizeWorkspace(items) {
  if (!Array.isArray(items)) {
    throw new Error('Parameter items harus berupa array');
  }
  return organizeWorkspace(items);
}
```

## 🔍 Contoh Penggunaan Lanjutan

```javascript
// Contoh dengan berbagai jenis item
const officeItems = [
  "laptop", "pen", "book", "stapler", 
  "monitor", "novel", "scissors", "tablet",
  "unknown_item"  // Item ini akan diabaikan
];

const [electronics, stationery, books] = organizeWorkspace(officeItems);

console.log("Elektronik:", electronics);
console.log("Alat Tulis:", stationery);  
console.log("Buku:", books);

// Output:
// Elektronik: ["laptop", "monitor", "tablet"]
// Alat Tulis: ["pen", "stapler", "scissors"]
// Buku: ["book", "novel"]
```

---

*Dokumentasi ini dibuat untuk membantu developer memahami dan menggunakan fungsi `organizeWorkspace` dengan lebih efektif.*
