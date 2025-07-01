# 🥪 Two-Decker Sandwich Maker

## 🧠 Deskripsi Tantangan

**Tingkat Kesulitan:** 🟢 Mudah  
Buatlah sebuah fungsi bernama `makeSandwich` yang menerima tiga parameter:

- `topBread`
- `filling`
- `bottomBread`

Tujuanmu adalah menentukan apakah bahan-bahan yang diberikan dapat membentuk **sandwich dua lapis yang valid**. Fungsi harus mengembalikan pesan yang sesuai berdasarkan input tersebut.

---

## 📜 Aturan Membuat Sandwich

Agar sandwich dianggap valid, ikuti aturan berikut:

✅ **Jenis Roti:**
- `topBread` dan `bottomBread` harus berupa:
  - `"white"` 🍞 (putih)
  - `"wheat"` 🌾 (gandum)

✅ **Isian yang Diperbolehkan:**
- `filling` harus salah satu dari:
  - `"cheese"` 🧀 (keju)
  - `"ham"` 🍖 (daging asap)
  - `"lettuce"` 🥬 (selada)

✅ **Jenis Roti Harus Sama:**
- `topBread` dan `bottomBread` harus memiliki **jenis yang sama**.

---

## 🔢 Parameter Fungsi

| Parameter     | Tipe    | Deskripsi                                            |
|---------------|---------|------------------------------------------------------|
| `topBread`    | string  | Jenis roti bagian atas (`"white"` atau `"wheat"`)   |
| `filling`     | string  | Isi sandwich (`"cheese"`, `"ham"`, atau `"lettuce"`)|
| `bottomBread` | string  | Jenis roti bagian bawah (`"white"` atau `"wheat"`)  |

---

## 🧾 Nilai Kembali (Return)

Fungsi harus mengembalikan salah satu dari pesan berikut:

- ✅ **Jika semua valid:**  
  `"Delicious [filling] sandwich on [bread type] bread!"`

- ❌ **Jika jenis roti tidak sama:**  
  `"Mismatched bread types!"`

- ❌ **Jika jenis roti tidak valid:**  
  `"Invalid bread type!"`

- ❌ **Jika isian tidak valid:**  
  `"Invalid filling!"`

---

## ✅ Contoh Penggunaan

```javascript
makeSandwich("white", "cheese", "white");
// ➜ "Delicious cheese sandwich on white bread!"

makeSandwich("white", "bacon", "white");
// ➜ "Invalid filling!"

makeSandwich("wheat", "ham", "white");
// ➜ "Mismatched bread types!"

makeSandwich("rye", "lettuce", "wheat");
// ➜ "Invalid bread type!"
