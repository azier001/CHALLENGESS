# 🌱 Dokumentasi Fungsi `dryPlants`

## 📋 Deskripsi

Fungsi `dryPlants` adalah sebuah fungsi JavaScript yang digunakan untuk mensimulasikan proses pengeringan tanaman. Fungsi ini akan mengurangi tingkat kelembaban tanaman yang memiliki kelembaban tinggi dan mengembalikan daftar tanaman beserta tingkat kelembaban barunya dalam format string.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `plants` | Array | Daftar nama-nama tanaman (dalam bentuk string) |
| `moistureLevels` | Array | Daftar tingkat kelembaban untuk setiap tanaman (dalam bentuk angka) |

**Catatan:** Kedua array harus memiliki panjang yang sama, dimana indeks yang sama pada kedua array merepresentasikan satu tanaman.

## ⚙️ Cara Kerja

1. **Pengurangan Kelembaban**: Jika tingkat kelembaban tanaman > 10, maka kelembaban akan dikurangi 5
2. **Batas Minimum**: Menggunakan `Math.max(0, nilai-5)` untuk memastikan nilai tidak pernah negatif
3. **Tanpa Perubahan**: Jika kelembaban ≤ 10, nilai tetap tidak berubah
4. **Format Output**: Setiap tanaman akan diformat menjadi string `"Nama Tanaman: Tingkat Kelembaban"`

## 📝 Kode Fungsi

```javascript
function dryPlants(plants, moistureLevels) {
    const result = [];
    
    // Melakukan iterasi untuk setiap tanaman
    for (let i = 0; i < plants.length; i++) {
        // Jika tingkat kelembaban di atas 10, kurangi dengan 5
        // Math.max(0, nilai-5) memastikan hasil tidak negatif
        if (moistureLevels[i] > 10) {
            moistureLevels[i] = Math.max(0, moistureLevels[i] - 5);
        }
        
        // Menambahkan string yang sudah diformat ke array hasil
        result.push(`${plants[i]}: ${moistureLevels[i]}`);
    }
    
    return result;
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Kelembaban Normal dan Tinggi
```javascript
const tanaman = ["Mawar", "Melati", "Anggrek"];
const kelembaban = [8, 12, 15];

const hasil = dryPlants(tanaman, kelembaban);
console.log(hasil);
```

**Output:**
```
["Mawar: 8", "Melati: 7", "Anggrek: 10"]
```

### Contoh 2: Kelembaban Rendah
```javascript
const tanaman = ["Kaktus", "Sukulen"];
const kelembaban = [3, 5];

const hasil = dryPlants(tanaman, kelembaban);
console.log(hasil);
```

**Output:**
```
["Kaktus: 3", "Sukulen: 5"]
```

### Contoh 3: Kelembaban Sangat Tinggi
```javascript
const tanaman = ["Pakis", "Lumut", "Bambu"];
const kelembaban = [25, 4, 18];

const hasil = dryPlants(tanaman, kelembaban);
console.log(hasil);
```

**Output:**
```
["Pakis: 20", "Lumut: 4", "Bambu: 13"]
```

### Contoh 4: Kelembaban yang Akan Menjadi Negatif
```javascript
const tanaman = ["Violet", "Dahlia"];
const kelembaban = [12, 3];

const hasil = dryPlants(tanaman, kelembaban);
console.log(hasil);
```

**Output:**
```
["Violet: 7", "Dahlia: 3"]
```

## 📊 Tabel Kondisi Kelembaban

| Kondisi Kelembaban | Aksi | Hasil | Contoh |
|-------------------|------|-------|--------|
| ≤ 10 | Tidak ada perubahan | Nilai tetap sama | 8 → 8, 5 → 5 |
| > 10 dan ≥ 5 setelah dikurangi | Kurangi 5 | Nilai - 5 | 15 → 10, 12 → 7 |
| > 10 tapi < 5 setelah dikurangi | Set ke 0 | Math.max(0, nilai-5) | 4 → 0, 3 → 0 |

## 🔍 Perbedaan dengan Versi Sebelumnya

Versi ini menggunakan **`Math.max(0, moistureLevels[i] - 5)`** yang lebih efisien daripada menggunakan dua kondisi if terpisah. Fungsi `Math.max()` secara otomatis memilih nilai terbesar antara 0 dan hasil pengurangan, sehingga memastikan nilai tidak pernah negatif.

## ⚠️ Catatan Penting

- **Modifikasi Array**: Fungsi ini **memodifikasi array `moistureLevels` asli**. Jika Anda ingin mempertahankan array asli, buat salinan terlebih dahulu
- Pastikan array `plants` dan `moistureLevels` memiliki panjang yang sama
- Tingkat kelembaban harus berupa angka (number)
- Fungsi tidak melakukan validasi input, jadi pastikan data yang dimasukkan sudah benar
- Nilai kelembaban minimum yang dikembalikan adalah 0

## 🚀 Tips Penggunaan

1. **Salinan Array**: Jika ingin mempertahankan data asli, gunakan `[...moistureLevels]` untuk membuat salinan
   ```javascript
   const kelembabanAsli = [12, 8, 15];
   const kelembabanSalinan = [...kelembabanAsli];
   const hasil = dryPlants(tanaman, kelembabanSalinan);
   ```

2. **Validasi Data**: Selalu pastikan kedua array memiliki panjang yang sama sebelum memanggil fungsi

3. **Tipe Data**: Pastikan `moistureLevels` berisi angka, bukan string

4. **Debugging**: Gunakan `console.log()` untuk memeriksa input dan output jika ada masalah

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja dan penggunaan fungsi `dryPlants` dalam JavaScript.*
