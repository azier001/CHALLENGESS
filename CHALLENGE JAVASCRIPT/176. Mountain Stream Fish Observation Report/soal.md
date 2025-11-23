# Laporan Observasi Ikan Mountain Stream

## 📋 Gambaran Umum Challenge

**Tingkat Kesulitan:** Easy

Buat sebuah function yang menggabungkan spesies ikan yang tidak biasa dengan ikan mountain stream yang umum dan menghasilkan laporan observasi yang terformat dengan rapi.

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `fishObservation` yang menerima dua parameter dan menghasilkan laporan observasi komprehensif yang mencakup salam, data temperatur, daftar spesies ikan, dan fakta ekologis.

---

## 📝 Persyaratan Function

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|------------|
| `unusualFish` | Array | Sebuah array berisi string nama spesies ikan yang tidak biasa |
| `waterTemp` | Number | Temperatur air dalam Celsius |

### Return Value

Sebuah **string** yang berisi laporan observasi yang terformat

---

## 🔧 Langkah-Langkah Implementasi

### Langkah 1: Gabungkan Array Ikan
- Gabungkan array `unusualFish` dengan array predefined yang berisi ikan mountain stream yang umum
- Referensi spesies umum: `["trout", "salmon", "grayling"]`

### Langkah 2: Buat String Terformat
Output laporan harus mencakup section-section berikut:

- **Morning Greeting** — Sebuah pesan sambutan untuk memulai laporan
- **Water Temperature** — Tampilkan temperatur air saat ini dalam Celsius
- **Fish Species List** — Semua ikan yang diamati (tidak biasa + umum), digabung dengan koma dan spasi
- **Fun Fact** — Sebuah fakta menarik tentang ekosistem mountain stream

---

## 📌 Catatan Penting

- ✅ Gabungkan semua spesies ikan dengan **koma dan spasi** untuk keterbacaan optimal
- ✅ Pastikan output string terformat dengan baik dan mudah dibaca
- ✅ Sertakan spesies ikan yang tidak biasa dan umum dalam daftar final
- ✅ Presentasikan data dengan cara yang jelas dan terorganisir

---

## 💡 Contoh Penggunaan

```javascript
const unusualSpecies = ["electric eel", "arapaima"];
const temperature = 12;

fishObservation(unusualSpecies, temperature);
```

**Format Output yang Diharapkan:**

```
Good morning! 🌅

Today's Water Temperature: 12°C

Fish Species Observed:
electric eel, arapaima, trout, salmon, grayling

Fun Fact:
Mountain stream ecosystems adalah rumah bagi beberapa spesies ikan yang paling tangguh di Bumi, 
yang beradaptasi dengan air yang dingin dan mengalir deras.
```

---

## 🌊 Konteks

Mountain stream adalah lingkungan akuatik yang pristine yang ditandai dengan air yang dingin, jernih, 
dan mengalir deras. Ekosistem ini mendukung populasi ikan yang beragam mulai dari spesies umum seperti 
trout dan salmon hingga spesies yang lebih tidak biasa ditemukan di kawasan geografis tertentu. 
Laporan observasi Anda akan membantu mendokumentasikan dan merayakan keanekaragaman hayati dari 
lingkungan yang luar biasa ini.

---

## ✨ Kriteria Kesuksesan Challenge

- ✅ Function menerima array `unusualFish` dan number `waterTemp`
- ✅ Array ikan umum digabungkan dengan benar
- ✅ Output mencakup semua section yang diperlukan
- ✅ Spesies ikan dipisahkan dengan koma dan spasi yang tepat
- ✅ Return value adalah sebuah string terformat tunggal
