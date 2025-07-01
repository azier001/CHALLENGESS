# 💍 **Generator Pola Kotak Perhiasan Antik**

## 📦 Gambaran Umum
Fungsi `createAntiqueJewelryBox` menghasilkan **pola kotak persegi ASCII** yang menyerupai kotak perhiasan antik dengan beberapa lapisan hiasan. Kotak ini terbuat dari karakter `*` (asterisk) dan `.` (titik), yang merepresentasikan bagian luar dan kompartemen ornamen di dalamnya.

Setiap lapisan melambangkan tingkat keindahan—berawal dari bingkai terluar menuju ruang inti yang paling sederhana.

## 🧾 Tanda Tangan Fungsi

```javascript
function createAntiqueJewelryBox(layers)
```

## 📥 Parameter

| Parameter | Tipe   | Deskripsi                                         |
|-----------|--------|---------------------------------------------------|
| `layers`  | number | Bilangan bulat tak negatif (`≥ 0`) yang mewakili jumlah lapisan hiasan. |

## 📤 Nilai Kembali

- Sebuah `string` tunggal yang merepresentasikan pola kotak perhiasan berlapis.
- Setiap baris pola dipisahkan oleh karakter baris baru (`\n`).

## 🧮 Pola & Aturan

- 🧱 **Ukuran kotak** = `2 * layers + 3` (tinggi dan lebar).
- ✨ **Lapisan terluar** diisi penuh dengan `*`.
- 🎨 **Lapisan dalam**:
  - Sudut berisi `*`
  - Bagian dalam berisi `.`
- 🧊 **Bagian inti (paling dalam)**, jika ada, hanya berisi `.`.

## 📌 Contoh Pola

### 🔢 Input: `2`

```
*******
*.....*
*.*.*.*
*.....*
*******
```

### 🔢 Input: `3`

```
*********
*.......*
*.*****.*
*.*...*.*
*.*...*.*
*.*****.*
*.......*
*********
```

## 🛠️ Tips Implementasi

- 🧩 Gunakan **loop bersarang** untuk membangun setiap baris.
- 🧮 Buat matriks dengan ukuran `N x N`, di mana `N = 2 * layers + 3`.
- 🔁 Loop melalui setiap lapisan:
  - Tandai bingkai dengan `*`
  - Isi bagian dalam dengan `.` atau pola `*` sesuai kedalaman

## 📚 Contoh Penggunaan

```javascript
console.log(createAntiqueJewelryBox(2));
```
