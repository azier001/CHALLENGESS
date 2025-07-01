
# 🌿 Tantangan Pemeliharaan Taman

### 🧩 Tingkat Kesulitan: Mudah

---

## 📋 Deskripsi

Buatlah fungsi bernama `maintainGarden` yang mensimulasikan pemeliharaan taman dengan **menyiram tanaman** dan **memangkas pagar tanaman**.

---

## 🛠️ Tanda Tangan Fungsi

```javascript
function maintainGarden(gardenBed, hedge)
```

---

## 🧪 Parameter

| Parameter   | Tipe   | Deskripsi                                            |
|-------------|--------|------------------------------------------------------|
| `gardenBed` | string | `'w'` untuk tanaman yang sudah disiram, `'d'` untuk tanaman kering. Ganti `'d'` dengan `'w'`. |
| `hedge`     | string | `'g'` untuk bagian pagar yang sudah dipangkas, `'u'` untuk bagian yang belum dipangkas. Balik substring `'u'`. |

---

## 🔄 Perilaku

### 🌱 Area Tanaman

- Tanaman kering (`'d'`) harus disiram — ganti **setiap `'d'` dengan `'w'`**.

### ✂️ Pagar Tanaman

- Bagian yang belum dipangkas (`'u'`) harus dibalik urutannya.  
  Contoh: `'guuuugg'` → balik bagian `'uuu'` → `'guuuggug'`.

> **Catatan**: Hanya balik bagian substring `'u'` yang berurutan.

---

## 📤 Keluaran

Sebuah array dengan **dua elemen**:

1. String area tanaman yang **sudah disiram semua**.
2. String pagar taman yang **rapi setelah dipangkas**.

---

## ✅ Contoh

```javascript
maintainGarden("dwdwd", "guuugguu")
// ➞ ["wwwww", "guuuggug"]
```

---

## 🌟 Catatan

- Gunakan regular expressions atau manipulasi string untuk implementasi yang efisien.
- Fokus pada kode yang **bersih dan mudah dibaca** untuk pemeliharaan jangka panjang.

---
