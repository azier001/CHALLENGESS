# 🃏 Penyusun Nomor Kartu

## 🎯 Tantangan

**Tingkat Kesulitan:** Mudah

Kamu dan teman-temanmu sedang membuat kartu ucapan di sore yang nyaman.  
Kamu ingin menyusun angka-angka spesial (seperti tanggal ulang tahun, hari jadi, atau angka keberuntungan) di kartu dengan pola tertentu.

---

## 📋 Deskripsi Tugas

Buatlah sebuah fungsi bernama `arrangeCardNumbers` yang menerima sebuah array angka dan mengembalikan **array baru** dengan susunan angka sebagai berikut:

### ✅ Aturan Penyusunan

1. **Angka genap** harus ditempatkan **terlebih dahulu**, dalam **urutan menaik**
2. **Angka ganjil** ditempatkan **setelahnya**, dalam **urutan menurun**

---

## 🧾 Tanda Tangan Fungsi

```javascript
function arrangeCardNumbers(numbers)
```

### 📥 Parameter:

- `numbers` (array):  
  Sebuah array yang berisi bilangan bulat yang merupakan angka-angka spesial untuk disusun di kartu.

### 📤 Keluaran:

- Array baru dengan angka-angka yang telah disusun sesuai pola yang ditentukan.

---

## 💡 Contoh

```javascript
arrangeCardNumbers([3, 2, 8, 5, 7, 4])
// Output: [2, 4, 8, 7, 5, 3]
```

---





## 📝 Catatan

- Fungsi ini berguna untuk menyusun pola angka dekoratif pada kartu, poster, atau ucapan digital.
- Ingat bahwa penyortiran tergantung pada klasifikasi genap/ganjil.

---
