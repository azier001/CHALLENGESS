# 🃏 Arrange Card Numbers

Fungsi `arrangeCardNumbers` digunakan untuk **menyusun ulang angka-angka kartu** dengan cara memisahkan antara angka genap dan ganjil, lalu mengurutkannya sesuai aturan tertentu.

---

## 🧠 Penjelasan Umum

### 📥 Parameter Fungsi

| Parameter | Tipe       | Deskripsi                                                      |
| --------- | ---------- | -------------------------------------------------------------- |
| `numbers` | `number[]` | Array angka yang akan diurutkan berdasarkan sifat genap/ganjil |

### 📤 Return Value

* Fungsi akan mengembalikan array baru yang terdiri dari:

  * Angka **genap**, diurutkan dari **kecil ke besar**
  * Diikuti angka **ganjil**, diurutkan dari **besar ke kecil**

### 🔣 Karakteristik Penyusunan

| Jenis Angka | Urutan             | Posisi di Output    |
| ----------- | ------------------ | ------------------- |
| Genap       | Naik (Ascending)   | Di awal array       |
| Ganjil      | Turun (Descending) | Setelah angka genap |

> ♠️ Cocok digunakan untuk permainan kartu, pemrosesan data numerik, atau latihan logika pemisahan data.

---

## 🧩 Kode Fungsi

```javascript
function arrangeCardNumbers(numbers) {
  const evens = numbers.filter(num => num % 2 === 0).sort((a, b) => a - b);
  const odds = numbers.filter(num => num % 2 !== 0).sort((a, b) => b - a);
  return [...evens, ...odds];
}
```

---

## ✅ Contoh Penggunaan (Test Cases)

### `arrangeCardNumbers([5, 3, 2, 8, 1, 4])`

```
[2, 4, 8, 5, 3, 1]
```

**Penjelasan:**

* Angka genap: `[2, 4, 8]` → urut naik
* Angka ganjil: `[5, 3, 1]` → urut turun
* Gabungan hasil akhir: `[2, 4, 8, 5, 3, 1]`

### `arrangeCardNumbers([9, 12, 4, 7, 2])`

```
[2, 4, 12, 9, 7]
```

---

## 📌 Catatan Akhir

* Fungsi tidak mengubah array asli (non-mutation)
* Merupakan contoh penggunaan kombinasi metode array seperti:

  * `filter()` → menyaring elemen
  * `sort()` → mengurutkan
  * Spread operator `...` → menggabungkan array

> 🧮 Dokumentasi ini siap digunakan untuk pembelajaran, proyek pribadi, atau latihan pemrograman dasar dengan JavaScript!
