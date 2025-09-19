# 🧠 Reversing Thoughts in the Psychiatrist's Office

> **Challenge Level:** `Easy` 

## 📋 Gambaran Umum

Di ruang praktik psikiater pada hari yang mendung, seorang pasien mengungkapkan kekhawatirannya. Psikiater memutuskan untuk membantu pasien mendapatkan perspektif baru dengan membalik pikiran mereka. Tugas Anda adalah mengimplementasikan proses pembalikan pikiran yang melambangkan pergeseran perspektif dan introspeksi yang lebih dalam.

## 🎯 Deskripsi Challenge

Buatlah function bernama `reverseThoughts` yang melakukan **double reversal** pada pikiran pasien:

1. **Membalik urutan kata-kata** dalam kalimat
2. **Membalik karakter dalam setiap kata**

Double reversal ini mewakili teknik terapeutik untuk membantu pasien melihat pikiran mereka dari sudut yang benar-benar berbeda.

## 📝 Spesifikasi Function

### Function Signature
```javascript
function reverseThoughts(patientThoughts)
```

### Parameter
- **`patientThoughts`** _(string)_: String yang mewakili pikiran pasien berisi satu atau lebih kata yang dipisahkan oleh spasi.

### Return Value
- **Returns:** String yang mewakili pikiran yang telah dibalik setelah menerapkan teknik double reversal.

## 🔧 Persyaratan Implementasi

### Proses Step-by-Step

1. **Split** string input menjadi array kata-kata
2. **Reverse** urutan kata-kata dalam array
3. **Reverse** karakter dalam setiap kata
4. **Join** kata-kata yang sudah dibalik kembali menjadi string tunggal

### ⚠️ Batasan Penting

> **Catatan:** Jangan gunakan built-in reverse functions. Anda harus mengimplementasikan logic reversal sendiri untuk:
> - Reversal urutan kata
> - Reversal karakter dalam kata

## 💡 Contoh Penggunaan

```javascript
// Input
reverseThoughts("I feel anxious today")

// Proses:
// 1. Split: ["I", "feel", "anxious", "today"]
// 2. Reverse urutan kata: ["today", "anxious", "feel", "I"]
// 3. Reverse karakter dalam setiap kata: ["yadot", "suoixna", "leef", "I"]
// 4. Join: "yadot suoixna leef I"

// Output
"yadot suoixna leef I"
```

## 🎨 Metafora Terapeutik

Teknik double reversal berfungsi sebagai metafora yang kuat:

- **Word Order Reversal**: Mewakili melihat situasi dari hasil akhir kembali ke awal
- **Character Reversal**: Melambangkan pemeriksaan setiap komponen pikiran secara detail dari perspektif baru
- **Combined Effect**: Menciptakan sudut pandang yang benar-benar berubah yang mungkin mengungkapkan wawasan tersembunyi

## 🏆 Kriteria Keberhasilan

Implementasi Anda harus:

- ✅ Menangani kata tunggal dan multiple words dengan benar
- ✅ Mengimplementasikan custom reversal logic (tidak ada built-in reverse functions)
- ✅ Mempertahankan spacing antar kata
- ✅ Bekerja dengan input string yang valid
- ✅ Mengembalikan reversed thoughts yang terformat dengan benar

---

*Good luck membantu pasien mendapatkan perspektif baru melalui code! 🌟*
