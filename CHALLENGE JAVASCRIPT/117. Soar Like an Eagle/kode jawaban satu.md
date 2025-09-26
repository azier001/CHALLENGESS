# 🦅 Dokumentasi Fungsi `soarLikeEagle`

## 📖 Deskripsi

Fungsi `soarLikeEagle` adalah sebuah fungsi JavaScript yang digunakan untuk mengulangi setiap karakter dalam string dengan aturan khusus. Huruf vokal akan diulang lebih banyak dibandingkan huruf konsonan, memberikan efek "terbang tinggi" seperti elang pada teks.

## ⚙️ Sintaks

```javascript
soarLikeEagle(str, n)
```

## 📝 Parameter

| Parameter | Tipe   | Deskripsi                                                |
|-----------|--------|----------------------------------------------------------|
| `str`     | String | Teks yang akan diproses dan karakter-karakternya diulang |
| `n`       | Number | Jumlah pengulangan dasar untuk setiap karakter          |

### 📋 Detail Parameter:
- **`str`**: String input yang berisi teks apapun (huruf, angka, simbol)
- **`n`**: Angka yang menentukan berapa kali karakter akan diulang
  - Jika `n <= 0`, fungsi akan mengembalikan string kosong
  - Huruf vokal akan diulang `n + 1` kali
  - Huruf konsonan dan karakter lain akan diulang `n` kali

## 🔤 Tabel Karakter Vokal

| Huruf Vokal |
|-------------|
| a           |
| e           |
| i           |
| o           |
| u           |

**Catatan**: Fungsi ini mendeteksi vokal dengan mengubah karakter ke huruf kecil terlebih dahulu, sehingga huruf besar seperti A, E, I, O, U juga akan dikenali sebagai vokal.

## 💻 Kode Lengkap

```javascript
function soarLikeEagle(str, n) {
  // Jika n kurang dari atau sama dengan 0, kembalikan string kosong
  if (n <= 0) {
    return '';
  }
  
  // Definisi huruf vokal dalam array (hanya huruf kecil)
  const vowels = ['a', 'e', 'i', 'o', 'u'];
  let result = '';
  
  // Loop melalui setiap indeks karakter dalam string
  for (let i = 0; i < str.length; i++) {
    // Ambil karakter dan ubah ke huruf kecil untuk pengecekan vokal
    const char = str[i].toLowerCase();
    
    // Tentukan jumlah pengulangan berdasarkan jenis karakter
    const repeat = vowels.includes(char) ? n + 1 : n;
    
    // Tambahkan karakter asli (dengan case yang dipertahankan) yang sudah diulang ke hasil
    result += str[i].repeat(repeat);
  }
  
  // Kembalikan hasil akhir
  return result;
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Penggunaan Dasar
```javascript
console.log(soarLikeEagle("hello", 2));
// Output: "hheellllooo"
```

**Penjelasan:**
- `h` (konsonan) → diulang 2 kali → `hh`
- `e` (vokal) → diulang 3 kali (2+1) → `eee`
- `l` (konsonan) → diulang 2 kali → `ll`
- `l` (konsonan) → diulang 2 kali → `ll`
- `o` (vokal) → diulang 3 kali (2+1) → `ooo`

### Contoh 2: Dengan Huruf Besar dan Kecil
```javascript
console.log(soarLikeEagle("JavaScript", 1));
// Output: "JaaavaaaSSccrriipptt"
```

**Penjelasan:**
- Huruf besar seperti `J` dan `S` tetap dipertahankan case-nya
- `a`, `i`, dan `a` dikenali sebagai vokal dan diulang 2 kali

### Contoh 3: Dengan Angka dan Simbol
```javascript
console.log(soarLikeEagle("Code123!", 2));
// Output: "CCoodddeee112233!!"
```

### Contoh 4: Nilai n = 0
```javascript
console.log(soarLikeEagle("test", 0));
// Output: ""
```

### Contoh 5: Huruf Besar Vokal
```javascript
console.log(soarLikeEagle("AEIOU", 1));
// Output: "AAEEIIOOUU"
```

## 📊 Tabel Contoh Output

| Input               | n | Output                      | Keterangan                        |
|---------------------|---|-----------------------------|-----------------------------------|
| `"ai"`              | 1 | `"aaaii"`                  | Kedua huruf vokal diulang 2 kali  |
| `"bc"`              | 1 | `"bc"`                     | Kedua konsonan diulang 1 kali     |
| `"Halo"`            | 2 | `"HHaaalllooo"`            | Vokal 3 kali, konsonan 2 kali    |
| `"123"`             | 1 | `"123"`                    | Angka diulang 1 kali              |
| `"A"`               | 3 | `"AAAA"`                   | Vokal besar diulang 4 kali (3+1)  |
| `"Hello World"`     | 1 | `"HHeellllloo WWoorrlldd"` | Spasi juga diulang sebagai konsonan |

## ⚠️ Catatan Penting

- Fungsi ini **case-insensitive** untuk pendeteksian vokal (huruf besar A,E,I,O,U akan dikenali sebagai vokal)
- **Case original dipertahankan** dalam output (huruf besar tetap besar, huruf kecil tetap kecil)
- Menggunakan array `['a', 'e', 'i', 'o', 'u']` untuk deteksi vokal dengan `toLowerCase()`
- Semua karakter yang bukan vokal (konsonan, angka, simbol, spasi) akan diulang sebanyak `n` kali
- Jika parameter `n` bernilai 0 atau negatif, fungsi akan mengembalikan string kosong
- Menggunakan loop `for` dengan indeks untuk iterasi karakter

## 🔄 Perbedaan dengan Versi Sebelumnya

| Aspek              | Versi Ini                    | Versi Sebelumnya           |
|-------------------|------------------------------|----------------------------|
| Deteksi Vokal     | Array + toLowerCase()        | String "aeiouAEIOU"        |
| Loop Method       | for loop dengan indeks       | for...of loop              |
| Case Sensitivity  | Case-insensitive detection   | Case-sensitive detection   |
| Case Preservation | Ya (case asli dipertahankan) | Ya                         |

## 🎯 Kegunaan

Fungsi ini cocok digunakan untuk:
- Membuat efek teks yang unik untuk game atau aplikasi
- Simulasi suara atau efek vokal dalam teks
- Pembelajaran tentang manipulasi string dan pengulangan karakter
- Membuat pattern teks yang menarik untuk desain atau animasi
- Latihan algoritma dengan case-insensitive string processing
