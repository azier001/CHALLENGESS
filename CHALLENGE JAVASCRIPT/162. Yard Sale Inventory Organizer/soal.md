# 🏷️ Yard Sale Inventory Organizer

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Medium`

Buat sebuah function yang mengubah string item yard sale yang tidak terformat menjadi ringkasan inventory yang terorganisir dengan baik, lengkap dengan kategorisasi dan kalkulasi finansial.

---

## 🎯 Tujuan

Tulis sebuah function bernama `organizeYardSale` yang memproses array dari string item dan mengembalikan object ringkasan inventory yang komprehensif dengan organisasi berbasis kategori dan total.

---

## 🔧 Function Signature

```javascript
function organizeYardSale(items)
```

---

## 📥 Spesifikasi Input

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `items` | `Array<string>` | Array dari string item dalam format tertentu |

### Format Item String

Setiap item mengikuti pola ini:

```
"category:name:price"
```

**Contoh:**
```javascript
[
  "furniture:chair:15.99",
  "kitchen:blender:12.50",
  "furniture:table:30.00"
]
```

---

## 📤 Spesifikasi Output

### Return Value

Sebuah object dimana:
- **Keys** merepresentasikan kategori item
- **Values** adalah object yang berisi:
  - `count`: Jumlah item dalam kategori
  - `total`: Jumlah dari semua harga item dalam kategori

### Format Output

```javascript
{
  "category_name": {
    "count": <number>,
    "total": <number>
  }
}
```

### Contoh Output

```javascript
{
  "furniture": {
    "count": 2,
    "total": 45.99
  },
  "kitchen": {
    "count": 1,
    "total": 12.50
  }
}
```

---

## 🧮 Logic Pemrosesan

Function harus mengimplementasikan langkah-langkah berikut:

### 1. **Parse Item Strings**
   - Split setiap string dengan delimiter `:`
   - Extract tiga komponen: `category`, `name`, dan `price`

### 2. **Kategorisasi Item**
   - Group item berdasarkan kategorinya
   - Increment count untuk setiap item yang ditambahkan ke kategori

### 3. **Hitung Total Kategori**
   - Akumulasi harga item individual
   - Hitung total harga per kategori

### 4. **Generate Summary**
   - Return object yang terorganisir dengan semua kategori dan statistiknya

---

## 💡 Persyaratan Utama

- ✅ Parse semua item string dengan benar
- ✅ Handle multiple item per kategori
- ✅ Hitung total harga dengan akurat
- ✅ Pertahankan count item yang tepat
- ✅ Return data dalam format yang ditentukan

---

## 🧪 Contoh Test Case

### Input
```javascript
const items = [
  "furniture:chair:15.99",
  "kitchen:blender:12.50",
  "furniture:table:30.00",
  "electronics:radio:8.00",
  "kitchen:pot:5.50"
];
```

### Output yang Diharapkan
```javascript
{
  "furniture": {
    "count": 2,
    "total": 45.99
  },
  "kitchen": {
    "count": 2,
    "total": 18.00
  },
  "electronics": {
    "count": 1,
    "total": 8.00
  }
}
```

---

## 🚀 Memulai

Mulai dengan:
1. Membuat struktur function
2. Mengimplementasikan logic parsing string
3. Membangun mekanisme grouping kategori
4. Menambahkan logic kalkulasi
5. Testing dengan berbagai input

Semoga berhasil! 🎉
