# 📋 Dokumentasi Fungsi `organizeFairSchedule`

## 📝 Deskripsi

Fungsi `organizeFairSchedule` digunakan untuk mengatur jadwal acara festival atau pameran. Fungsi ini mengelola jumlah keranjang dan tekstil yang akan dipamerkan, serta menggabungkan jadwal penampilan musisi dan lonceng menara menjadi satu jadwal terpadu.

---

## 🔧 Sintaks

```javascript
organizeFairSchedule(basketCount, textileCount, musicianSlots, belfryChimes)
```

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `basketCount` | `Number` | Jumlah keranjang yang akan dipamerkan |
| `textileCount` | `Number` | Jumlah tekstil/kain yang akan dipamerkan |
| `musicianSlots` | `Array` | Array yang berisi jadwal slot penampilan musisi |
| `belfryChimes` | `Array` | Array yang berisi jadwal bunyi lonceng menara |

---

## 📤 Return Value

Fungsi ini mengembalikan sebuah **objek** dengan struktur sebagai berikut:

| Property | Tipe | Deskripsi |
|----------|------|-----------|
| `baskets` | `Number` | Jumlah keranjang + 1 (mungkin termasuk keranjang tambahan untuk cadangan) |
| `textiles` | `Number` | Jumlah tekstil + 1 (mungkin termasuk tekstil tambahan untuk cadangan) |
| `schedule` | `Array` | Gabungan array dari jadwal musisi dan lonceng menara |

---

## 💻 Kode Fungsi

```javascript
function organizeFairSchedule(basketCount, textileCount, musicianSlots, belfryChimes) {
  
  return {
    // Menambahkan 1 keranjang ekstra (mungkin untuk cadangan atau display khusus)
    baskets: basketCount + 1,
    
    // Menambahkan 1 tekstil ekstra (mungkin untuk cadangan atau display khusus)
    textiles: textileCount + 1,
    
    // Menggabungkan array jadwal musisi dan lonceng menjadi satu jadwal lengkap
    schedule: [...musicianSlots, ...belfryChimes]
  };
  
}
```

---

## 🎯 Contoh Penggunaan

### Contoh 1: Festival Sederhana

```javascript
const result = organizeFairSchedule(
  5,                              // 5 keranjang
  3,                              // 3 tekstil
  ["Band A - 10:00", "Band B - 14:00"],  // 2 slot musisi
  ["Lonceng - 12:00", "Lonceng - 18:00"] // 2 jadwal lonceng
);

console.log(result);
```

**Output:**
```javascript
{
  baskets: 6,
  textiles: 4,
  schedule: [
    "Band A - 10:00",
    "Band B - 14:00",
    "Lonceng - 12:00",
    "Lonceng - 18:00"
  ]
}
```

### Contoh 2: Pameran Besar

```javascript
const result = organizeFairSchedule(
  10,                             // 10 keranjang
  8,                              // 8 tekstil
  ["Orkestra - 09:00", "Jazz - 15:00", "Tradisional - 19:00"],
  ["Lonceng Pagi - 08:00", "Lonceng Sore - 17:00"]
);

console.log(result);
```

**Output:**
```javascript
{
  baskets: 11,
  textiles: 9,
  schedule: [
    "Orkestra - 09:00",
    "Jazz - 15:00",
    "Tradisional - 19:00",
    "Lonceng Pagi - 08:00",
    "Lonceng Sore - 17:00"
  ]
}
```

---

## 📚 Penjelasan Detail

### Mengapa `+1` pada baskets dan textiles?

Fungsi ini menambahkan 1 item ekstra pada keranjang dan tekstil. Ini bisa berguna untuk:
- 🛡️ **Cadangan**: Jika ada yang rusak atau hilang
- 🎨 **Display khusus**: Item tambahan untuk display promosi
- 📦 **Stok tambahan**: Untuk keperluan darurat

### Bagaimana cara kerja penggabungan jadwal?

Operator spread (`...`) digunakan untuk menggabungkan dua array:
1. `...musicianSlots` - Menyebarkan semua elemen dari jadwal musisi
2. `...belfryChimes` - Menyebarkan semua elemen dari jadwal lonceng
3. Hasilnya adalah satu array baru yang berisi semua jadwal secara berurutan

---

## ⚠️ Catatan Penting

- Pastikan `musicianSlots` dan `belfryChimes` adalah **array** yang valid
- Fungsi tidak melakukan validasi input, jadi pastikan parameter yang diberikan sesuai tipe data
- Urutan jadwal akan mengikuti urutan: **musisi dulu**, kemudian **lonceng**

---

## 🚀 Tips Penggunaan

1. **Untuk jadwal yang terurut waktu**: Urutkan array `musicianSlots` dan `belfryChimes` sebelum memanggil fungsi
2. **Untuk data kosong**: Gunakan array kosong `[]` jika tidak ada jadwal musisi atau lonceng
3. **Untuk format data konsisten**: Gunakan format string yang sama untuk semua jadwal (contoh: "Nama - Waktu")

---

## 📖 Lisensi

Fungsi ini bebas digunakan untuk keperluan pribadi maupun komersial.

---

**Dibuat dengan ❤️ untuk mempermudah pengelolaan jadwal festival**
