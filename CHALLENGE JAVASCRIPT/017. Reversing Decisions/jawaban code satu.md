# 🧠 Dokumentasi Fungsi reverseDecision

## 📌 Deskripsi

Fungsi `reverseDecision` mensimulasikan tindakan merenungkan keputusan gegabah yang dibuat secara spontan. Fungsi ini menerima sebuah kalimat (string) dan membalik setiap **kata** di dalamnya, tetapi tetap mempertahankan **urutan kata asli**.

---

## 🔧 Deklarasi Fungsi

```javascript
function reverseDecision(decision)
```

---

## 🧩 Kode Lengkap

```javascript
function reverseDecision(decision) {
  const parsedText = decision
    .split(' ')
    .map((e) => {
      const reversedText = e.split('').reverse().join('');
      return reversedText;
    })
    .join(' ');

  return parsedText;
}
```

---

## 🧾 Parameter

| Parameter | Tipe   | Deskripsi                                  |
| --------- | ------ | ------------------------------------------ |
| decision  | String | Kalimat masukan yang berisi beberapa kata. |

---

## 🔄 Cara Kerja

1. Memecah string masukan berdasarkan spasi.
2. Membalik setiap kata satu per satu.
3. Menggabungkan kembali kata-kata yang telah dibalik dengan spasi.

---

## 📤 Nilai Kembali

* **Tipe:** `String`
* **Deskripsi:** String di mana setiap kata dibalik, tetapi urutan kata tetap seperti semula.

---

## 🔡 Contoh Perilaku Karakter

Jika masukan mengandung kata-kata seperti:

| Kata Asli | Kata Setelah Dibalik |
| --------- | -------------------- |
| hello     | olleh                |
| world     | dlrow                |

Kalimat:

```
hello world
```

Akan menjadi:

```
olleh dlrow
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

## 📎 Catatan

* Cocok digunakan untuk transformasi kata dan manipulasi string kreatif.
* Hanya berfungsi pada kata yang dipisahkan oleh spasi. Tanda baca tetap menjadi bagian dari kata.

---

Selamat ngoding! 🚀
