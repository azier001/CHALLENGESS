# 📦 Dokumentasi Fungsi `checkSupplies`

## 📋 Deskripsi

Fungsi `checkSupplies` adalah fungsi JavaScript yang digunakan untuk **memeriksa ketersediaan suatu item** dalam dua daftar persediaan yang berbeda. Fungsi ini akan menggabungkan kedua daftar tersebut dan mengecek apakah item yang dicari ada di dalam gabungan daftar tersebut.

Fungsi ini sangat berguna ketika Anda memiliki dua atau lebih sumber persediaan dan ingin mengecek apakah suatu barang tersedia di salah satu dari sumber tersebut.

---

## 🔧 Parameter

Fungsi ini menerima **3 parameter**:

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `list1` | Array | Daftar persediaan pertama yang berisi item-item |
| `list2` | Array | Daftar persediaan kedua yang berisi item-item |
| `item` | Any | Item yang ingin dicari/dicek ketersediaannya |

---

## 📤 Return Value

Fungsi ini mengembalikan nilai **boolean**:

- `true` - Jika item **ditemukan** dalam salah satu atau kedua daftar
- `false` - Jika item **tidak ditemukan** dalam kedua daftar

---

## 💻 Kode Fungsi

```javascript
function checkSupplies(list1, list2, item) {
    // Menggabungkan list1 dan list2 menjadi satu array
    const combinedList = list1.concat(list2);
    
    // Mengecek apakah item ada dalam array yang sudah digabungkan
    return combinedList.includes(item);
}
```

---

## 📚 Cara Kerja

1. **Penggabungan**: Fungsi menggunakan metode `concat()` untuk menggabungkan `list1` dan `list2` menjadi satu array baru
2. **Pengecekan**: Menggunakan metode `includes()` untuk memeriksa apakah `item` ada dalam array gabungan
3. **Return**: Mengembalikan hasil `true` atau `false`

---

## 🎯 Contoh Penggunaan

### Contoh 1: Item Ditemukan

```javascript
const gudangA = ['pensil', 'penghapus', 'buku'];
const gudangB = ['penggaris', 'spidol', 'kertas'];

const hasil = checkSupplies(gudangA, gudangB, 'spidol');
console.log(hasil);
```

**Output:**
```
true
```
> Item 'spidol' ditemukan di gudangB

---

### Contoh 2: Item Tidak Ditemukan

```javascript
const gudangA = ['pensil', 'penghapus', 'buku'];
const gudangB = ['penggaris', 'spidol', 'kertas'];

const hasil = checkSupplies(gudangA, gudangB, 'gunting');
console.log(hasil);
```

**Output:**
```
false
```
> Item 'gunting' tidak ditemukan di kedua gudang

---

### Contoh 3: Menggunakan Angka

```javascript
const stokToko1 = [101, 102, 103];
const stokToko2 = [201, 202, 203];

const adaBarang = checkSupplies(stokToko1, stokToko2, 202);
console.log(adaBarang);
```

**Output:**
```
true
```
> Barang dengan kode 202 tersedia di stokToko2

---

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** array asli (`list1` dan `list2`)
- Pengecekan menggunakan **strict equality** (`===`), jadi tipe data harus sama persis
- Fungsi ini **case-sensitive** untuk string (huruf besar/kecil dianggap berbeda)

---

## 🚀 Tips Penggunaan

✅ **Cocok digunakan untuk:**
- Mengecek ketersediaan produk di beberapa gudang
- Validasi item dalam inventory system
- Mencari keberadaan data dalam multiple sources

❌ **Tidak cocok untuk:**
- Array dengan ukuran sangat besar (pertimbangkan Set atau Map)
- Pencarian pattern atau partial match (gunakan regex)

---

## 📝 Lisensi

Fungsi ini bebas digunakan untuk keperluan pembelajaran dan proyek pribadi Anda.

---

**Dibuat dengan ❤️ untuk memudahkan pengecekan persediaan**
