# 🌱 Community Garden Inventory

> **Tingkat Kesulitan:** `Easy`

---

## 📋 Deskripsi Challenge

Buat sebuah function bernama `gardenInventory` yang membantu seorang penjaga kebun mengelola inventaris kebun komunitas dengan membandingkan nama-nama tanaman dan mengorganisirnya ke dalam berbagai section.

Function ini membandingkan tanaman yang sudah ada dengan tanaman baru yang datang, mengidentifikasi duplikat dan mengorganisir inventaris dengan efisien.

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
gardenInventory(currentPlants, newPlants)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `currentPlants` | `array` | Array berisi string yang merepresentasikan nama-nama tanaman yang saat ini ada di kebun |
| `newPlants` | `array` | Array berisi string yang merepresentasikan nama-nama tanaman baru yang akan ditambahkan |

### Return Value

Function mengembalikan sebuah **object** dengan struktur berikut:

```javascript
{
  existingPlants: [...],  // Array of strings
  newPlants: [...],       // Array of strings
  totalPlants: 0          // Integer
}
```

#### Key Return Object

- **`existingPlants`**: Array berisi string nama tanaman yang sudah ada di kebun (duplikat dari list tanaman baru)

- **`newPlants`**: Array berisi string nama tanaman yang baru dan akan ditambahkan ke kebun

- **`totalPlants`**: Integer yang merepresentasikan total jumlah tanaman unik setelah menambahkan tanaman baru

---

## 💡 Tips Implementasi

- Gunakan **string comparison** untuk mengecek apakah tanaman sudah ada di kebun
- Gunakan **array** untuk mengorganisir dan menyimpan informasi tanaman
- Pertimbangkan case sensitivity saat membandingkan nama tanaman
- Pastikan tidak ada duplikat entries dalam perhitungan akhir

---

## 📝 Contoh Penggunaan

```javascript
const current = ['Rose', 'Tulip', 'Daisy'];
const incoming = ['Tulip', 'Sunflower', 'Rose', 'Lily'];

const result = gardenInventory(current, incoming);

console.log(result);
// Expected output:
// {
//   existingPlants: ['Tulip', 'Rose'],
//   newPlants: ['Sunflower', 'Lily'],
//   totalPlants: 5
// }
```

---

## 🎯 Konsep Utama

- Manipulasi array
- Perbandingan string
- Pembuatan object dan assignment property
- Operasi set (union, intersection)
- Organisasi dan kategorisasi data

---

**Semoga berhasil dengan implementasinya! 🌻**
