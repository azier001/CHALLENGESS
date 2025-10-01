# 🌿 Botanist's Rare Plant Search

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

---

## 🎯 Deskripsi Masalah

Seorang botanist yang frustasi sedang mencari tanaman langka tertentu di lapangan yang penuh dengan berbagai tanaman. Karena kebingungan mereka, beberapa nama tanaman dalam catatan mereka mungkin secara tidak sengaja **terbalik**. 

Tugas Anda adalah membantu botanist menemukan tanaman langka yang mereka cari dengan membuat function pencarian yang memperhitungkan ejaan normal dan terbalik.

---

## 💻 Persyaratan Function

### Function Signature

```javascript
function findRarePlant(plantNames, rarePlant)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `plantNames` | `array` | Array string yang merepresentasikan nama-nama tanaman berbeda yang ditemukan di lapangan. Beberapa nama mungkin terbalik. |
| `rarePlant` | `string` | Nama tanaman langka yang dicari botanist. |

### Return Value

- **Type:** `integer`
- **Mengembalikan:** 
  - **Index** dari tanaman yang cocok dalam array `plantNames` (jika ditemukan dalam bentuk normal atau terbalik)
  - `-1` jika tanaman tidak ditemukan

---

## 🔧 Panduan Implementasi

### Helper Function

Anda dapat menggunakan helper function ini untuk membalikkan string:

```javascript
function reverseString(str) {
    return str.split('').reverse().join('');
}
```

### Task Checklist

- [ ] Cari melalui array `plantNames`
- [ ] Periksa apakah `rarePlant` cocok dengan nama tanaman (ejaan normal)
- [ ] Periksa apakah `rarePlant` cocok dengan nama tanaman (ejaan terbalik)
- [ ] Return index dari kecocokan pertama yang ditemukan
- [ ] Return `-1` jika tidak ada kecocokan yang ditemukan

---

## 📝 Contoh Skenario

### Skenario 1: Normal Match
```javascript
plantNames = ["rose", "tulip", "orchid"]
rarePlant = "tulip"
// Expected output: 1
```

### Skenario 2: Reversed Match
```javascript
plantNames = ["rose", "pilut", "orchid"]
rarePlant = "tulip"
// Expected output: 1 (karena "pilut" dibalik menjadi "tulip")
```

### Skenario 3: Not Found
```javascript
plantNames = ["rose", "orchid", "daisy"]
rarePlant = "tulip"
// Expected output: -1
```

---

## 💡 Tips

- Pertimbangkan bentuk normal dan terbalik dari nama tanaman dalam array
- Nama tanaman langka (`rarePlant`) harus dibandingkan dengan kedua bentuk
- Ingat untuk mengembalikan index yang **pertama** cocok
- Method manipulasi string seperti `split()`, `reverse()`, dan `join()` adalah teman Anda!

---

## 🚀 Siap Memulai?

Sekarang giliran Anda untuk mengimplementasikan function `findRarePlant` dan membantu botanist menemukan tanaman langka mereka yang berharga!
