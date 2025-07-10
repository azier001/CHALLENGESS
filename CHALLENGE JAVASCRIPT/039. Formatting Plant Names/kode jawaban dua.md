# 🌱 Dokumentasi Fungsi `formatPlantName`

## 📝 Deskripsi Fungsi

Fungsi `formatPlantName` digunakan untuk memformat nama tanaman agar setiap kata dimulai dengan huruf kapital (Title Case). Fungsi ini sangat berguna untuk menyeragamkan penulisan nama tanaman dalam aplikasi atau database.

## 🎯 Tujuan Penggunaan

- Menyeragamkan format penulisan nama tanaman
- Membuat tampilan nama tanaman lebih profesional
- Menghindari inkonsistensi dalam penulisan nama

## 📋 Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|--------|
| `plantName` | String | Nama tanaman yang ingin diformat | `"mawar merah"` |

## 🔧 Cara Kerja

1. **Pemisahan Kata**: Memisahkan nama tanaman menjadi array kata-kata
2. **Format Setiap Kata**: Mengubah huruf pertama menjadi kapital dan sisanya menjadi huruf kecil
3. **Penggabungan**: Menggabungkan kembali kata-kata yang sudah diformat

## 💻 Kode Fungsi

```javascript
function formatPlantName(plantName) {
    // Pisahkan nama tanaman menjadi array kata-kata
    const words = plantName.split(' ');
    
    // Loop melalui setiap kata dan format
    const formattedWords = words.map(word => {
        // Ubah huruf pertama menjadi kapital dan sisanya menjadi huruf kecil
        return word.charAt(0).toUpperCase() + word.slice(1).toLowerCase();
    });
    
    // Gabungkan kembali kata-kata menjadi satu string
    return formattedWords.join(' ');
}
```

## 🎨 Contoh Penggunaan

### Input dan Output

| Input | Output |
|-------|--------|
| `"mawar merah"` | `"Mawar Merah"` |
| `"BUNGA MATAHARI"` | `"Bunga Matahari"` |
| `"anggrek bULaN"` | `"Anggrek Bulan"` |
| `"kaktus mini"` | `"Kaktus Mini"` |

### Contoh Implementasi

```javascript
// Contoh 1: Nama tanaman dengan huruf kecil
const plant1 = "mawar merah";
console.log(formatPlantName(plant1)); 
// Output: "Mawar Merah"

// Contoh 2: Nama tanaman dengan huruf kapital semua
const plant2 = "BUNGA MATAHARI";
console.log(formatPlantName(plant2)); 
// Output: "Bunga Matahari"

// Contoh 3: Nama tanaman dengan format campuran
const plant3 = "anggrek bULaN";
console.log(formatPlantName(plant3)); 
// Output: "Anggrek Bulan"
```

## 📊 Tabel Karakter yang Diproses

| Karakter | Sebelum | Sesudah | Keterangan |
|----------|---------|---------|------------|
| Huruf pertama kata | `m` | `M` | Diubah menjadi kapital |
| Huruf kedua dst | `AWAR` | `awar` | Diubah menjadi huruf kecil |
| Spasi | ` ` | ` ` | Tetap dipertahankan |

## ✅ Kelebihan

- **Sederhana**: Mudah dipahami dan digunakan
- **Konsisten**: Menghasilkan format yang seragam
- **Fleksibel**: Dapat menangani berbagai format input
- **Efisien**: Menggunakan built-in method JavaScript

## ⚠️ Catatan Penting

- Fungsi ini hanya memproses spasi sebagai pemisah kata
- Input harus berupa string yang valid
- Tidak menangani karakter khusus sebagai pemisah (seperti tanda hubung)

## 🚀 Tips Penggunaan

1. **Validasi Input**: Pastikan input adalah string sebelum menggunakan fungsi
2. **Handling Error**: Tambahkan pengecekan untuk input kosong atau null
3. **Ekstensibilitas**: Dapat diperluas untuk menangani pemisah lain selain spasi

## 🎯 Return Value

**Tipe**: `String`  
**Deskripsi**: Nama tanaman yang sudah diformat dengan setiap kata diawali huruf kapital

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja dan penggunaan fungsi `formatPlantName` dalam proyek JavaScript.*
