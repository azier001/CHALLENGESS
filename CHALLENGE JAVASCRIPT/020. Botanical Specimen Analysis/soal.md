# 🌿 Botanical Specimen Analysis

## 🧪 Tantangan

**Tingkat Kesulitan:** Mudah

Buatlah sebuah fungsi bernama `analyzePlantSpecimen` yang menerima tiga parameter: `plantName`, `numberOfLeaves`, dan `plantHeight`.

Fungsi ini akan menganalisis spesimen tanaman dan mengembalikan string terformat yang berisi informasi tentang tanaman tersebut.

---

## ✅ Instruksi

Ikuti langkah-langkah berikut untuk melakukan analisis:

1. **Hitung luas satu daun:**

   * Anggap setiap daun berbentuk persegi panjang dengan lebar `1.5 cm`.
   * Rumus: `leafArea = plantHeight * 1.5`

2. **Hitung total luas daun:**

   * Kalikan luas satu daun dengan jumlah daun.

3. **Konversi tinggi tanaman ke inci:**

   * Gunakan rumus: `heightInInches = plantHeight / 2.54`
   * Bulatkan hasilnya ke satu angka di belakang koma.

4. **Klasifikasikan tinggi tanaman:**

   * Jika tinggi < 30 cm → `"short"`
   * Jika 30 cm ≤ tinggi ≤ 100 cm → `"medium"`
   * Jika tinggi > 100 cm → `"tall"`

5. **Buat kode warna:**

   * Ulangi huruf pertama dari nama tanaman sebanyak tiga kali (misalnya, "Fern" → "FFF").

6. **Kembalikan string terformat** yang berisi semua nilai yang telah dihitung.

---

## 📥 Parameter

| Nama             | Tipe   | Deskripsi                               |
| ---------------- | ------ | --------------------------------------- |
| `plantName`      | String | Nama dari spesimen tanaman.             |
| `numberOfLeaves` | Number | Jumlah daun yang dimiliki oleh tanaman. |
| `plantHeight`    | Number | Tinggi tanaman dalam satuan sentimeter. |

---

## 📤 Nilai Kembali

Sebuah string terformat yang berisi:

* Nama tanaman
* Jumlah daun
* Tinggi tanaman dalam cm dan inci
* Luas satu daun
* Total luas daun
* Klasifikasi tinggi
* Kode warna

---

## 💡 Contoh

```javascript
analyzePlantSpecimen("Moss", 5000, 2);
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

Semoga sukses! 🍀
