# 🎯 Check Event Supplies

## Ringkasan Challenge

**Difficulty:** `Easy`

---

## 📋 Deskripsi Soal

Buatlah sebuah function `checkSupplies` yang menerima `list1`, `list2` dan `item` dan mengembalikan boolean yang menunjukkan apakah item tersebut ditemukan dalam list gabungan.

Function ini menggabungkan dua array supplies untuk acara outdoor Anda dan memeriksa apakah item tertentu ada dalam list yang digabungkan.

---

## 🔧 Function Signature

```javascript
function checkSupplies(list1, list2, item)
```

---

## 📥 Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `list1` | `array` | List pertama dari event supplies |
| `list2` | `array` | List kedua dari event supplies |
| `item` | `string` | Nama item yang dicari |

---

## 📤 Returns

**Type:** `Boolean`

**Deskripsi:** Menunjukkan apakah item ditemukan dalam supply lists gabungan.

**Format:** `true` atau `false`

---

## 💡 Contoh Penggunaan

```javascript
// Contoh 1
const supplies1 = ['tent', 'sleeping bag', 'flashlight'];
const supplies2 = ['cooler', 'grill', 'chairs'];
checkSupplies(supplies1, supplies2, 'flashlight');
// Expected output: true

// Contoh 2
checkSupplies(supplies1, supplies2, 'umbrella');
// Expected output: false
```

---

## ✅ Persyaratan

- Gabungkan kedua supply lists
- Cari item yang ditentukan dalam list gabungan
- Return `true` jika item ada, `false` jika tidak

---

## 🎓 Skills yang Dipraktikkan

- Manipulasi array
- Penggabungan array
- Operasi pencarian
- Logika boolean

---

> **Catatan:** Ini adalah challenge level mudah yang dirancang untuk melatih operasi array dasar dan fungsi pencarian.
