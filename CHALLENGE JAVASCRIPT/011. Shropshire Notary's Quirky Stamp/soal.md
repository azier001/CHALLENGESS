# 🕵️‍♂️ Shropshire Notary's Quirky Stamp (Cap Unik Notaris Shropshire)

## 💼 Ringkasan Tantangan

**Tingkat Kesulitan:** Mudah

Selamat datang di dunia penuh keunikan notaris Shropshire! Notaris ini memiliki kebiasaan aneh: capnya membalik teks yang dicap dan mengelilinginya dengan bingkai bintang (`*`).

Misi Anda adalah mereplikasi cap unik ini melalui kode.

---

## 🧠 Deskripsi Tugas

Buatlah fungsi bernama `notaryStampReverse` yang mensimulasikan proses pencapan.

### Tanda Tangan Fungsi

```javascript
function notaryStampReverse(textArray, borderWidth)
```

### Parameter

- `textArray` (`array`):  
  Sebuah array 2 dimensi berisi string yang merupakan teks asli yang akan dicap.  
  Setiap array dalamnya berisi string yang akan **dibalik** dan **dikonkat**.

- `borderWidth` (`number`):  
  Bilangan bulat positif yang merepresentasikan **lebar bingkai** (dari karakter `*`) yang mengelilingi teks cap.

---

## 📝 Persyaratan

1. 🔄 **Balikkan** setiap string dalam array 2 dimensi.
2. 🔗 **Gabungkan** string terbalik dalam setiap baris dengan **spasi tunggal**.
3. ✨ **Tambahkan bingkai** dari karakter `*` mengelilingi teks, sesuai `borderWidth` yang diberikan.
4. 🧾 **Kembalikan** hasil akhir sebagai **satu string**, termasuk baris-baris dan bingkai.

---

## 🧪 Contoh

### Input

```javascript
notaryStampReverse(
  [
    ["Hello", "World"],
    ["Shropshire", "Notary"]
  ],
  2
);
```

### Proses

1. Membalikkan setiap string:
   ```
   ["olleH", "dlroW"]
   ["erihsporhS", "yratoN"]
   ```

2. Menggabungkan dengan spasi:
   ```
   "olleH dlroW"
   "erihsporhS yratoN"
   ```

3. Menghitung lebar akhir:
   - Baris terpanjang: `"erihsporhS yratoN"` → 18 karakter
   - Total lebar: 18 (teks) + 2×borderWidth = 22

4. Menerapkan bingkai dengan lebar 2:
   ```
   **********************
   **********************
   **olleH dlroW       **
   **erihsporhS yratoN **
   **********************
   **********************
   ```

### Output

```plaintext
**********************
**********************
**olleH dlroW       **
**erihsporhS yratoN **
**********************
**********************
```

---

## ✅ Catatan Tambahan

- Pastikan semua baris **dipenuhi ke panjang yang sama** sebelum ditambahkan bingkai.
- **Bagian atas dan bawah** bingkai harus berupa baris karakter `*` sebanyak `borderWidth`.
- **Kiri dan kanan** masing-masing diberi `borderWidth` karakter `*`.

---

Selamat ngoding dan semoga cap Anda selalu penuh gaya! 🖋️
