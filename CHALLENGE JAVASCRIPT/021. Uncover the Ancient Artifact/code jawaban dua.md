# 🏺 Mengungkap Artefak Kuno

## 📜 Deskripsi Tantangan

🔍 Seorang arkeolog telah menemukan artefak misterius yang tertutup dengan inskripsi aneh. Misi kamu adalah mensimulasikan proses hati-hati untuk mengungkap dan menganalisis struktur tersembunyinya menggunakan logika pemrograman.

---

## 🧠 Tujuan

Buatlah sebuah fungsi bernama `uncoverArtifact` yang menerima satu parameter: sebuah string yang merepresentasikan artefak yang acak. Fungsi ini akan memproses string tersebut melalui dua langkah simulasi:

1. **Pembersihan Hati-hati** — Urutkan setengah bagian pertama string secara menaik.
2. **Mengungkap Rahasia** — Balik urutan setengah bagian kedua string.

Akhirnya, fungsi ini akan menggabungkan kedua bagian dan mengembalikannya sebagai versi artefak yang telah diungkap.

---

## 🔧 Instruksi

### Tanda Tangan Fungsi:

```js
function uncoverArtifact(artifact: string): string
```

### Parameter:

| Nama       | Tipe     | Deskripsi                                                     |
| ---------- | -------- | ------------------------------------------------------------- |
| `artifact` | `string` | String berisi huruf dan angka yang mewakili artefak misterius |

### Return:

* `string`: versi artefak yang telah dibersihkan dan terungkap

---

## 📊 Rincian Perilaku

| Langkah    | Operasi                              | Contoh                       |
| ---------- | ------------------------------------ | ---------------------------- |
| 1. Split   | Pisahkan menjadi dua bagian          | "421olleh" → "421" + "olleh" |
| 2. Sort    | Urutkan bagian pertama secara menaik | "421" → "124"                |
| 3. Reverse | Balik bagian kedua                   | "olleh" → "hello"            |
| 4. Join    | Gabungkan hasil akhir                | "124" + "hello" → "124ehllo" |

---

## 🧪 Contoh Penggunaan

```js
uncoverArtifact("421olleh");
// Output: "124ehllo"
```

---

## 💡 Visualisasi Contoh

```txt
String Awal:    "421olleh"
                 └───┬───┘
               Bagian | Bagian
               Pertama| Kedua

Setelah Urut:   "124"
Setelah Balik:  "hello"
Hasil Akhir:    "124ehllo"
```

---

## 🔓 Petunjuk

* Gunakan `slice()` dan `split()` untuk memotong dan memanipulasi bagian string.
* Gunakan `Array.prototype.sort()` untuk mengurutkan.
* Gunakan `Array.prototype.reverse()` untuk membalik.
* Gunakan `Math.floor()` untuk menangani panjang string yang ganjil.

---

## 💻 Kode Alternatif Fungsi

Berikut versi alternatif dari fungsi `uncoverArtifact` yang menggunakan pendekatan manipulasi array lebih eksplisit:

```js
function uncoverArtifact(artifact) {
  const chars = artifact.split('');
  const midpoint = Math.floor(chars.length / 2);

  const firstHalf = chars.slice(0, midpoint).sort();
  const secondHalf = chars.slice(midpoint).reverse();

  return firstHalf.concat(secondHalf).join('');
}
```

---

## 📝 Penjelasan Fungsi Alternatif

1. `split('')`: Mengubah string menjadi array karakter.
2. `Math.floor(chars.length / 2)`: Menentukan indeks tengah array.
3. `slice(0, midpoint)`: Mengambil bagian pertama (depan) array.
4. `.sort()`: Mengurutkan bagian pertama secara alfabetik/angka.
5. `slice(midpoint)`: Mengambil bagian kedua (belakang) array.
6. `.reverse()`: Membalik urutan bagian kedua.
7. `concat(...)`: Menggabungkan dua bagian array.
8. `.join('')`: Mengubah array gabungan kembali menjadi string.

Fungsi ini memiliki hasil yang identik, hanya berbeda dari sisi teknik implementasi. Cocok untuk belajar cara kerja `Array.prototype.concat()`.

---
