# 🍲 Sukiyaki Dinner Preparation Challenge

## Tingkat Kesulitan
**Easy** 🟢

---

## 📋 Deskripsi Challenge

Buat sebuah function bernama `prepareSukiyaki` yang menerima `meats` dan `vegetables` sebagai parameter.

Function ini menggabungkan ingredients dari kedua array menjadi satu array, **bergantian antara satu meat dan satu vegetable**, dimulai dengan meat.

---

## 🎯 Function Signature

```javascript
prepareSukiyaki(meats, vegetables)
```

---

## 📥 Parameters

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `meats` | `array of strings` | Daging iris untuk sukiyaki |
| `vegetables` | `array of strings` | Sayuran untuk sukiyaki |

---

## 📤 Return Value

Mengembalikan sebuah **array of strings** yang merepresentasikan urutan ingredients yang ditambahkan ke dalam panci.

---

## 💡 Persyaratan Utama

- ✅ Bergantian antara meat dan vegetable
- ✅ Mulai dengan meat terlebih dahulu
- ✅ Gabungkan kedua array menjadi satu hasil

---

## 📝 Contoh

```javascript
const meats = ["beef", "pork", "chicken"];
const vegetables = ["tofu", "mushroom", "cabbage"];

prepareSukiyaki(meats, vegetables);
// Expected output: ["beef", "tofu", "pork", "mushroom", "chicken", "cabbage"]
```

---

## 🧠 Petunjuk

- Pikirkan bagaimana cara melakukan iterasi melalui kedua array secara bersamaan
- Pertimbangkan apa yang terjadi ketika satu array lebih panjang dari yang lain
- Polanya harus: meat → vegetable → meat → vegetable...

---

## 🎉 Selamat mengerjakan sukiyaki preparation challenge Anda!
