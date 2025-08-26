# 🚂 Perjalanan Kereta Melalui Malam

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`  
**Jenis Challenge:** Manipulasi String

---

## 🎯 Tujuan

Buat sebuah function bernama `trainJourney` yang mensimulasikan perjalanan magis kereta melalui malam dengan mentransformasi input string melalui serangkaian operasi spesifik.

---

## 📝 Spesifikasi Function

### Function Signature
```javascript
function trainJourney(string)
```

### Parameter
- **Input:** `string` - String asli yang merepresentasikan rute kereta

### Return Value
- **Output:** `string` - String yang telah ditransformasi merepresentasikan perjalanan malam yang telah selesai

---

## 🔧 Langkah-langkah Transformasi

Function harus melakukan operasi berikut **secara berurutan**:

### Langkah 1: 🔄 Balik Urutan Kata
Balik urutan kata-kata dalam input string sambil mempertahankan kata itu sendiri tetap utuh.

### Langkah 2: 🔤 Kapitalisasi Setiap Karakter ke-3
Dimulai dari **karakter pertama** (indeks 0), ubah menjadi huruf kapital setiap karakter ke-3 dalam string yang sudah dibalik.
- Karakter pada posisi: 0, 3, 6, 9, 12, ... harus dikapitalkan

### Langkah 3: 🚂 Tambahkan Suara Kereta
Gabungkan string `" choo choo!"` ke bagian akhir string yang sudah dimodifikasi.

---

## 💡 Contoh Penjelasan Langkah demi Langkah

```
Input: "hello world night"

Langkah 1 - Balik kata-kata:
"night world hello"

Langkah 2 - Kapitalkan setiap karakter ke-3 (posisi 0, 3, 6, 9, 12...):
"NigHt World hEllo"
 ↑  ↑     ↑   ↑

Langkah 3 - Tambahkan suara kereta:
"NigHt World hEllo choo choo!"

Output Akhir: "NigHt World hEllo choo choo!"
```

---

## ✅ Checklist Persyaratan

- [ ] Function diberi nama `trainJourney`
- [ ] Menerima satu parameter string
- [ ] Mengembalikan sebuah string
- [ ] Dengan benar membalik urutan kata
- [ ] Mengkapitalkan setiap karakter ke-3 dimulai dari indeks 0
- [ ] Menambahkan `" choo choo!"` ke hasil akhir
- [ ] Menangani edge case (string kosong, kata tunggal, dll.)

---

## 🚀 Tips Implementasi

> **Hint:** Pertimbangkan untuk memecah masalah menjadi function-function kecil untuk setiap langkah transformasi agar kode Anda lebih mudah dibaca dan dipelihara.

> **Catatan:** Ingat bahwa indeks string dimulai dari 0, jadi "karakter pertama" untuk kapitalisasi berada di indeks 0.

---

## 🧪 Menguji Solusi Anda

Pastikan untuk menguji function Anda dengan berbagai input:
- Kata tunggal
- Beberapa kata
- String kosong
- String dengan karakter khusus
- Kalimat panjang

Selamat coding! 🎉
