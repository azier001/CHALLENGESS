
# Sort Buckets by String Length

## Deskripsi Tantangan
- Fungsi menerima array string bernama `buckets`.
- Urutkan berdasarkan **panjang string secara ascending**.
- Jika dua string memiliki panjang yang sama, urutan **tetap seperti semula** (ini disebut *stable sort*).
- Kembalikan array yang telah diurutkan.

## Solusi dalam JavaScript

```javascript
function sortBuckets(buckets) {
  return buckets.slice().sort((a, b) => a.length - b.length);
}
```

### Penjelasan
- `buckets.slice()` digunakan untuk membuat **salinan array**, agar array asli tidak berubah.
- `.sort((a, b) => a.length - b.length)` mengurutkan berdasarkan panjang string.
- JavaScript’s built-in `.sort()` adalah **stable sort** sejak ECMAScript 2019 (modern JavaScript), jadi urutan asli untuk elemen dengan panjang yang sama akan dipertahankan.

## Contoh Penggunaan

```javascript
console.log(sortBuckets(["apple", "dog", "banana", "cat"]));
// Output: ["dog", "cat", "apple", "banana"]
```
