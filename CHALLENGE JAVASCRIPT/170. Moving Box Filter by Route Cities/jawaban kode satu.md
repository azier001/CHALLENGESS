# 📦 Dokumentasi Fungsi `filterItemsByRoute`

## 📋 Deskripsi

Fungsi `filterItemsByRoute` digunakan untuk **memfilter item-item dalam beberapa kotak** berdasarkan daftar kota yang diberikan. Fungsi ini akan memeriksa setiap item dan hanya menyimpan item yang mengandung nama kota tertentu.

Bayangkan Anda memiliki beberapa kotak berisi paket kiriman, dan Anda ingin memisahkan paket-paket yang akan dikirim ke kota-kota tertentu saja. Fungsi ini akan membantu Anda melakukan penyaringan tersebut secara otomatis.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `cities` | `Array<string>` | Array berisi nama-nama kota yang akan digunakan sebagai filter |
| `boxes` | `Array<Array<string>>` | Array 2 dimensi yang berisi kotak-kotak, dimana setiap kotak berisi beberapa item (string) |

---

## 📤 Return Value

**Tipe:** `Array<Array<string>>`

Mengembalikan array 2 dimensi dengan struktur yang sama seperti `boxes`, tetapi setiap kotak hanya berisi item-item yang cocok dengan kota yang ada di parameter `cities`.

---

## 💻 Kode Fungsi

```javascript
function filterItemsByRoute(cities, boxes) {
    // Melakukan iterasi pada setiap kotak dalam array boxes
    return boxes.map(box => {
        
        // Memfilter item dalam setiap kotak
        return box.filter(item => {
            
            // Memeriksa apakah item mengandung salah satu nama kota
            // Pencarian dilakukan secara case-insensitive (tidak memperhatikan huruf besar/kecil)
            return cities.some(city => 
                item.toLowerCase().includes(city.toLowerCase())
            );
        });
    });
}
```

---

## 📝 Cara Kerja

1. **Iterasi Kotak**: Fungsi menggunakan `map()` untuk mengiterasi setiap kotak dalam `boxes`
2. **Filter Item**: Untuk setiap kotak, fungsi menggunakan `filter()` untuk menyaring item
3. **Pencocokan Kota**: Menggunakan `some()` untuk memeriksa apakah item mengandung salah satu nama kota
4. **Case-Insensitive**: Pencarian menggunakan `toLowerCase()` sehingga tidak terpengaruh huruf besar/kecil

---

## 🎯 Contoh Penggunaan

### Contoh 1: Filter Paket Berdasarkan Kota

```javascript
// Daftar kota tujuan
const cities = ['Jakarta', 'Bandung', 'Surabaya'];

// Kotak-kotak berisi paket
const boxes = [
    ['Paket ke Jakarta Pusat', 'Paket ke Medan', 'Paket ke Bandung Barat'],
    ['Paket ke Yogyakarta', 'Paket ke Surabaya Timur'],
    ['Paket ke Jakarta Selatan', 'Paket ke Bali']
];

const hasil = filterItemsByRoute(cities, boxes);
console.log(hasil);
```

**Output:**
```javascript
[
    ['Paket ke Jakarta Pusat', 'Paket ke Bandung Barat'],
    ['Paket ke Surabaya Timur'],
    ['Paket ke Jakarta Selatan']
]
```

### Contoh 2: Kotak Kosong Jika Tidak Ada yang Cocok

```javascript
const cities = ['Bali', 'Lombok'];

const boxes = [
    ['Paket ke Jakarta', 'Paket ke Bandung'],
    ['Paket ke Bali Utara', 'Paket ke Lombok Timur'],
    ['Paket ke Medan']
];

const hasil = filterItemsByRoute(cities, boxes);
console.log(hasil);
```

**Output:**
```javascript
[
    [],  // Tidak ada item yang cocok
    ['Paket ke Bali Utara', 'Paket ke Lombok Timur'],
    []   // Tidak ada item yang cocok
]
```

---

## ⚠️ Catatan Penting

- ✅ Pencarian **tidak memperhatikan huruf besar/kecil** (case-insensitive)
- ✅ Jika tidak ada item yang cocok di dalam kotak, akan mengembalikan **array kosong** `[]`
- ✅ Fungsi **tidak mengubah** data asli (immutable)
- ⚠️ Item akan cocok jika **mengandung** nama kota, tidak harus sama persis

---

## 🎓 Untuk Pemula

Analoginya seperti ini:

Bayangkan Anda adalah petugas sorting di kantor pos. Anda punya:
- 📋 **Daftar kota** yang menjadi rute hari ini: Jakarta, Bandung, Surabaya
- 📦 **Beberapa kotak** berisi paket-paket

Tugas Anda adalah:
1. Buka setiap kotak satu per satu
2. Lihat label setiap paket
3. Jika label paket menyebut salah satu kota di daftar rute → **simpan paket itu**
4. Jika tidak → **abaikan paket itu**
5. Susun kembali paket yang lolos ke kotak-kotak baru

Itulah yang dilakukan fungsi ini secara otomatis! 🚀
