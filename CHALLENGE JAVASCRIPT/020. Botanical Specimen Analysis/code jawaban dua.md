# 🌿 Dokumentasi Fungsi `analyzePlantSpecimen`

## 📌 Deskripsi Fungsi

Fungsi `analyzePlantSpecimen` digunakan untuk menganalisis spesimen tanaman berdasarkan nama, jumlah daun, dan tinggi tanaman. Fungsi ini menghitung luas daun tunggal, total luas daun, mengonversi tinggi tanaman ke inci, mengklasifikasikan tinggi, dan membuat kode warna berdasarkan nama tanaman.

---

## 🧩 Kode Fungsi

```javascript
function analyzePlantSpecimen(plantName, numberOfLeaves, plantHeight) {
  // Calculate the area of a single leaf
  const singleLeafArea = plantHeight * 1.5;

  // Calculate the total leaf area
  const totalLeafArea = singleLeafArea * numberOfLeaves;

  // Convert plant height to inches and round to one decimal place
  const heightInInches = Number((plantHeight / 2.54).toFixed(1));

  // Classify the plant height
  let heightClassification;
  if (plantHeight < 30) {
    heightClassification = "short";
  } else if (plantHeight <= 100) {
    heightClassification = "medium";
  } else {
    heightClassification = "tall";
  }

  // Create color code
  const colorCode = plantName[0].toUpperCase().repeat(3);

  // Format the result string
  const result = `Plant: ${plantName}\n` +
                 `Number of Leaves: ${numberOfLeaves}\n` +
                 `Plant Height: ${plantHeight} cm (${heightInInches} inches)\n` +
                 `Leaf Area: ${singleLeafArea.toFixed(2)} sq cm\n` +
                 `Total Leaf Area: ${totalLeafArea.toFixed(2)} sq cm\n` +
                 `Height Classification: ${heightClassification}\n` +
                 `Color Code: ${colorCode}`;

  return result;
}
```

---

## 📥 Parameter

| Nama             | Tipe   | Deskripsi                       |
| ---------------- | ------ | ------------------------------- |
| `plantName`      | String | Nama spesimen tanaman           |
| `numberOfLeaves` | Number | Jumlah daun pada tanaman        |
| `plantHeight`    | Number | Tinggi tanaman dalam sentimeter |

---

## 🔄 Proses Analisis

1. **Luas satu daun** dihitung dengan rumus: `plantHeight × 1.5`.
2. **Total luas daun** = luas satu daun × jumlah daun.
3. **Konversi tinggi**: dari cm ke inci (dibulatkan 1 angka desimal).
4. **Klasifikasi tinggi tanaman**:

   * `< 30 cm` → `short`
   * `30–100 cm` → `medium`
   * `> 100 cm` → `tall`
5. **Kode warna**: 3 huruf kapital pertama dari nama tanaman.
6. Hasil dikembalikan dalam bentuk string yang terformat.

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

* Tidak ada validasi untuk parameter input, asumsikan data selalu valid.
* Kode warna hanya simbolik dan berdasarkan huruf pertama nama tanaman.
* Semua angka ditampilkan dengan dua angka di belakang koma untuk kejelasan.

---

Gunakan fungsi ini untuk mengolah dan menyajikan informasi botani dengan rapi dan informatif! 🌱
