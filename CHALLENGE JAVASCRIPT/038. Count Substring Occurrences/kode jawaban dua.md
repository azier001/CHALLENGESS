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
    if (!substr || maxLen === 0) {
        return {};
    }

    const result = {};
    const validSubstrings = new Set();

    // Mencari semua substring yang mengandung substr, memiliki panjang <= maxLen, dan tidak mengandung angka
    for (let i = 0; i <= str.length - substr.length; i++) {
        for (let j = i + substr.length; j <= str.length && j - i <= maxLen; j++) {
            const substring = str.slice(i, j);

            // Mengecek apakah substring mengandung substr dan tidak memiliki angka
            if (substring.includes(substr) && !/\d/.test(substring)) {
                validSubstrings.add(substring);
            }
        }
    }

    // Menghitung kemunculan dari setiap substring yang valid
    for (const validSubstring of validSubstrings) {
        let count = 0;
        
        for (let i = 0; i <= str.length - validSubstring.length; i++) {
            if (str.slice(i, i + validSubstring.length) === validSubstring) {
                count++;
            }
        }
        
        result[validSubstring] = count;
    }

    return result;
}
```

## 🎯 Cara Kerja Fungsi

1. **Validasi Input**: Fungsi pertama-tama memeriksa apakah `substr` kosong atau `maxLen` adalah 0. Jika ya, mengembalikan objek kosong.

2. **Pencarian Substring**: Menggunakan nested loop untuk mencari semua kemungkinan substring dalam string utama.

3. **Filtering**: Hanya menyimpan substring yang:
   - Mengandung substring yang dicari (`substr`)
   - Panjangnya tidak melebihi `maxLen`
   - Tidak mengandung angka/digit

4. **Penghitungan**: Untuk setiap substring yang valid, menghitung berapa kali substring tersebut muncul dalam string utama.

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

## ⚠️ Catatan Penting

- Fungsi ini case-sensitive (membedakan huruf besar dan kecil)
- Substring yang mengandung angka akan diabaikan
- Panjang substring dibatasi oleh parameter `maxLen`
- Menggunakan `Set` untuk menghindari duplikasi substring
- Kompleksitas waktu: O(n³) dimana n adalah panjang string

## 🚀 Tips Penggunaan

1. **Untuk pencarian yang efisien**: Gunakan `maxLen` yang tidak terlalu besar untuk menghindari pemrosesan yang lambat
2. **Untuk hasil yang akurat**: Pastikan `substr` tidak kosong
3. **Untuk debugging**: Gunakan `console.log` untuk melihat proses pencarian step-by-step
