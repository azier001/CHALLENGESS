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
    
    // Array untuk menyimpan item yang sudah dikelompokkan
    const electronicsItems = [];
    const stationeryItems = [];
    const booksItems = [];
    
    // Melakukan pengelompokan setiap item berdasarkan kategorinya
    items.forEach(item => {
        if (electronics.includes(item)) {
            electronicsItems.push(item);
        } else if (stationery.includes(item)) {
            stationeryItems.push(item);
        } else if (books.includes(item)) {
            booksItems.push(item);
        }
    });
    
    // Mengembalikan hasil dalam bentuk array berisi 3 kategori
    return [electronicsItems, stationeryItems, booksItems];
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

---

*Dokumentasi ini dibuat untuk membantu developer memahami dan menggunakan fungsi `organizeWorkspace` dengan lebih efektif.*
