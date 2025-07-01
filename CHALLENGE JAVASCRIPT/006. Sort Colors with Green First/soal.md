# 🎨 Sort Colors with Green First

## 🧩 Challenge Overview

**Level:** 🟢 Easy  
**Goal:** Buat fungsi `sortColors` yang mengurutkan warna **alfabetis**, tapi semua `"green"` (jika ada) harus ditempatkan **di depan**.

---

## ✅ Syarat & Ketentuan

- 🔤 Warna harus diurutkan secara **alfabetis**.
- ✅ Jika ada `"green"`, letakkan **semua** `"green"` di **awal array**.
- 🔁 Jika ada lebih dari satu `"green"`, semuanya tetap harus di depan.
- 🧠 Sorting bersifat **case-sensitive**:
  - `"Green"` dan `"green"` dianggap **berbeda**.
- 🧪 Input hanya berisi string warna valid.

---

## 📌 Contoh Penggunaan

```js
sortColors(["blue", "red", "yellow"]);
// ➞ ["blue", "red", "yellow"]

sortColors(["blue", "green", "red"]);
// ➞ ["green", "blue", "red"]

sortColors(["purple", "orange", "green", "cyan"]);
// ➞ ["green", "cyan", "orange", "purple"]

sortColors(["green", "Green", "green", "blue"]);
// ➞ ["green", "green", "Green", "blue"]
