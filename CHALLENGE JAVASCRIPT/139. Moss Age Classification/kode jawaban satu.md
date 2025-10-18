# 🌿 Dokumentasi Fungsi `classifyMoss`

## 📋 Deskripsi

Fungsi `classifyMoss` adalah sebuah fungsi JavaScript yang digunakan untuk mengklasifikasikan lumut (moss) berdasarkan usianya. Fungsi ini menerima input berupa angka yang merepresentasikan umur lumut, kemudian mengembalikan kategori klasifikasi lumut dalam bentuk string.

Fungsi ini sangat berguna untuk aplikasi biologi, game, atau sistem simulasi yang membutuhkan kategorisasi lumut berdasarkan tingkat kedewasaannya.

---

## 🎯 Parameter

| Parameter | Tipe Data | Wajib | Deskripsi |
|-----------|-----------|-------|-----------|
| `mossAge` | `number` | Ya | Umur lumut dalam satuan tahun (bilangan bulat atau desimal) |

---

## 📊 Tabel Klasifikasi Lumut

| Kategori | Rentang Usia | Deskripsi |
|----------|--------------|-----------|
| 🌱 Young Moss | 0 - 5 tahun | Lumut muda yang baru tumbuh |
| 🍃 Mature Moss | 6 - 20 tahun | Lumut dewasa yang sudah berkembang |
| 🌿 Old Moss | 21 - 50 tahun | Lumut tua yang sudah mapan |
| 🏛️ Ancient Moss | 51 - 100 tahun | Lumut purba yang sangat tua |
| 👑 Legendary Moss | > 100 tahun | Lumut legendaris yang berusia sangat lama |

---

## 💻 Kode Fungsi

```javascript
function classifyMoss(mossAge) {
  // Jika umur lumut antara 0-5 tahun
  if (mossAge >= 0 && mossAge <= 5) {
    return "Young Moss";
  } 
  
  // Jika umur lumut antara 6-20 tahun
  else if (mossAge >= 6 && mossAge <= 20) {
    return "Mature Moss";
  } 
  
  // Jika umur lumut antara 21-50 tahun
  else if (mossAge >= 21 && mossAge <= 50) {
    return "Old Moss";
  } 
  
  // Jika umur lumut antara 51-100 tahun
  else if (mossAge >= 51 && mossAge <= 100) {
    return "Ancient Moss";
  } 
  
  // Jika umur lumut lebih dari 100 tahun
  else if (mossAge > 100) {
    return "Legendary Moss";
  }
}
```

---

## 📝 Cara Penggunaan

```javascript
// Contoh 1: Lumut berusia 3 tahun
const result1 = classifyMoss(3);
console.log(result1); 

// Contoh 2: Lumut berusia 15 tahun
const result2 = classifyMoss(15);
console.log(result2);

// Contoh 3: Lumut berusia 75 tahun
const result3 = classifyMoss(75);
console.log(result3);

// Contoh 4: Lumut berusia 150 tahun
const result4 = classifyMoss(150);
console.log(result4);
```

---

## 🎬 Contoh Output

```
Young Moss
Mature Moss
Ancient Moss
Legendary Moss
```

---

## ⚠️ Catatan Penting

1. **Input Negatif**: Fungsi tidak memiliki penanganan khusus untuk nilai negatif. Jika `mossAge` bernilai negatif, fungsi akan mengembalikan `undefined`.

2. **Batas Atas**: Semua nilai di atas 100 akan dikategorikan sebagai "Legendary Moss" tanpa batas maksimum.

3. **Tipe Data**: Fungsi dapat menerima bilangan desimal (misalnya: 5.5 tahun), namun akan dikategorikan sesuai rentang yang ada.

---

## 🔧 Saran Pengembangan

- Tambahkan validasi untuk memastikan input adalah angka
- Tambahkan penanganan untuk nilai negatif atau input yang tidak valid
- Pertimbangkan untuk menambahkan lebih banyak kategori jika diperlukan
- Bisa ditambahkan return value berupa objek yang berisi kategori dan informasi tambahan

---

## 📄 Lisensi

Fungsi ini bersifat open source dan dapat digunakan secara bebas untuk keperluan pembelajaran atau proyek pribadi.

---

**Dibuat dengan** 💚 **untuk para pencinta lumut dan pemrogram pemula**
