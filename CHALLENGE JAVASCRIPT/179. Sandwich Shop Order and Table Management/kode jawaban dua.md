# 📋 Dokumentasi Fungsi `processShopOrders`

## 📖 Deskripsi

Fungsi `processShopOrders` adalah fungsi yang digunakan untuk memproses pesanan sandwich di sebuah toko dan memeriksa ketersediaan meja. Fungsi ini akan:
- Menghitung jumlah setiap jenis sandwich yang dipesan
- Mencari meja-meja yang tersedia untuk pelanggan

Fungsi ini sangat berguna untuk sistem manajemen restoran atau toko sandwich yang perlu melacak pesanan dan ketersediaan tempat duduk.

---

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `orders` | Array | Daftar pesanan sandwich. Setiap elemen adalah string yang berisi nama sandwich |
| `tableStatuses` | Array | Status setiap meja. Berisi string `"available"` (tersedia) atau `"occupied"` (terisi) |

---

## 🔄 Return Value

Fungsi ini mengembalikan sebuah **object** dengan dua properti:

| Properti | Tipe | Deskripsi |
|----------|------|-----------|
| `sandwichCounts` | Object | Objek yang berisi jumlah setiap jenis sandwich. Key adalah nama sandwich, value adalah jumlahnya |
| `availableTables` | Array | Array berisi nomor meja yang tersedia (dimulai dari 1) |

---

## 💻 Kode Fungsi

```javascript
function processShopOrders(orders, tableStatuses) {
  // Objek untuk menyimpan jumlah setiap jenis sandwich
  const sandwichCounts = {};
  
  // Menghitung jumlah setiap jenis sandwich yang dipesan
  for (const sandwich of orders) {
    sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1;
  }
  
  // Array untuk menyimpan nomor meja yang tersedia
  const availableTables = [];
  
  // Mencari meja-meja yang statusnya "available"
  for (let i = 0; i < tableStatuses.length; i++) {
    if (tableStatuses[i] === "available") {
      // Menambahkan nomor meja (index + 1) ke dalam array
      availableTables.push(i + 1);
    }
  }
  
  // Mengembalikan hasil berupa objek dengan dua properti
  return {
    sandwichCounts,
    availableTables
  };
}
```

---

## 📊 Cara Kerja

### 1️⃣ Menghitung Pesanan Sandwich
Fungsi ini menggunakan loop untuk menghitung berapa kali setiap jenis sandwich dipesan:
- Jika sandwich belum ada di objek `sandwichCounts`, nilainya diset ke 0 kemudian ditambah 1
- Jika sudah ada, nilainya ditambah 1

### 2️⃣ Mencari Meja Tersedia
Fungsi ini memeriksa setiap status meja:
- Jika status meja adalah `"available"`, nomor mejanya ditambahkan ke array
- Nomor meja dimulai dari 1 (bukan 0), karena menggunakan `i + 1`

---

## 🎯 Contoh Penggunaan

### Contoh 1: Toko dengan Beberapa Pesanan

```javascript
const orders = ["Tuna", "Club", "Tuna", "Veggie", "Club", "Tuna"];
const tableStatuses = ["available", "occupied", "available", "occupied", "available"];

const result = processShopOrders(orders, tableStatuses);
console.log(result);
```

**Output:**
```javascript
{
  sandwichCounts: {
    Tuna: 3,
    Club: 2,
    Veggie: 1
  },
  availableTables: [1, 3, 5]
}
```

**Penjelasan:**
- Sandwich **Tuna** dipesan sebanyak **3 kali**
- Sandwich **Club** dipesan sebanyak **2 kali**
- Sandwich **Veggie** dipesan sebanyak **1 kali**
- Meja yang tersedia adalah meja nomor **1, 3, dan 5**

---

### Contoh 2: Semua Meja Terisi

```javascript
const orders = ["BLT", "Chicken", "BLT"];
const tableStatuses = ["occupied", "occupied", "occupied"];

const result = processShopOrders(orders, tableStatuses);
console.log(result);
```

**Output:**
```javascript
{
  sandwichCounts: {
    BLT: 2,
    Chicken: 1
  },
  availableTables: []
}
```

**Penjelasan:**
- Sandwich **BLT** dipesan sebanyak **2 kali**
- Sandwich **Chicken** dipesan sebanyak **1 kali**
- **Tidak ada meja yang tersedia** (array kosong)

---

### Contoh 3: Tidak Ada Pesanan

```javascript
const orders = [];
const tableStatuses = ["available", "available"];

const result = processShopOrders(orders, tableStatuses);
console.log(result);
```

**Output:**
```javascript
{
  sandwichCounts: {},
  availableTables: [1, 2]
}
```

**Penjelasan:**
- **Tidak ada pesanan** sama sekali (objek kosong)
- Meja nomor **1 dan 2** tersedia

---

## 💡 Tips Penggunaan

- ✅ Pastikan array `orders` berisi string (nama sandwich)
- ✅ Pastikan array `tableStatuses` hanya berisi string `"available"` atau `"occupied"`
- ✅ Fungsi ini tidak mengubah array input, jadi aman untuk digunakan berulang kali
- ⚠️ Jika ada typo pada status meja (misalnya `"avaliable"`), meja tersebut tidak akan dihitung sebagai tersedia

---

## 🎓 Konsep Pemrograman yang Digunakan

| Konsep | Penjelasan |
|--------|------------|
| **Loop for...of** | Digunakan untuk iterasi setiap pesanan sandwich |
| **Loop for** | Digunakan untuk iterasi index array status meja |
| **Object** | Menyimpan data dalam bentuk key-value pairs |
| **Array** | Menyimpan daftar nomor meja yang tersedia |
| **Conditional (if)** | Memeriksa kondisi status meja |
| **Logical OR (||)** | Memberikan nilai default 0 jika sandwich belum ada |

---

## 📚 Referensi

- [MDN - for...of statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
- [MDN - Working with Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
- [MDN - Array.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

---

**📌 Catatan:** Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi `processShopOrders`. Jika ada pertanyaan, jangan ragu untuk bertanya! 😊
