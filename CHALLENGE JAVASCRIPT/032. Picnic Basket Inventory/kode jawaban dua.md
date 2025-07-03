# 🧺 Dokumentasi Fungsi `preparePicnicBasket`

## 📋 Deskripsi Fungsi

Fungsi `preparePicnicBasket` adalah sebuah utilitas sederhana yang digunakan untuk menambahkan item-item baru ke dalam keranjang piknik yang sudah ada. Fungsi ini mengambil daftar item yang sudah ada dan menambahkan sejumlah item baru dengan format yang konsisten.

## 🎯 Tujuan Penggunaan

- Mempermudah penambahan item ke dalam daftar keranjang piknik
- Memberikan format yang konsisten untuk item-item baru
- Menghemat waktu dalam pembuatan daftar belanja atau persiapan piknik

## 📝 Sintaks

```javascript
preparePicnicBasket(currentItems, itemsToAdd)
```

## 🔧 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|-------|
| `currentItems` | String | Daftar item yang sudah ada dalam keranjang (format string) | ✅ Ya |
| `itemsToAdd` | Number | Jumlah item baru yang ingin ditambahkan | ✅ Ya |

### 📌 Penjelasan Parameter

- **`currentItems`**: Merupakan string yang berisi daftar item yang sudah ada. Bisa berupa string kosong atau daftar item yang dipisahkan koma.
- **`itemsToAdd`**: Angka yang menunjukkan berapa banyak item baru yang akan ditambahkan. Item baru akan diberi nama `item1`, `item2`, dst.

## 🔄 Nilai Kembalian

Fungsi ini mengembalikan sebuah **string** yang berisi gabungan dari item yang sudah ada dan item-item baru yang ditambahkan.

## 📊 Tabel Karakter Khusus

| Karakter | Fungsi | Lokasi Penggunaan |
|----------|---------|-------------------|
| `,` | Pemisah antar item | Antara setiap item dalam daftar |
| ` ` | Spasi | Setelah setiap koma untuk keterbacaan |

## 💻 Kode Sumber

```javascript
function preparePicnicBasket(currentItems, itemsToAdd) {
    let result = currentItems;
    
    for (let i = 1; i <= itemsToAdd; i++) {
        result += `, item${i}`;
    }
    
    return result;
}
```

## 🎨 Contoh Penggunaan

### Contoh 1: Menambahkan item ke keranjang kosong
```javascript
const basket = preparePicnicBasket("", 3);
console.log(basket);
```
**Output:** `, item1, item2, item3`

### Contoh 2: Menambahkan item ke keranjang yang sudah ada
```javascript
const basket = preparePicnicBasket("roti, keju", 2);
console.log(basket);
```
**Output:** `roti, keju, item1, item2`

### Contoh 3: Menambahkan banyak item
```javascript
const basket = preparePicnicBasket("sandwich, jus apel", 5);
console.log(basket);
```
**Output:** `sandwich, jus apel, item1, item2, item3, item4, item5`

## 🧐 Cara Kerja Detail

1. **Inisialisasi**: Fungsi menyimpan nilai `currentItems` ke dalam variabel `result`
2. **Looping**: Menggunakan loop `for` dari 1 hingga `itemsToAdd`
3. **Penambahan**: Setiap iterasi menambahkan string `, item${i}` ke `result`
4. **Pengembalian**: Mengembalikan string final yang sudah digabungkan

## ⚠️ Catatan Penting

- Jika `currentItems` kosong, hasil akan dimulai dengan koma
- Item baru selalu diberi nama dengan format `item` + nomor urut
- Fungsi tidak melakukan validasi input, pastikan parameter yang diberikan benar

## 🔍 Tips Penggunaan

- Gunakan string kosong `""` untuk `currentItems` jika memulai dari keranjang kosong
- Pastikan `itemsToAdd` adalah angka positif
- Untuk menghindari koma di awal, cek terlebih dahulu apakah `currentItems` kosong

## 🎯 Pengembangan Lebih Lanjut

Fungsi ini dapat dikembangkan dengan menambahkan:
- Validasi input parameter
- Opsi untuk mengubah format nama item
- Kemampuan untuk menambahkan item dengan nama khusus
- Fungsi untuk menghapus item dari keranjang

---

*Dokumentasi ini dibuat untuk membantu pemula memahami fungsi `preparePicnicBasket` dengan mudah dan lengkap.*
