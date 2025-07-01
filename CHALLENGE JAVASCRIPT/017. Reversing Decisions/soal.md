# 🌀 Membalikkan Keputusan

**Tingkat Kesulitan:** Mudah  
**Kategori:** Manipulasi String  
**Bahasa:** JavaScript

---

## 📚 Ringkasan

Tantangan ini mensimulasikan proses **merenungkan keputusan yang terburu-buru**. Dengan membalik setiap kata dalam kalimat—namun tetap mempertahankan urutan katanya—kita menggambarkan tindakan introspeksi untuk melihat kembali dan mempertimbangkan ulang pilihan yang telah diambil.

---

## 🎯 Tujuan

Buatlah fungsi bernama `reverseDecision` yang memproses sebuah kalimat (`decision`) dengan membalik setiap kata satu per satu **tanpa mengubah urutan kata-katanya**.

---

## 📥 Parameter

| Parameter | Tipe   | Deskripsi                                                                 |
|-----------|--------|---------------------------------------------------------------------------|
| decision  | string | Kalimat yang hanya terdiri dari huruf alfabet dan spasi. Tidak ada tanda baca, tidak ada spasi berlebih. |

---

## 📤 Keluaran

Mengembalikan sebuah **string** di mana **setiap kata dibalik**, tetapi **urutan kata tetap seperti semula**.

---

## 🔍 Contoh

```js
reverseDecision("Think before you act");
```

➡️ Output:
```
"knihT erofeb uoy tca"
```

---

## 🔧 Langkah-langkah

1. Pisahkan string `decision` menjadi kata-kata individual.
2. Balikkan karakter dalam setiap kata.
3. Gabungkan kata-kata yang sudah dibalik dengan spasi.
4. Kembalikan string hasil akhir.

---

## 🧠 Batasan

- String input hanya mengandung:
  - Huruf alfabet (`a-z`, `A-Z`)
  - Spasi tunggal antar kata
- Tidak mengandung tanda baca
- Tidak ada spasi ganda, spasi awal atau akhir

---

## 💡 Petunjuk

- Gunakan `.split(" ")` untuk memisahkan kata.
- Gunakan `.split("").reverse().join("")` untuk membalik sebuah kata.
- Gabungkan semuanya dengan `.join(" ")`.

---





## ✅ Contoh Uji

| Input                         | Output                        |
|------------------------------|-------------------------------|
| `"Think before you act"`     | `"knihT erofeb uoy tca"`      |
| `"Regret nothing"`           | `"tergeR gnihton"`            |
| `"Live and learn"`           | `"eviL dna nrael"`            |
| `"Just do it"`               | `"tsuJ od ti"`                |
| `"Seize the day"`            | `"ezeiS eht yad"`             |

---

## 🏁 Kesimpulan

Tantangan ini membantu memperkuat pemahaman tentang **manipulasi string**, khususnya penggunaan metode array seperti `.split()`, `.map()`, `.reverse()`, dan `.join()`—alat yang sering digunakan dalam tugas pemrograman sehari-hari. ✨

Selamat ngoding! 🚀
