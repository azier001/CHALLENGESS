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

## 💻 Kode Lengkap Fungsi

```js
function uncoverArtifact(artifact) {
  const mid = Math.floor(artifact.length / 2);
  const firstHalf = artifact.slice(0, mid).split('').sort().join('');
  const secondHalf = artifact.slice(mid).split('').reverse().join('');
  return firstHalf + secondHalf;
}
```

---

## 📝 Penjelasan Fungsi

Fungsi `uncoverArtifact` digunakan untuk mensimulasikan proses pengungkapan artefak kuno dari string acak. Berikut adalah penjelasan langkah demi langkah yang mudah dipahami:

1. `Math.floor(artifact.length / 2)`: menghitung posisi tengah dari string. Jika panjang string ganjil, bagian pertama akan lebih pendek.
2. `slice(0, mid)`: mengambil bagian pertama string.
3. `.split('').sort().join('')`: mengubah bagian pertama menjadi array karakter, mengurutkannya, lalu menggabungkan kembali menjadi string.
4. `slice(mid)`: mengambil bagian kedua string.
5. `.split('').reverse().join('')`: membalik urutan bagian kedua string.
6. `return firstHalf + secondHalf`: menggabungkan hasil bagian pertama dan kedua lalu dikembalikan sebagai output.

---
