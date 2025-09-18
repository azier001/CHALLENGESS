# 🌱 Dokumentasi Fungsi `dryPlants`

## 📋 Deskripsi

Fungsi `dryPlants` adalah sebuah fungsi JavaScript yang digunakan untuk mensimulasikan proses pengeringan tanaman. Fungsi ini akan mengurangi tingkat kelembaban tanaman dan mengembalikan daftar tanaman beserta tingkat kelembaban barunya dalam format string.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `plants` | Array | Daftar nama-nama tanaman (dalam bentuk string) |
| `moistureLevels` | Array | Daftar tingkat kelembaban untuk setiap tanaman (dalam bentuk angka) |

**Catatan:** Kedua array harus memiliki panjang yang sama, dimana indeks yang sama pada kedua array merepresentasikan satu tanaman.

## ⚙️ Cara Kerja

1. **Pengurangan Kelembaban**: Jika tingkat kelembaban tanaman > 10, maka kelembaban akan dikurangi 5
2. **Batas Minimum**: Jika hasil pengurangan menghasilkan nilai negatif, maka nilai akan diset menjadi 0
3. **Format Output**: Setiap tanaman akan diformat menjadi string `"Nama Tanaman: Tingkat Kelembaban"`

## 📝 Kode Fungsi

```javascript
function dryPlants(plants, moistureLevels) {
    const result = [];
    
    // Melakukan iterasi untuk setiap tanaman
    for (let i = 0; i < plants.length; i++) {
        let newMoistureLevel = moistureLevels[i];
        
        // Jika tingkat kelembaban di atas 10, kurangi dengan 5
        if (moistureLevels[i] > 10) {
            newMoistureLevel = moistureLevels[i] - 5;
        }
        
        // Jika tingkat kelembaban menjadi negatif, set menjadi 0
        if (newMoistureLevel < 0) {
            newMoistureLevel = 0;
        }
        
        // Menambahkan string yang sudah diformat ke array hasil
        result.push(`${plants[i]}: ${newMoistureLevel}`);
    }
    
    return result;
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Kelembaban Normal
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

### Contoh 3: Kelembaban Tinggi
```javascript
const tanaman = ["Pakis", "Lumut"];
const kelembaban = [25, 18];

const hasil = dryPlants(tanaman, kelembaban);
console.log(hasil);
```

**Output:**
```
["Pakis: 20", "Lumut: 13"]
```

## 📊 Tabel Kondisi Kelembaban

| Kondisi Kelembaban | Aksi | Hasil |
|-------------------|------|-------|
| ≤ 10 | Tidak ada perubahan | Nilai tetap sama |
| > 10 | Kurangi 5 | Nilai - 5 |
| Hasil negatif | Set ke 0 | Nilai = 0 |

## ⚠️ Catatan Penting

- Pastikan array `plants` dan `moistureLevels` memiliki panjang yang sama
- Tingkat kelembaban harus berupa angka (number)
- Fungsi tidak melakukan validasi input, jadi pastikan data yang dimasukkan sudah benar
- Nilai kelembaban minimum yang dikembalikan adalah 0

## 🚀 Tips Penggunaan

1. **Validasi Data**: Selalu pastikan kedua array memiliki panjang yang sama sebelum memanggil fungsi
2. **Tipe Data**: Pastikan `moistureLevels` berisi angka, bukan string
3. **Debugging**: Gunakan `console.log()` untuk memeriksa input dan output jika ada masalah

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja dan penggunaan fungsi `dryPlants` dalam JavaScript.*
