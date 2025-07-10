# 🌱 Tantangan Format Nama Tanaman

## 📋 Gambaran Umum Challenge

**Tingkat Kesulitan:** `Easy`  
**Nama Function:** `formatPlantName`

Buat sebuah function yang memformat nama tanaman dengan benar dengan cara mengkapitalisasi huruf pertama dari setiap kata sambil membuat semua huruf lainnya menjadi lowercase.

## 🎯 Tujuan

Mengubah nama tanaman dari berbagai format (all lowercase, all uppercase, atau mixed case) menjadi format standar dengan kapitalisasi yang tepat.

## 📝 Spesifikasi Function

### Parameter
- **`plantName`** *(string)*: Nama tanaman yang perlu diformat
  - Bisa dalam bentuk all lowercase, all uppercase, atau mixed case
  - Berisi satu atau lebih kata yang dipisahkan oleh spasi

### Return
- **`string`**: Nama tanaman yang telah diformat dengan kapitalisasi yang tepat

## 🔧 Langkah-langkah Implementasi

Ikuti langkah-langkah berikut untuk menyelesaikan challenge:

1. **Split string** 
   - Gunakan `split()` untuk mengubah string `plantName` menjadi array kata-kata

2. **Proses setiap kata**
   - Loop melalui setiap kata dalam array
   - Terapkan kapitalisasi yang tepat pada setiap kata

3. **Kapitalisasi dengan benar**
   - Gunakan `toUpperCase()` untuk huruf pertama
   - Gunakan `toLowerCase()` untuk huruf-huruf yang tersisa

4. **Rekonstruksi string**
   - Gunakan `join()` dengan spasi sebagai separator untuk menggabungkan kata-kata kembali menjadi satu string

5. **Return hasil**
   - Return nama tanaman yang telah diformat

## 📊 Contoh Penggunaan

```javascript
// Contoh input dan output yang diharapkan
formatPlantName("rose bush") → "Rose Bush"
formatPlantName("SUNFLOWER") → "Sunflower"
formatPlantName("bAmBoO tReE") → "Bamboo Tree"
formatPlantName("african violet") → "African Violet"
```

## 🎨 Perilaku yang Diharapkan

| Input | Output |
|-------|---------|
| `"rose bush"` | `"Rose Bush"` |
| `"SUNFLOWER"` | `"Sunflower"` |
| `"bAmBoO tReE"` | `"Bamboo Tree"` |
| `"african violet"` | `"African Violet"` |

## 💡 Tips

- Ingat untuk menangani nama tanaman satu kata maupun multi-kata
- Pertimbangkan edge case seperti string kosong atau string dengan spasi ekstra
- Test function Anda dengan berbagai format input untuk memastikan berfungsi dengan benar

## 🏆 Kriteria Keberhasilan

Function Anda harus:
- ✅ Mengkapitalisasi huruf pertama dari setiap kata dengan tepat
- ✅ Mengonversi semua huruf lainnya menjadi lowercase
- ✅ Menangani berbagai format input dengan benar
- ✅ Return string yang telah diformat dengan tepat

---

*Selamat coding! 🌿*
