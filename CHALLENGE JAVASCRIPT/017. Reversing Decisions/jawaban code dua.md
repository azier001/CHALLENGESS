# 🧠 Dokumentasi Fungsi reverseDecision

## 📌 Deskripsi

Fungsi `reverseDecision` mensimulasikan momen refleksi, di mana setiap kata dalam sebuah kalimat dibalik seolah-olah sedang memikirkan ulang keputusan masa lalu. Fungsi ini memproses sebuah kalimat (string) dan membalik setiap kata di dalamnya, namun tetap mempertahankan urutan kata asli.

Fungsi ini sangat cocok untuk pemula yang ingin belajar manipulasi string menggunakan `split`, `map`, dan `join` di JavaScript.

---

## 🔧 Deklarasi Fungsi

```javascript
function reverseDecision(decision)
```

---

## 🧩 Kode Lengkap

```javascript
function reverseDecision(decision) {
  return decision.split(' ').map(word => word.split('').reverse().join('')).join(' ');
}
```

---

## 🧾 Parameter

| Parameter | Tipe   | Deskripsi                                 |
| --------- | ------ | ----------------------------------------- |
| decision  | String | Kalimat yang setiap katanya akan dibalik. |

---

## 🔄 Cara Kerja (Langkah demi Langkah)

1. Kalimat dipecah menjadi array kata berdasarkan spasi.
2. Setiap kata dibalik huruf per huruf.
3. Semua kata yang telah dibalik digabung kembali menjadi satu kalimat menggunakan spasi.

---

## 📤 Nilai Kembali

* **Tipe:** `String`
* **Deskripsi:** Kalimat di mana setiap kata dibalik, namun urutan kata tetap seperti semula.

---

## 🔡 Tabel Perilaku Kata

| Kata Asli | Kata Setelah Dibalik |
| --------- | -------------------- |
| hello     | olleh                |
| world     | dlrow                |

Contoh:

```
Input:  "hello world"
Output: "olleh dlrow"
```

---

## 💡 Contoh Penggunaan

```javascript
console.log(reverseDecision("I made a choice"));
```

### ✅ Output

```
I edam a eciohc
```

---

## 🧪 Contoh Lain

| Masukan                | Keluaran               |
| ---------------------- | ---------------------- |
| "Think before you act" | "knihT erofeb uoy tca" |
| "Live and learn"       | "eviL dna nrael"       |
| "Regret nothing"       | "tergeR gnihton"       |

---

## 📎 Catatan untuk Pemula

* Sangat berguna untuk belajar cara kerja string dan array di JavaScript.
* Hanya berfungsi pada kata-kata yang dipisahkan oleh spasi.
* Tanda baca dianggap sebagai bagian dari kata (tidak dipisahkan).

---

Selamat belajar dan semangat ngoding! 🚀
