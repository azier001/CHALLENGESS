
# 🪣 Sort Buckets by String Length

## 🎯 Challenge Overview
**Difficulty**: 🟢 Easy

## 📚 Deskripsi
Buatlah sebuah fungsi bernama `sortBuckets` yang menerima sebuah array string bernama `buckets`.

Fungsi ini akan mengurutkan array berdasarkan:
- 🔢 **Panjang setiap string** (dari yang terpendek ke terpanjang).
- 📌 **Menjaga urutan asli** untuk string dengan panjang yang sama (*stable sort*).

Fungsi harus mengembalikan array `buckets` yang sudah terurut.

---

## ✅ Contoh
Jika diberikan input:

```javascript
["apple", "dog", "banana", "cat"]
```

Maka output yang diharapkan:

```javascript
["dog", "cat", "apple", "banana"]
```

---

## 🛠️ Tips
- Gunakan fungsi bawaan seperti `.sort()` untuk membantu proses pengurutan.
- Jika ingin menjaga array asli tetap utuh, pertimbangkan untuk membuat salinan dengan `.slice()`.

Semangat mengerjakan! 🚀
