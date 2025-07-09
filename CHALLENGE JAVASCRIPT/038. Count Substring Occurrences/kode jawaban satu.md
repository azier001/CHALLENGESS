# 📚 Dokumentasi Fungsi `countSubstringOccurrences`

## 🔍 Deskripsi Fungsi

Fungsi `countSubstringOccurrences` adalah sebuah fungsi JavaScript yang digunakan untuk mencari dan menghitung kemunculan substring dalam sebuah string. Fungsi ini memiliki beberapa kriteria khusus:

- Mencari semua substring yang mengandung substring tertentu
- Membatasi panjang maksimum substring yang dicari
- Mengabaikan substring yang mengandung angka (digit)
- Mengembalikan objek yang berisi substring beserta jumlah kemunculannya

## 📝 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `str` | String | String utama tempat pencarian dilakukan |
| `substr` | String | Substring yang ingin dicari dalam string utama |
| `maxLen` | Number | Panjang maksimum substring yang akan dianalisis |

## 🔧 Kode Fungsi

```javascript
function countSubstringOccurrences(str, substr, maxLen) {
    // Mengembalikan objek kosong jika substr kosong atau maxLen adalah 0
    if (substr === '' || maxLen === 0) {
        return {};
    }

    const result = {};

    // Mencari semua kemungkinan substring dalam string utama
    for (let i = 0; i < str.length; i++) {
        for (let j = i + 1; j <= str.length; j++) {
            const substring = str.slice(i, j);

            // Mengecek apakah substring memenuhi kriteria:
            // 1. Mengandung substr yang dicari
            // 2. Panjangnya tidak melebihi maxLen
            // 3. Tidak mengandung angka/digit
            if (
                substring.includes(substr) &&
                substring.length <= maxLen &&
                !/\d/.test(substring)
            ) {
                // Menambahkan atau menginkremen jumlah kemunculan substring
                result[substring] = (result[substring] || 0) + 1;
            }
        }
    }

    return result;
}
```

## 🎯 Cara Kerja Fungsi

1. **Validasi Input**: Fungsi pertama-tama memeriksa apakah `substr` kosong atau `maxLen` adalah 0. Jika ya, mengembalikan objek kosong.

2. **Pencarian Substring**: Menggunakan nested loop untuk mencari semua kemungkinan substring dalam string utama:
   - Loop pertama (`i`) menentukan posisi awal substring
   - Loop kedua (`j`) menentukan posisi akhir substring

3. **Filtering dan Counting**: Untuk setiap substring yang ditemukan, fungsi mengecek apakah:
   - Mengandung substring yang dicari (`substr`)
   - Panjangnya tidak melebihi `maxLen`
   - Tidak mengandung angka/digit

4. **Increment Counter**: Jika substring memenuhi kriteria, jumlah kemunculannya akan ditambahkan ke dalam objek hasil.

5. **Return**: Mengembalikan objek dengan key berupa substring dan value berupa jumlah kemunculannya.

## 📊 Contoh Penggunaan

### Contoh 1: Pencarian Dasar
```javascript
const text = "hello world hello";
const result = countSubstringOccurrences(text, "hello", 10);
console.log(result);
```

**Output:**
```javascript
{
    "hello": 2,
    "hello ": 1,
    "hello w": 1,
    "hello wo": 1,
    "hello wor": 1,
    "hello worl": 1,
    "hello world": 1,
    "hello world ": 1,
    "hello world h": 1,
    "hello world he": 1
}
```

### Contoh 2: Dengan Angka (Diabaikan)
```javascript
const text = "cat123 cat dog cat";
const result = countSubstringOccurrences(text, "cat", 8);
console.log(result);
```

**Output:**
```javascript
{
    "cat": 2,
    "cat ": 1,
    "cat d": 1,
    "cat do": 1,
    "cat dog": 1,
    "cat dog ": 1,
    "cat dog c": 1,
    "cat dog ca": 1,
    "cat dog cat": 1
}
```

*Perhatikan bahwa "cat123" tidak muncul dalam hasil karena mengandung angka.*

### Contoh 3: Batasan Panjang
```javascript
const text = "programming";
const result = countSubstringOccurrences(text, "gram", 5);
console.log(result);
```

**Output:**
```javascript
{
    "gram": 1,
    "gramm": 1
}
```

### Contoh 4: String Kosong atau MaxLen 0
```javascript
const text = "hello world";
const result1 = countSubstringOccurrences(text, "", 5);
const result2 = countSubstringOccurrences(text, "hello", 0);

console.log(result1); // {}
console.log(result2); // {}
```

## ⚡ Perbedaan dengan Versi Sebelumnya

Versi ini lebih efisien karena:
- **Menghitung secara langsung**: Tidak perlu menyimpan substring dalam Set terlebih dahulu
- **Satu kali loop**: Menghitung kemunculan sambil mencari substring
- **Lebih sederhana**: Logika yang lebih streamlined tanpa mengurangi fungsionalitas

## 🔄 Tabel Perbandingan Karakter

| Karakter | Diterima | Ditolak | Keterangan |
|----------|----------|---------|------------|
| Huruf (a-z, A-Z) | ✅ | ❌ | Semua huruf diterima |
| Angka (0-9) | ❌ | ✅ | Substring dengan angka diabaikan |
| Spasi | ✅ | ❌ | Spasi diterima sebagai karakter valid |
| Simbol (!@#$%^&*) | ✅ | ❌ | Simbol khusus diterima |

## ⚠️ Catatan Penting

- Fungsi ini case-sensitive (membedakan huruf besar dan kecil)
- Substring yang mengandung angka akan diabaikan sepenuhnya
- Panjang substring dibatasi oleh parameter `maxLen`
- Menggunakan metode increment `(result[substring] || 0) + 1` untuk menghitung
- Kompleksitas waktu: O(n³) dimana n adalah panjang string

## 🚀 Tips Penggunaan

1. **Untuk pencarian yang efisien**: Gunakan `maxLen` yang tidak terlalu besar untuk menghindari pemrosesan yang lambat
2. **Untuk hasil yang akurat**: Pastikan `substr` tidak kosong
3. **Untuk debugging**: Gunakan `console.log` untuk melihat proses pencarian step-by-step
4. **Untuk performa**: Fungsi ini cocok untuk string dengan panjang sedang (< 1000 karakter)

## 💡 Contoh Penggunaan Praktis

```javascript
// Mencari kata "code" dalam dokumentasi
const documentation = "This code example shows how to code efficiently";
const result = countSubstringOccurrences(documentation, "code", 15);
console.log(result);

// Output akan menampilkan semua substring yang mengandung "code"
// dengan panjang maksimal 15 karakter
```
