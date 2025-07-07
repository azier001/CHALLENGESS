# 🍎 Dokumentasi Fungsi `compareApples`

## 📋 Deskripsi

Fungsi `compareApples` adalah sebuah fungsi JavaScript yang digunakan untuk membandingkan dua varietas apel berdasarkan kesamaan karakter dalam nama mereka. Fungsi ini menghitung persentase kesamaan dengan membandingkan karakter-karakter pada posisi yang sama dari kedua nama varietas apel.

## 🎯 Kegunaan

- Menganalisis kesamaan nama varietas apel
- Memberikan skor persentase kesamaan
- Menampilkan hasil dalam format yang mudah dibaca

## 📝 Parameter

| Parameter | Tipe Data | Deskripsi | Contoh |
|-----------|-----------|-----------|---------|
| `variety1` | String | Nama varietas apel pertama | "Fuji" |
| `variety2` | String | Nama varietas apel kedua | "Gala" |
| `appleCount` | Number | Jumlah apel yang dibandingkan | 5 |

## ⚙️ Cara Kerja

1. **Menentukan Panjang Minimum**: Fungsi mengambil panjang string yang lebih pendek antara kedua varietas
2. **Menghitung Karakter yang Sama**: Membandingkan setiap karakter pada posisi yang sama
3. **Menghitung Skor Kesamaan**: Menggunakan rumus `(karakter_sama / panjang_minimum) × 100`
4. **Mengembalikan Hasil**: Memberikan string dengan format yang informatif

## 🔤 Tabel Contoh Perbandingan Karakter

### Contoh 1: "Fuji" vs "Gala"
| Posisi | Karakter 1 | Karakter 2 | Sama? |
|--------|------------|------------|-------|
| 0 | F | G | ❌ |
| 1 | u | a | ❌ |
| 2 | j | l | ❌ |
| 3 | i | a | ❌ |

**Hasil**: 0/4 = 0% kesamaan

### Contoh 2: "Apple" vs "Apricot"
| Posisi | Karakter 1 | Karakter 2 | Sama? |
|--------|------------|------------|-------|
| 0 | A | A | ✅ |
| 1 | p | p | ✅ |
| 2 | p | r | ❌ |
| 3 | l | i | ❌ |
| 4 | e | c | ❌ |

**Hasil**: 2/5 = 40% kesamaan

## 💻 Kode Fungsi

```javascript
function compareApples(variety1, variety2, appleCount) {
    // Find the shorter length for comparison
    const shorterLength = Math.min(variety1.length, variety2.length);
    
    // Count matching characters
    let matchingChars = 0;
    for (let i = 0; i < shorterLength; i++) {
        if (variety1[i] === variety2[i]) {
            matchingChars++;
        }
    }
    
    // Calculate similarity score
    const similarityScore = (matchingChars / shorterLength) * 100;
    
    // Return formatted string
    return `Comparing ${appleCount} ${variety1} apples with ${variety2} apples: ${similarityScore.toFixed(2)}% similarity`;
}
```

## 🚀 Contoh Penggunaan

```javascript
// Contoh 1: Membandingkan Fuji dengan Gala
console.log(compareApples("Fuji", "Gala", 10));

// Contoh 2: Membandingkan Apple dengan Apricot
console.log(compareApples("Apple", "Apricot", 5));

// Contoh 3: Membandingkan Red dengan Green
console.log(compareApples("Red", "Green", 3));
```

## 📊 Contoh Output

```
Comparing 10 Fuji apples with Gala apples: 0.00% similarity
Comparing 5 Apple apples with Apricot apples: 40.00% similarity
Comparing 3 Red apples with Green apples: 0.00% similarity
```

## 🧮 Penjelasan Perhitungan

### Formula Kesamaan:
```
Persentase Kesamaan = (Jumlah Karakter Sama / Panjang String Terpendek) × 100
```

### Contoh Perhitungan Detail:
- **Input**: "Apple" vs "Apricot"
- **Panjang terpendek**: min(5, 7) = 5
- **Karakter yang sama**: A=A ✅, p=p ✅, p≠r ❌, l≠i ❌, e≠c ❌
- **Total karakter sama**: 2
- **Perhitungan**: (2/5) × 100 = 40%

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** (membedakan huruf besar dan kecil)
- Hanya membandingkan karakter sampai panjang string terpendek
- Hasil dibulatkan hingga 2 angka desimal
- Parameter `appleCount` hanya digunakan untuk format output, tidak mempengaruhi perhitungan

## 🎭 Tips Penggunaan

1. **Konsistensi Format**: Gunakan format yang sama untuk nama varietas (misalnya semua huruf kecil)
2. **Validasi Input**: Pastikan parameter tidak kosong sebelum memanggil fungsi
3. **Interpretasi Hasil**: Skor 0% artinya tidak ada kesamaan, 100% artinya identik pada karakter awal

---

*Dokumentasi ini dibuat untuk membantu pemahaman fungsi `compareApples` dengan penjelasan yang mudah dipahami untuk pemula.*
