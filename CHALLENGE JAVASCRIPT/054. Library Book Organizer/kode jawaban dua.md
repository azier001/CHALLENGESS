# 📚 Dokumentasi Fungsi `organizeLibrary`

## 📝 Deskripsi

Fungsi `organizeLibrary` adalah sebuah fungsi JavaScript yang digunakan untuk mengorganisir dan memformat koleksi buku sains dan filsafat. Fungsi ini akan menggabungkan kedua jenis buku tersebut ke dalam satu array dengan format judul yang konsisten (huruf pertama kapital, sisanya huruf kecil).

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `scienceBooks` | Array | Array yang berisi judul-judul buku sains dalam bentuk string |
| `philosophyBooks` | Array | Array yang berisi judul-judul buku filsafat dalam bentuk string |

## 🔄 Return Value

**Tipe:** `Array`

**Deskripsi:** Mengembalikan array baru yang berisi semua judul buku (sains dan filsafat) dengan format yang telah distandarisasi.

## 💻 Kode Fungsi

```javascript
function organizeLibrary(scienceBooks, philosophyBooks) {
    let result = [];
    
    // Menambahkan buku-buku sains dengan format yang telah distandarisasi
    for (let i = 0; i < scienceBooks.length; i++) {
        let formattedTitle = scienceBooks[i].charAt(0).toUpperCase() + 
                           scienceBooks[i].slice(1).toLowerCase();
        result.push(formattedTitle);
    }
    
    // Menambahkan buku-buku filsafat dengan format yang telah distandarisasi
    for (let i = 0; i < philosophyBooks.length; i++) {
        let formattedTitle = philosophyBooks[i].charAt(0).toUpperCase() + 
                           philosophyBooks[i].slice(1).toLowerCase();
        result.push(formattedTitle);
    }
    
    return result;
}
```

## 🚀 Cara Kerja

1. **Inisialisasi**: Fungsi membuat array kosong `result` untuk menyimpan hasil akhir
2. **Pemrosesan Buku Sains**: 
   - Melakukan iterasi pada setiap buku sains
   - Mengubah huruf pertama menjadi kapital menggunakan `charAt(0).toUpperCase()`
   - Mengubah sisa huruf menjadi huruf kecil menggunakan `slice(1).toLowerCase()`
   - Menambahkan hasil format ke dalam array `result`
3. **Pemrosesan Buku Filsafat**: 
   - Melakukan proses yang sama seperti buku sains
   - Menambahkan hasil ke array `result` setelah buku-buku sains
4. **Return**: Mengembalikan array `result` yang berisi semua buku yang telah diformat

## 📋 Contoh Penggunaan

```javascript
// Contoh data input
const bukuSains = ["FISIKA KUANTUM", "biologi molekuler", "KiMiA oRgAnIk"];
const bukuFilsafat = ["ETIKA ARISTOTELES", "logika simbolik", "FiLsAfAt MoDeRn"];

// Memanggil fungsi
const perpustakaanTerorganisir = organizeLibrary(bukuSains, bukuFilsafat);

console.log(perpustakaanTerorganisir);
```

## 📤 Contoh Output

```javascript
[
    "Fisika kuantum",
    "Biologi molekuler", 
    "Kimia organik",
    "Etika aristoteles",
    "Logika simbolik",
    "Filsafat modern"
]
```

## 🎯 Kegunaan

- **Standardisasi Format**: Menyeragamkan format penulisan judul buku
- **Organisasi Perpustakaan**: Menggabungkan berbagai kategori buku dalam satu koleksi
- **Kemudahan Pencarian**: Format yang konsisten memudahkan pencarian dan pengurutan
- **Presentasi Data**: Membuat tampilan judul buku menjadi lebih rapi dan profesional

## ⚠️ Catatan Penting

- Fungsi ini tidak mengubah array input asli (immutable)
- Urutan buku dalam hasil akhir adalah: buku sains terlebih dahulu, kemudian buku filsafat
- Fungsi mengasumsikan input berupa array yang berisi string
- Jika ada string kosong, akan menghasilkan string kosong juga dalam output
