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

| Huruf Kecil | Huruf Besar |
|-------------|-------------|
| a           | A           |
| e           | E           |
| i           | I           |
| o           | O           |
| u           | U           |

## 💻 Kode Lengkap

```javascript
function soarLikeEagle(str, n) {
  // Jika n kurang dari atau sama dengan 0, kembalikan string kosong
  if (n <= 0) return "";
  
  // Definisi huruf vokal (huruf kecil dan besar)
  const vowels = "aeiouAEIOU";
  let result = "";
  
  // Loop melalui setiap karakter dalam string
  for (let char of str) {
    // Tentukan jumlah pengulangan berdasarkan jenis karakter
    const repeatCount = vowels.includes(char) ? n + 1 : n;
    
    // Tambahkan karakter yang sudah diulang ke hasil
    result += char.repeat(repeatCount);
  }
  
  // Kembalikan hasil akhir
  return result;
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Penggunaan Dasar
```javascript
console.log(soarLikeEagle("hello", 2));
// Output: "hheelllloo"
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
// Output: "JaaavvaaSSccrriiipptt"
```

### Contoh 3: Dengan Angka dan Simbol
```javascript
console.log(soarLikeEagle("Code123!", 2));
// Output: "CCooddee112233!!"
```

### Contoh 4: Nilai n = 0
```javascript
console.log(soarLikeEagle("test", 0));
// Output: ""
```

## 📊 Tabel Contoh Output

| Input               | n | Output                      | Keterangan                        |
|---------------------|---|-----------------------------|-----------------------------------|
| `"ai"`              | 1 | `"aaii"`                   | Kedua huruf vokal diulang 2 kali  |
| `"bc"`              | 1 | `"bc"`                     | Kedua konsonan diulang 1 kali     |
| `"Halo"`            | 2 | `"HHaaalllooo"`            | Vokal 3 kali, konsonan 2 kali    |
| `"123"`             | 1 | `"123"`                    | Angka diulang 1 kali              |
| `"a"`               | 3 | `"aaaa"`                   | Vokal diulang 4 kali (3+1)       |

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** untuk pendeteksian vokal (membedakan huruf besar dan kecil)
- Semua karakter yang bukan vokal (konsonan, angka, simbol) akan diulang sebanyak `n` kali
- Jika parameter `n` bernilai 0 atau negatif, fungsi akan mengembalikan string kosong
- Spasi dan karakter khusus lainnya diperlakukan sebagai konsonan

## 🎯 Kegunaan

Fungsi ini cocok digunakan untuk:
- Membuat efek teks yang unik untuk game atau aplikasi
- Simulasi suara atau efek vokal dalam teks
- Pembelajaran tentang manipulasi string dan pengulangan karakter
- Membuat pattern teks yang menarik untuk desain atau animasi
