# 🦋 Butterfly Colors at the Pumpkin Patch

## Ringkasan Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function yang menghitung kemunculan berbagai warna kupu-kupu yang diamati di kebun labu. Ini adalah challenge ramah pemula yang sempurna untuk fokus pada iterasi array dan manipulasi object.

---

## 📋 Deskripsi Masalah

Anda perlu mengimplementasikan function bernama `countButterflyColors` yang memproses array warna kupu-kupu dan mengembalikan summary object yang menunjukkan berapa kali setiap warna muncul.

### Yang Harus Dilakukan Function:

1. **Menerima** array string warna sebagai input
2. **Melakukan iterasi** melalui setiap warna dalam array
3. **Menghitung** berapa kali setiap warna unik muncul
4. **Mengembalikan** object dengan warna sebagai key dan jumlah sebagai value

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
countButterflyColors
```

### Parameter

| Parameter | Type | Deskripsi | Batasan |
|-----------|------|-----------|---------|
| `colors` | `Array<String>` | Array string warna kupu-kupu | Panjang: 2-100 elemen |

### Return Value

- **Type:** `Object`
- **Struktur:** `{ namaWarna: jumlah, ... }`
- **Key:** Nama warna unik (string)
- **Value:** Jumlah kemunculan (integer)

---

## 📊 Contoh Penggunaan

```javascript
// Contoh Input
const butterflyColors = ["red", "blue", "red", "yellow", "blue", "red"];

// Output yang Diharapkan
{
  "red": 3,
  "blue": 2,
  "yellow": 1
}
```

---

## ✅ Checklist Persyaratan

- [ ] Nama function harus persis `countButterflyColors`
- [ ] Harus menerima satu parameter bernama `colors`
- [ ] Menangani array dengan 2-100 elemen
- [ ] Mengembalikan object dengan pasangan warna-jumlah
- [ ] Menghitung setiap warna unik dengan benar
- [ ] Menangani warna duplikat dengan tepat

---

## 🎯 Konsep Utama

Challenge ini membantu Anda berlatih:

- **Array Iteration** - Melakukan loop melalui elemen array
- **Object Manipulation** - Membuat dan memperbarui property object
- **Conditional Logic** - Memeriksa apakah property ada
- **Counting Algorithm** - Melacak frekuensi kemunculan

---

## 💡 Petunjuk

> **Tip 1:** Pertimbangkan menggunakan loop untuk melakukan iterasi melalui array colors
> 
> **Tip 2:** Periksa apakah warna sudah ada dalam result object sebelum menambah nilai
> 
> **Tip 3:** Inisialisasi warna baru dengan count 1, increment yang sudah ada

---

## 🏷️ Tag

`#JavaScript` `#Arrays` `#Objects` `#Counting` `#Beginner` `#DataStructures`
