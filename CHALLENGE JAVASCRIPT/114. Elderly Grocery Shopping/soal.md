# 🛒 Challenge Belanja Grocery untuk Lansia

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy` ⭐

### 🎯 Objektif
Buat sebuah function bernama `groceryBasket` yang membantu seorang lansia menentukan item mana saja yang benar-benar bisa dibeli dari toko dadakan seorang supir taksi berdasarkan ketersediaan barang.

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
groceryBasket(storeItems, wantedItems)
```

### 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `storeItems` | `Array<string>` | Item-item yang tersedia di toko dadakan supir taksi |
| `wantedItems` | `Array<string>` | Item-item yang ingin dibeli oleh lansia |

### 📤 Return Value
- **Type:** `Array<string>`
- **Deskripsi:** Item-item yang benar-benar bisa dibeli lansia (irisan antara item yang diinginkan dan tersedia)

---

## 💡 Deskripsi Problem

Seorang lansia sedang berbelanja di toko dadakan seorang supir taksi dan membutuhkan bantuan untuk menentukan item mana dari daftar belanjanya yang benar-benar tersedia untuk dibeli.

Function kamu harus:
- ✅ Membandingkan item yang diinginkan dengan inventory toko
- ✅ Mengembalikan hanya item yang diinginkan DAN tersedia
- ✅ Menangani edge case (tidak ada yang cocok, semua cocok)

---

## 📝 Contoh Penggunaan

```javascript
// Inventory toko
let storeItems = ['bread', 'milk', 'eggs', 'soap', 'toothpaste'];

// Daftar belanja customer
let wantedItems = ['bread', 'eggs', 'coffee', 'medicine'];

// Pemanggilan function
let purchasedItems = groceryBasket(storeItems, wantedItems);

// Output yang diharapkan
console.log(purchasedItems); 
// Output: ['bread', 'eggs']
```

### 🔍 Breakdown Contoh

| Item | Tersedia di Toko | Diinginkan Customer | Bisa Dibeli |
|------|------------------|-------------------|-------------|
| `bread` | ✅ | ✅ | ✅ |
| `eggs` | ✅ | ✅ | ✅ |
| `coffee` | ❌ | ✅ | ❌ |
| `medicine` | ❌ | ✅ | ❌ |

**Hasil:** Hanya `['bread', 'eggs']` yang bisa dibeli.

---

## 🎯 Skenario Testing

### Skenario 1: Sebagian Cocok
```javascript
storeItems = ['apple', 'banana', 'orange'];
wantedItems = ['apple', 'grape', 'banana'];
// Expected: ['apple', 'banana']
```

### Skenario 2: Tidak Ada yang Cocok
```javascript
storeItems = ['tea', 'sugar', 'rice'];
wantedItems = ['coffee', 'honey', 'bread'];
// Expected: []
```

### Skenario 3: Semua Cocok
```javascript
storeItems = ['water', 'juice', 'soda'];
wantedItems = ['water', 'juice'];
// Expected: ['water', 'juice']
```

---

## ⚠️ Pertimbangan Penting

- 🔄 Tangani array kosong dengan baik
- 📝 Pertahankan urutan asli dari `wantedItems`
- 🎯 Pastikan pencocokan string yang tepat (case-sensitive)
- ⚡ Pertimbangkan performa untuk dataset yang lebih besar

---

## 🏆 Kriteria Sukses

Solusi kamu harus bisa menangani semua edge case dengan benar dan mengembalikan irisan dari kedua input array sambil mempertahankan urutan item seperti yang muncul dalam array `wantedItems`.
