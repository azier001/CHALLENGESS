# 🌿 Dokumentasi Fungsi `analyzePlantSpecimen`

## 📌 Deskripsi Fungsi

Fungsi `analyzePlantSpecimen` digunakan untuk menganalisis sebuah spesimen tanaman berdasarkan nama, jumlah daun, dan tinggi tanaman. Fungsi ini menghitung luas daun, luas total semua daun, mengonversi tinggi ke satuan inci, mengklasifikasikan tinggi tanaman, dan menghasilkan kode warna berdasarkan nama tanaman.

---

## 🧩 Kode Fungsi

```javascript
function analyzePlantSpecimen(plantName, numberOfLeaves, plantHeight) {
  const leafWidth = 1.5;
  const singleLeafArea = plantHeight * leafWidth;
  const totalLeafArea = singleLeafArea * numberOfLeaves;
  const heightInInches = (plantHeight / 2.54).toFixed(1);

  let heightCategory = "";
  if (plantHeight < 30) {
    heightCategory = "short";
  } else if (plantHeight <= 100) {
    heightCategory = "medium";
  } else {
    heightCategory = "tall";
  }

  const colorCode = plantName[0].toUpperCase().repeat(3);

  return `Plant: ${plantName}\n` +
         `Number of Leaves: ${numberOfLeaves}\n` +
         `Plant Height: ${plantHeight} cm (${heightInInches} inches)\n` +
         `Leaf Area: ${singleLeafArea.toFixed(2)} sq cm\n` +
         `Total Leaf Area: ${totalLeafArea.toFixed(2)} sq cm\n` +
         `Height Classification: ${heightCategory}\n` +
         `Color Code: ${colorCode}`;
}
```

---

## 📥 Parameter

| Nama             | Tipe   | Deskripsi                               |
| ---------------- | ------ | --------------------------------------- |
| `plantName`      | String | Nama dari spesimen tanaman.             |
| `numberOfLeaves` | Number | Jumlah daun yang dimiliki oleh tanaman. |
| `plantHeight`    | Number | Tinggi tanaman dalam satuan sentimeter. |

---

## 🔄 Proses yang Dilakukan

1. Menghitung **luas satu daun** menggunakan rumus: `tinggi × 1.5`.
2. Menghitung **total luas daun**: `luas satu daun × jumlah daun`.
3. Mengonversi tinggi tanaman ke satuan **inci**, dibulatkan ke 1 angka di belakang koma.
4. Menentukan **klasifikasi tinggi tanaman**:

   * `< 30 cm` → `short`
   * `30 - 100 cm` → `medium`
   * `> 100 cm` → `tall`
5. Membuat **kode warna** dari 3 huruf pertama (kapital) nama tanaman.
6. Mengembalikan semua informasi dalam string terformat.

---

## 💡 Contoh Penggunaan

```javascript
console.log(analyzePlantSpecimen("Moss", 5000, 2));
```

### ✅ Output

```
Plant: Moss
Number of Leaves: 5000
Plant Height: 2 cm (0.8 inches)
Leaf Area: 3.00 sq cm
Total Leaf Area: 15000.00 sq cm
Height Classification: short
Color Code: MMM
```

---

## 📎 Catatan

* Fungsi ini tidak melakukan validasi input.
* Semua nilai numerik ditampilkan dengan dua angka di belakang koma.
* Kode warna bersifat simbolik dan hanya menggunakan huruf pertama dari nama tanaman.

---

Gunakan fungsi ini untuk menganalisis data tanaman secara sederhana namun informatif! 🌱
