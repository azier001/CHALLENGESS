# 🍫 Chocolate Shop Tasting Experience

> Simulasikan perjalanan menyenangkan pelanggan saat mencicipi berbagai rasa cokelat, dimulai dari rasa favorit mereka!

---

## 📌 Ringkasan Tantangan

**Tingkat Kesulitan**: 🟢 Mudah

Buatlah fungsi bernama `chocolateTasting` yang mensimulasikan pengalaman mencicipi di sebuah toko cokelat.

---

## 🧠 Logika yang Harus Diimplementasikan

1. 🔍 **Cari indeks** dari rasa cokelat favorit pelanggan dalam array `flavors`.
2. 🍽️ **Buat array baru** yang mencakup semua rasa mulai dari rasa favorit.
3. 🚫 Jika rasa favorit **tidak ditemukan** atau berada di **akhir array**, gunakan **seluruh rasa**.
4. 🔗 **Gabungkan** semua rasa dalam array baru dengan pemisah `' dan '`.
5. 💬 **Kembalikan pesan** yang mendeskripsikan pengalaman mencicipi pelanggan.

---

## 🧾 Tanda Tangan Fungsi

```javascript
function chocolateTasting(flavors: string[], favorite: string): string
```

---

## 📥 Parameter

| Nama       | Tipe     | Deskripsi                                                        |
|------------|----------|------------------------------------------------------------------|
| `flavors`  | `array`  | Array string yang merepresentasikan berbagai rasa cokelat        |
| `favorite` | `string` | String rasa cokelat favorit pelanggan                            |

---

## 📤 Keluaran

- Sebuah `string` yang menjelaskan pengalaman mencicipi pelanggan.

---

## 💡 Contoh

```javascript
const flavors = ['hazelnut', 'caramel', 'mint', 'dark', 'milk'];
const favorite = 'mint';

console.log(chocolateTasting(flavors, favorite));
// Output:
// "Rasa favorit pelanggan adalah mint. Mereka mencicipi: mint dan dark dan milk"
```

---

## ✅ Format Output yang Diharapkan

```
"Rasa favorit pelanggan adalah <favorite>. Mereka mencicipi: <flavor1> dan <flavor2> dan ..."
```

Selamat ngoding dan selamat mencicipi cokelat! 🍬
