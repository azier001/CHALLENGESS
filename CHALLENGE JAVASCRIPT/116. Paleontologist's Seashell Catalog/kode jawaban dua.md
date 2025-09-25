# 🐚 Dokumentasi Fungsi processSeashells

## 📋 Deskripsi Fungsi

Fungsi `processSeashells` adalah sebuah fungsi JavaScript yang memproses array kerang laut (seashells) dengan cara membalik urutan elemen dalam array, menggabungkannya dengan tanda hubung (`-`), dan menambahkan kata kunci (keyword) di akhir dengan pemisah garis bawah (`_`).

## 🔧 Kode Fungsi

```javascript
function processSeashells(seashells, keyword) {
    // Membalik urutan array, menggabungkan dengan tanda hubung,
    // dan menambahkan keyword dengan pemisah underscore
    return seashells.reverse().join('-') + '_' + keyword;
}
```

## 📝 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `seashells` | Array | ✅ Ya | Array yang berisi elemen-elemen kerang laut atau data lainnya yang akan diproses |
| `keyword` | String | ✅ Ya | Kata kunci yang akan ditambahkan di akhir hasil pemrosesan |

## ⚙️ Cara Kerja

1. **Membalik Array**: Fungsi akan membalik urutan elemen dalam array `seashells` menggunakan method `.reverse()`
2. **Menggabungkan**: Semua elemen yang sudah dibalik akan digabungkan menjadi satu string dengan pemisah tanda hubung (`-`) menggunakan method `.join('-')`
3. **Menambah Keyword**: Kata kunci (`keyword`) akan ditambahkan di akhir dengan pemisah garis bawah (`_`)

## 🎯 Contoh Penggunaan

### Contoh 1: Array String
```javascript
const kerangLaut = ['karang', 'siput', 'keong', 'tiram'];
const hasil = processSeashells(kerangLaut, 'pantai');

console.log(hasil);
// Output: "tiram-keong-siput-karang_pantai"
```

### Contoh 2: Array Angka
```javascript
const nomorKerang = [1, 2, 3, 4, 5];
const hasil = processSeashells(nomorKerang, 'laut');

console.log(hasil);
// Output: "5-4-3-2-1_laut"
```

### Contoh 3: Array Campuran
```javascript
const dataCampur = ['A', 'B', 'C'];
const hasil = processSeashells(dataCampur, 'koleksi');

console.log(hasil);
// Output: "C-B-A_koleksi"
```

## 📊 Tabel Contoh Input dan Output

| Input Array | Input Keyword | Output |
|-------------|---------------|--------|
| `['a', 'b', 'c']` | `'test'` | `'c-b-a_test'` |
| `[1, 2, 3]` | `'angka'` | `'3-2-1_angka'` |
| `['merah', 'biru']` | `'warna'` | `'biru-merah_warna'` |

## ⚠️ Catatan Penting

- **Perubahan Array Asli**: Method `.reverse()` akan mengubah array asli. Jika Anda tidak ingin array asli berubah, buat salinan terlebih dahulu menggunakan `[...seashells].reverse()`
- **Tipe Data**: Semua elemen dalam array akan dikonversi menjadi string saat menggunakan `.join()`
- **Array Kosong**: Jika array kosong, hasilnya akan berupa `'_' + keyword`

## 🔄 Versi yang Tidak Mengubah Array Asli

Jika Anda ingin array asli tetap tidak berubah:

```javascript
function processSeashellsSafe(seashells, keyword) {
    // Membuat salinan array terlebih dahulu agar array asli tidak berubah
    return [...seashells].reverse().join('-') + '_' + keyword;
}
```

## 🎨 Tips Penggunaan

- Gunakan untuk memformat data yang perlu diurutkan terbalik
- Cocok untuk membuat identifier unik dengan format tertentu
- Berguna untuk preprocessing data sebelum dikirim ke API atau disimpan ke database

---

*Dokumentasi ini dibuat untuk membantu pemula memahami fungsi processSeashells dengan mudah* 🌊
