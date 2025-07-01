# 🌸 Colorful Flower Garden Composer

## Tingkat Tantangan
**Easy**

---

## 📋 Deskripsi

Buat sebuah function bernama `flowerGardenComposer` yang menerima `flowerNames` dan `separator` sebagai parameter. Function ini bertujuan untuk membuat representasi string yang berwarna-warni dari taman bunga dengan menggabungkan nama-nama bunga dengan warna yang terkait.

---

## 🎯 Persyaratan

Function harus mengikuti langkah-langkah berikut:

1. **Definisikan palet warna**: Buat daftar warna: `["red", "yellow", "pink", "blue", "purple"]`
2. **Inisialisasi penyimpanan hasil**: Buat variabel string kosong untuk menyimpan hasil akhir
3. **Iterasi melalui bunga**: Loop melalui setiap nama bunga dalam array `flowerNames`
4. **Tetapkan warna**: Untuk setiap nama bunga, tentukan warna yang terkait menggunakan indeks modulo jumlah warna
5. **Bangun string**: Gabungkan warna, spasi, dan nama bunga ke string hasil
6. **Tambahkan separator**: Jika bunga saat ini bukan yang terakhir, tambahkan `separator` ke string hasil
7. **Return hasil**: Kembalikan string hasil akhir

---

## 📥 Parameter

| Parameter | Type | Deskripsi | Batasan |
|-----------|------|-----------|---------|
| `flowerNames` | `array of strings` | Array yang berisi nama-nama bunga | Maksimal 10 item |
| `separator` | `string` | String yang merepresentasikan separator yang digunakan antara nama bunga berwarna | String apa saja |

---

## 📤 Return Value

Function mengembalikan sebuah **string** yang merepresentasikan taman bunga berwarna-warni, dengan setiap nama bunga didahului oleh warna yang terkait dan dipisahkan oleh `separator` yang ditentukan.

---

## 💡 Contoh

```javascript
// Input
flowerNames = ["rose", "tulip", "daisy", "sunflower"]
separator = " | "

// Expected Output
"red rose | yellow tulip | pink daisy | blue sunflower"
```

---

## 🔧 Function Signature

```javascript
function flowerGardenComposer(flowerNames, separator) {
    // Implementasi Anda di sini
}
```
