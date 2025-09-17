# 🔄 Fungsi reverseExplorerPath

## 📝 Deskripsi

Fungsi `reverseExplorerPath` adalah sebuah utilitas yang digunakan untuk membalikkan urutan karakter dalam sebuah path (jalur) dan membalikkan urutan elemen dalam array inventory (inventaris). Fungsi ini berguna dalam konteks game atau aplikasi eksplorasi dimana kita perlu membalikkan arah perjalanan atau urutan item.

## 🔧 Sintaks

```javascript
reverseExplorerPath(path, inventory)
```

## 📋 Parameter

| Parameter   | Tipe    | Deskripsi                                                    |
|-------------|---------|--------------------------------------------------------------|
| `path`      | String  | String yang berisi jalur atau karakter yang akan dibalik    |
| `inventory` | Array   | Array yang berisi item-item inventaris yang akan dibalik    |

### Detail Parameter

- **path**: String yang akan dibalik karakter per karakternya
- **inventory**: Array yang akan dibalik urutan elemennya (elemen pertama menjadi terakhir, dst.)

## 📤 Return Value

Fungsi ini mengembalikan sebuah array dengan dua elemen:

| Index | Tipe   | Deskripsi                           |
|-------|--------|-------------------------------------|
| 0     | String | Path yang sudah dibalik             |
| 1     | Array  | Inventory yang sudah dibalik urutan |

## 💻 Kode Fungsi

```javascript
function reverseExplorerPath(path, inventory) {
    // Membalik urutan karakter dalam path dengan cara:
    // 1. Memecah string menjadi array karakter dengan split('')
    // 2. Membalik urutan array dengan reverse()
    // 3. Menggabungkan kembali menjadi string dengan join('')
    const reversedPath = path.split('').reverse().join('');
    
    // Membalik urutan elemen dalam inventory dengan cara:
    // 1. Membuat salinan array menggunakan spread operator (...)
    // 2. Membalik urutan array dengan reverse()
    const reversedInventory = [...inventory].reverse();
    
    // Mengembalikan array berisi path dan inventory yang sudah dibalik
    return [reversedPath, reversedInventory];
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Path Sederhana
```javascript
const path = "NSEW";
const inventory = ["sword", "shield", "potion"];

const [reversedPath, reversedInventory] = reverseExplorerPath(path, inventory);

console.log("Path asli:", path);
console.log("Path terbalik:", reversedPath);
console.log("Inventory asli:", inventory);
console.log("Inventory terbalik:", reversedInventory);
```

**Output:**
```
Path asli: NSEW
Path terbalik: WESN
Inventory asli: ["sword", "shield", "potion"]
Inventory terbalik: ["potion", "shield", "sword"]
```

### Contoh 2: Path dengan Angka
```javascript
const path = "123ABC";
const inventory = [1, 2, 3, 4, 5];

const [reversedPath, reversedInventory] = reverseExplorerPath(path, inventory);

console.log("Path asli:", path);
console.log("Path terbalik:", reversedPath);
console.log("Inventory asli:", inventory);
console.log("Inventory terbalik:", reversedInventory);
```

**Output:**
```
Path asli: 123ABC
Path terbalik: CBA321
Inventory asli: [1, 2, 3, 4, 5]
Inventory terbalik: [5, 4, 3, 2, 1]
```

### Contoh 3: Kasus dengan Array Kosong
```javascript
const path = "ABC";
const inventory = [];

const [reversedPath, reversedInventory] = reverseExplorerPath(path, inventory);

console.log("Path asli:", path);
console.log("Path terbalik:", reversedPath);
console.log("Inventory asli:", inventory);
console.log("Inventory terbalik:", reversedInventory);
```

**Output:**
```
Path asli: ABC
Path terbalik: CBA
Inventory asli: []
Inventory terbalik: []
```

## 📚 Tabel Karakter Path Umum

Dalam konteks game eksplorasi, berikut adalah karakter yang biasa digunakan:

| Karakter | Arti           | Terbalik Menjadi |
|----------|----------------|------------------|
| N        | North (Utara)  | Tetap N          |
| S        | South (Selatan)| Tetap S          |
| E        | East (Timur)   | Tetap E          |
| W        | West (Barat)   | Tetap W          |

**Catatan**: Karakter individual tidak berubah, hanya urutannya yang terbalik.

## ⚠️ Hal yang Perlu Diperhatikan

- Fungsi ini tidak mengubah array `inventory` asli karena menggunakan spread operator (`...`) untuk membuat salinan
- String `path` juga tidak diubah karena string bersifat immutable di JavaScript
- Fungsi ini akan bekerja dengan semua tipe data dalam array inventory
- Path kosong (`""`) akan menghasilkan string kosong juga
- Array inventory kosong (`[]`) akan menghasilkan array kosong juga

## 🚀 Use Case

Fungsi ini sangat berguna untuk:
- **Game RPG**: Membalikkan jalur perjalanan karakter
- **Algoritma Backtracking**: Mencari jalan kembali
- **Undo System**: Membalikkan aksi yang telah dilakukan
- **Puzzle Game**: Membalikkan urutan langkah atau item
