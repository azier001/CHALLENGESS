# 🍎 Dokumentasi Fungsi `compareApples`

## 📋 Deskripsi

Fungsi `compareApples` adalah sebuah fungsi JavaScript yang digunakan untuk membandingkan dua varietas apel berdasarkan kesamaan karakter dalam nama mereka. Fungsi ini menghitung persentase kesamaan dengan membandingkan karakter-karakter pada posisi yang sama dari kedua nama varietas apel, **tanpa membedakan huruf besar dan kecil** (case-insensitive).

## 🎯 Kegunaan

- Menganalisis kesamaan nama varietas apel
- Memberikan skor persentase kesamaan
- Menampilkan hasil dalam format yang mudah dibaca
- Membandingkan nama dengan mengabaikan perbedaan kapitalisasi

## 📝 Parameter

| Parameter | Tipe Data | Deskripsi | Contoh |
|-----------|-----------|-----------|---------|
| `variety1` | String | Nama varietas apel pertama | "Fuji" |
| `variety2` | String | Nama varietas apel kedua | "GALA" |
| `appleCount` | Number | Jumlah apel yang dibandingkan | 5 |

## ⚙️ Cara Kerja

1. **Menentukan Panjang Minimum**: Fungsi mengambil panjang string yang lebih pendek antara kedua varietas
2. **Konversi ke Huruf Kecil**: Setiap karakter diubah ke huruf kecil sebelum dibandingkan
3. **Menghitung Karakter yang Sama**: Membandingkan setiap karakter pada posisi yang sama
4. **Menghitung Skor Kesamaan**: Menggunakan rumus `(karakter_sama / panjang_minimum) × 100`
5. **Pembulatan Hasil**: Membulatkan hingga 2 angka desimal
6. **Mengembalikan Hasil**: Memberikan string dengan format yang informatif

## 🔤 Tabel Contoh Perbandingan Karakter

### Contoh 1: "Fuji" vs "GALA"
| Posisi | Karakter 1 | Karakter 2 | Lowercase 1 | Lowercase 2 | Sama? |
|--------|------------|------------|-------------|-------------|-------|
| 0 | F | G | f | g | ❌ |
| 1 | u | A | u | a | ❌ |
| 2 | j | L | j | l | ❌ |
| 3 | i | A | i | a | ❌ |

**Hasil**: 0/4 = 0% kesamaan

### Contoh 2: "Apple" vs "APRICOT"
| Posisi | Karakter 1 | Karakter 2 | Lowercase 1 | Lowercase 2 | Sama? |
|--------|------------|------------|-------------|-------------|-------|
| 0 | A | A | a | a | ✅ |
| 1 | p | P | p | p | ✅ |
| 2 | p | R | p | r | ❌ |
| 3 | l | I | l | i | ❌ |
| 4 | e | C | e | c | ❌ |

**Hasil**: 2/5 = 40% kesamaan

### Contoh 3: "RED" vs "red"
| Posisi | Karakter 1 | Karakter 2 | Lowercase 1 | Lowercase 2 | Sama? |
|--------|------------|------------|-------------|-------------|-------|
| 0 | R | r | r | r | ✅ |
| 1 | E | e | e | e | ✅ |
| 2 | D | d | d | d | ✅ |

**Hasil**: 3/3 = 100% kesamaan

## 💻 Kode Fungsi

```javascript
function compareApples(variety1, variety2, appleCount) {
  let matchingChars = 0;
  const minLength = Math.min(variety1.length, variety2.length);

  for (let i = 0; i < minLength; i++) {
    if (variety1[i].toLowerCase() === variety2[i].toLowerCase()) {
      matchingChars++;
    }
  }

  const similarityScore = (matchingChars / minLength) * 100;
  const roundedScore = similarityScore.toFixed(2);

  return `Comparing ${appleCount} ${variety1} apples with ${variety2} apples: ${roundedScore}% similarity`;
}
```

## 🚀 Contoh Penggunaan

```javascript
// Contoh 1: Membandingkan Fuji dengan GALA (huruf besar kecil berbeda)
console.log(compareApples("Fuji", "GALA", 10));

// Contoh 2: Membandingkan Apple dengan APRICOT
console.log(compareApples("Apple", "APRICOT", 5));

// Contoh 3: Membandingkan RED dengan red (sama persis setelah lowercase)
console.log(compareApples("RED", "red", 3));

// Contoh 4: Membandingkan Granny dengan Green
console.log(compareApples("Granny", "Green", 7));
```

## 📊 Contoh Output

```
Comparing 10 Fuji apples with GALA apples: 0.00% similarity
Comparing 5 Apple apples with APRICOT apples: 40.00% similarity
Comparing 3 RED apples with red apples: 100.00% similarity
Comparing 7 Granny apples with Green apples: 16.67% similarity
```

## 🧮 Penjelasan Perhitungan

### Formula Kesamaan:
```
Persentase Kesamaan = (Jumlah Karakter Sama / Panjang String Terpendek) × 100
```

### Contoh Perhitungan Detail:
- **Input**: "Granny" vs "Green"
- **Panjang terpendek**: min(6, 5) = 5
- **Konversi lowercase**: "granny" vs "green"
- **Karakter yang sama**: g=g ✅, r=r ✅, a≠e ❌, n≠e ❌, n≠n ❌
- **Total karakter sama**: 2
- **Perhitungan**: (2/5) × 100 = 40%
- **Hasil akhir**: 40.00%

## ⚠️ Catatan Penting

- Fungsi ini **case-insensitive** (tidak membedakan huruf besar dan kecil)
- Hanya membandingkan karakter sampai panjang string terpendek
- Hasil dibulatkan hingga 2 angka desimal menggunakan `toFixed(2)`
- Parameter `appleCount` hanya digunakan untuk format output, tidak mempengaruhi perhitungan
- Menggunakan method `.toLowerCase()` untuk konversi huruf

## 🎭 Tips Penggunaan

1. **Fleksibilitas Input**: Tidak perlu khawatir dengan kapitalisasi nama varietas
2. **Validasi Input**: Pastikan parameter tidak kosong sebelum memanggil fungsi
3. **Interpretasi Hasil**: 
   - 0% = tidak ada kesamaan
   - 100% = identik (setelah konversi lowercase)
   - 50-99% = memiliki kesamaan sebagian
4. **Contoh Praktis**: Berguna untuk mencocokkan nama varietas dengan toleransi penulisan

## 🔍 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Lama | Versi Baru |
|-------|------------|------------|
| **Case Sensitivity** | Membedakan huruf besar/kecil | Tidak membedakan (case-insensitive) |
| **Variabel** | `shorterLength` | `minLength` |
| **Pembulatan** | Langsung dalam return | Disimpan dalam `roundedScore` |
| **Fleksibilitas** | Terbatas | Lebih fleksibel untuk input |

---

*Dokumentasi ini dibuat untuk membantu pemahaman fungsi `compareApples` versi terbaru dengan penjelasan yang mudah dipahami untuk pemula.*
