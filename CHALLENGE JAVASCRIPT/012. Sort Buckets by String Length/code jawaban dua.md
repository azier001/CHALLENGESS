
# Sort Buckets by String Length

## Deskripsi Tantangan
- Fungsi menerima array string bernama `buckets`.
- Urutkan berdasarkan **panjang string secara ascending**.
- Jika dua string memiliki panjang yang sama, urutan **tetap seperti semula** (ini disebut *stable sort*).
- Kembalikan array yang telah diurutkan.

## Solusi dalam JavaScript

```javascript
function sortBuckets(buckets) {
  return buckets.sort((a, b) => a.length - b.length);
}
```

### Penjelasan
- `.sort((a, b) => a.length - b.length)` mengurutkan array berdasarkan panjang setiap string.
- Karena tidak menggunakan `slice()`, fungsi ini **mengubah array asli secara langsung**.
- Dalam JavaScript modern (sejak ECMAScript 2019), metode `.sort()` adalah **stable sort**, sehingga urutan elemen dengan panjang yang sama tetap dipertahankan di sebagian besar lingkungan JavaScript terbaru.
- Namun, untuk menghindari efek samping pada array asli, biasanya disarankan menambahkan `slice()`.

## Contoh Penggunaan

```javascript
console.log(sortBuckets(["apple", "dog", "banana", "cat"]));
// Output: ["dog", "cat", "apple", "banana"]
```
