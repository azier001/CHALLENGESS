# 🔬 Reverse Specimen Words Challenge

## 📋 Deskripsi Challenge

**Tingkat Kesulitan:** `Easy`

Sebagai seorang entomolog yang penasaran sedang memeriksa spesimen serangga yang terkena penyakit dengan pena berujung, Anda telah memutuskan untuk mengkodekan observasi Anda dengan membalik huruf-huruf dalam setiap kata. Tugas Anda adalah membuat function yang menerima kalimat tentang observasi serangga dan mengembalikan kalimat baru dimana huruf-huruf setiap kata dibalik, namun tetap mempertahankan urutan kata aslinya.

---

## 🎯 Tujuan

Buat function bernama `reverseSpecimenWords` yang menerima `observation` sebagai parameter dan mengembalikan versi encoded dari observasi tersebut.

---

## 📝 Spesifikasi Function

### Nama Function
```javascript
reverseSpecimenWords(observation)
```

### Parameter
- **`observation`** *(string)*: Kalimat yang mendeskripsikan observasi serangga
  - Dapat berisi huruf, angka, dan tanda baca dasar
  - Kata-kata dipisahkan oleh spasi

### Return Value
- **Type:** `string`
- **Deskripsi:** Kalimat baru dimana huruf-huruf setiap kata dibalik, tetapi kata-kata tetap dalam urutan yang sama

---

## 🔧 Strategi Implementasi

Ikuti pendekatan step-by-step berikut untuk menyelesaikan masalah ini:

1. **Split input string** menjadi array kata-kata
2. **Buat array baru** dimana setiap kata dibalik
3. **Join array** kata-kata yang telah dibalik kembali menjadi string tunggal

### 💡 Catatan Penting

> **Penanganan Tanda Baca:** Tanda baca harus tetap berada di posisi aslinya relatif terhadap kata yang melekat padanya.

> **Preservasi Spasi:** Pertahankan spasi yang tepat antara kata-kata dalam output.

---

## 📚 Contoh Penggunaan

```javascript
// Contoh pemanggilan function
const observation = "The beetle crawls slowly.";
const encoded = reverseSpecimenWords(observation);
console.log(encoded); // Expected output: "ehT elteeb slwarc ylwols."
```

---

## ✅ Skenario Testing

Pertimbangkan untuk menguji function Anda dengan tipe input berikut:

- **Kata sederhana:** `"ant bee"`
- **Kata dengan tanda baca:** `"Hello, world!"`
- **Konten campuran:** `"The spider has 8 legs."`
- **Kata tunggal:** `"butterfly"`
- **String kosong:** `""`

---

## 🐛 Edge Cases yang Perlu Dipertimbangkan

- Kata-kata yang mengandung angka
- Multiple spasi antar kata
- Tanda baca di awal atau akhir kata
- Karakter khusus dan simbol

---

*Happy coding, fellow entomologist! 🦗*
