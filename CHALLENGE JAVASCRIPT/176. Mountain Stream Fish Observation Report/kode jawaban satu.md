# 📚 Dokumentasi Fungsi `fishObservation`

## 🎯 Deskripsi Fungsi

Fungsi `fishObservation` adalah sebuah fungsi yang digunakan untuk membuat laporan observasi ikan di sungai pegunungan. Fungsi ini menggabungkan data ikan yang tidak biasa (unusual fish) dengan data ikan-ikan umum yang biasanya ditemukan di aliran sungai pegunungan, kemudian menghasilkan laporan yang informatif dan mudah dibaca.

---

## 📋 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `unusualFish` | Array (String) | Array berisi nama-nama ikan yang jarang atau tidak biasa ditemukan di lokasi observasi |
| `waterTemp` | Number | Suhu air sungai dalam satuan Celsius (°C) |

---

## 💻 Kode Fungsi

```javascript
function fishObservation(unusualFish, waterTemp) {
  // Array yang berisi nama-nama ikan umum yang biasanya ditemukan di sungai pegunungan
  const commonFish = ["trout", "salmon", "grayling"];
  
  // Menggabungkan array ikan yang tidak biasa dengan array ikan umum
  const allFish = unusualFish.concat(commonFish);
  
  // Membuat laporan observasi dengan format string template
  const report = `Good morning! Today's mountain stream observation:

Water Temperature: ${waterTemp}°C

Observed Fish Species: ${allFish.join(', ')}

Fun Fact: Mountain stream ecosystems are highly sensitive to environmental changes and serve as important indicators of overall watershed health.`;
  
  // Mengembalikan laporan observasi
  return report;
}
```

---

## 🔍 Penjelasan Kode

**Baris 1-2:** Mendefinisikan array `commonFish` yang berisi tiga jenis ikan yang umum ditemukan di sungai pegunungan: trout (ikan pelangi), salmon (ikan salmon), dan grayling (ikan char).

**Baris 3:** Menggunakan method `concat()` untuk menggabungkan array `unusualFish` (parameter dari user) dengan array `commonFish`. Hasilnya disimpan dalam variabel `allFish`.

**Baris 4-8:** Membuat string template (menggunakan backtick `` ` ``) yang berisi laporan observasi. String ini menggunakan interpolasi variabel dengan `${...}` untuk memasukkan nilai suhu air dan daftar ikan. Method `join(', ')` digunakan untuk mengubah array menjadi string dengan pemisah koma dan spasi.

**Baris 9:** Mengembalikan nilai `report` yang sudah dibuat.

---

## 📤 Contoh Penggunaan & Output

### Contoh 1: Observasi dengan 1 ikan tidak biasa
```javascript
const ikanTidakBiasa = ["pike"];
const suhuAir = 12;

const hasil = fishObservation(ikanTidakBiasa, suhuAir);
console.log(hasil);
```

**Output:**
```
Good morning! Today's mountain stream observation:
Water Temperature: 12°C
Observed Fish Species: pike, trout, salmon, grayling
Fun Fact: Mountain stream ecosystems are highly sensitive to environmental changes and serve as important indicators of overall watershed health.
```

---

### Contoh 2: Observasi dengan 3 ikan tidak biasa
```javascript
const ikanTidakBiasa = ["carp", "bass", "catfish"];
const suhuAir = 15;

const hasil = fishObservation(ikanTidakBiasa, suhuAir);
console.log(hasil);
```

**Output:**
```
Good morning! Today's mountain stream observation:
Water Temperature: 15°C
Observed Fish Species: carp, bass, catfish, trout, salmon, grayling
Fun Fact: Mountain stream ecosystems are highly sensitive to environmental changes and serve as important indicators of overall watershed health.
```

---

### Contoh 3: Observasi tanpa ikan tidak biasa
```javascript
const ikanTidakBiasa = [];
const suhuAir = 10;

const hasil = fishObservation(ikanTidakBiasa, suhuAir);
console.log(hasil);
```

**Output:**
```
Good morning! Today's mountain stream observation:
Water Temperature: 10°C
Observed Fish Species: trout, salmon, grayling
Fun Fact: Mountain stream ecosystems are highly sensitive to environmental changes and serve as important indicators of overall watershed health.
```

---

## ⚙️ Cara Kerja Fungsi (Step-by-Step)

1. **Definisi Ikan Umum** → Fungsi dimulai dengan mendaftar 3 jenis ikan umum di array `commonFish`

2. **Penggabungan Data** → Ikan-ikan yang tidak biasa (dari parameter) digabungkan dengan ikan umum menggunakan `.concat()`

3. **Pembuatan Laporan** → String template membentuk laporan dengan format yang rapi dan informatif

4. **Penambahan Informasi** → Suhu air dan daftar ikan dimasukkan ke dalam laporan menggunakan interpolasi string

5. **Pengembalian Hasil** → Laporan yang sudah jadi dikembalikan kepada pemanggil fungsi

---

## 💡 Catatan Penting

- Fungsi ini mengharapkan parameter `unusualFish` berupa **array**. Jika parameter tidak berupa array, akan terjadi error
- Jika array `unusualFish` kosong `[]`, fungsi tetap berjalan normal dan hanya akan menampilkan ikan-ikan umum
- Urutan ikan dalam output adalah: **ikan tidak biasa terlebih dahulu**, kemudian **ikan umum**
- Suhu air (`waterTemp`) dianggap sebagai bilangan yang valid dan akan ditampilkan apa adanya dalam laporan

---

## 🎓 Konsep yang Dipelajari

Melalui fungsi ini, Anda belajar tentang:
- ✅ Penggunaan **array** dan method `.concat()` untuk menggabungkan data
- ✅ Penggunaan **string template** (backtick) untuk membuat string yang kompleks
- ✅ **Interpolasi variabel** menggunakan `${...}` 
- ✅ Method `.join()` untuk mengubah array menjadi string
- ✅ Cara membuat **function yang dapat digunakan kembali** (reusable)
