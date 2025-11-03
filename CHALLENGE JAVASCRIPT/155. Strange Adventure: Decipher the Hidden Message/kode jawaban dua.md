# 🔍 Dokumentasi Fungsi `strangeAdventure`

## 📝 Deskripsi

Fungsi `strangeAdventure` adalah sebuah fungsi yang mencari petunjuk tersembunyi dalam sebuah array string berdasarkan cipher (kode rahasia). Fungsi ini akan:

1. Mencari substring dalam setiap petunjuk yang merupakan **anagram** dari cipher
2. Mengurutkan substring yang ditemukan berdasarkan jumlah kode karakter ASCII
3. Menggabungkan dan mentransformasi substring menjadi pesan rahasia

## 🎯 Cara Kerja

Fungsi ini bekerja seperti detektif yang memecahkan teka-teki:
- Memeriksa setiap petunjuk satu per satu
- Mencari bagian kata yang huruf-hurufnya sama dengan cipher (anagram)
- Menyusun petunjuk yang ditemukan berdasarkan nilai karakternya
- Mengubah format pesan: huruf besar → spasi, huruf kecil → huruf besar

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `clues` | Array of String | Array yang berisi petunjuk-petunjuk (string) yang akan diperiksa |
| `cipher` | String | Kode rahasia yang digunakan sebagai pembanding untuk mencari anagram |

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| String | Pesan tersembunyi yang sudah ditransformasi, atau `"No hidden message found!"` jika tidak ada anagram yang ditemukan |

## 🔤 Tabel Karakter & Transformasi

| Input | Output | Keterangan |
|-------|--------|------------|
| A-Z (Huruf Besar) | spasi ` ` | Semua huruf kapital diubah menjadi spasi |
| a-z (Huruf Kecil) | A-Z (Huruf Besar) | Semua huruf kecil diubah menjadi huruf kapital |
| Karakter lain | Tidak berubah | Karakter selain huruf tetap sama |

## 💻 Source Code

```javascript
function strangeAdventure(clues, cipher) {
  let decipheredClues = [];
  
  // Fungsi pembantu untuk memeriksa apakah dua string adalah anagram
  function areAnagrams(str1, str2) {
    // Jika panjang berbeda, pasti bukan anagram
    if (str1.length !== str2.length) return false;
    
    // Urutkan huruf-huruf dalam kedua string
    const sorted1 = str1.split('').sort().join('');
    const sorted2 = str2.split('').sort().join('');
    
    // Bandingkan hasil pengurutan
    return sorted1 === sorted2;
  }
  
  // Ekstrak substring dan bandingkan dengan cipher
  for (let clue of clues) {
    // Cek setiap kemungkinan substring dengan panjang sama dengan cipher
    for (let i = 0; i <= clue.length - cipher.length; i++) {
      let substring = clue.substring(i, i + cipher.length);
      
      // Jika substring adalah anagram dari cipher, simpan
      if (areAnagrams(substring, cipher)) {
        decipheredClues.push(substring);
      }
    }
  }
  
  // Periksa apakah ada petunjuk yang ditemukan
  if (decipheredClues.length === 0) {
    return "No hidden message found!";
  }
  
  // Urutkan berdasarkan jumlah kode karakter ASCII
  decipheredClues.sort((a, b) => {
    let sumA = 0, sumB = 0;
    
    // Hitung total nilai ASCII untuk string a
    for (let char of a) sumA += char.charCodeAt(0);
    
    // Hitung total nilai ASCII untuk string b
    for (let char of b) sumB += char.charCodeAt(0);
    
    // Urutkan dari nilai terkecil ke terbesar
    return sumA - sumB;
  });
  
  // Gabungkan semua petunjuk yang sudah diurutkan
  let hiddenMessage = decipheredClues.join('');
  
  // Transformasi pesan: huruf besar → spasi, huruf kecil → huruf besar
  hiddenMessage = hiddenMessage.split('').map(char => {
    // Jika huruf besar (A-Z), ubah jadi spasi
    if (char >= 'A' && char <= 'Z') return ' ';
    
    // Jika huruf kecil (a-z), ubah jadi huruf besar
    if (char >= 'a' && char <= 'z') return char.toUpperCase();
    
    // Karakter lain tetap tidak berubah
    return char;
  }).join('');
  
  return hiddenMessage;
}
```

## 📋 Contoh Penggunaan

### Contoh 1: Menemukan Pesan Tersembunyi

```javascript
const clues = ["abcDef", "ghiJkl", "mnoPqr"];
const cipher = "abc";

const result = strangeAdventure(clues, cipher);
console.log(result);
```

**Output:**
```
ABC
```

**Penjelasan:**
1. Fungsi mencari anagram dari "abc" dalam setiap clue
2. Ditemukan "abc" di clue pertama (index 0-2)
3. Setelah transformasi: 'a' → 'A', 'b' → 'B', 'c' → 'C'

### Contoh 2: Dengan Huruf Kapital

```javascript
const clues = ["aBcD", "CbAd", "xyz"];
const cipher = "abc";

const result = strangeAdventure(clues, cipher);
console.log(result);
```

**Output:**
```
AB  AB 
```

**Penjelasan:**
1. Ditemukan "aBc" dan "CbA" sebagai anagram dari "abc"
2. Setelah diurutkan dan ditransformasi:
   - 'a' → 'A', 'B' → ' ' (spasi), 'c' → 'C'
   - 'C' → ' ' (spasi), 'b' → 'B', 'A' → ' ' (spasi)

### Contoh 3: Tidak Ada Anagram

```javascript
const clues = ["xyz", "def", "ghi"];
const cipher = "abc";

const result = strangeAdventure(clues, cipher);
console.log(result);
```

**Output:**
```
No hidden message found!
```

**Penjelasan:**
Tidak ada substring dalam clues yang merupakan anagram dari "abc"

## 🔑 Konsep Penting

### Apa itu Anagram?

Anagram adalah kata atau frasa yang dibentuk dengan menyusun ulang huruf-huruf dari kata lain. Contoh:
- "abc" dan "bca" adalah anagram
- "abc" dan "cab" adalah anagram
- "abc" dan "xyz" BUKAN anagram

### Pengurutan Berdasarkan ASCII

Setiap karakter memiliki nilai ASCII:
- 'A' = 65, 'B' = 66, 'C' = 67, dst.
- 'a' = 97, 'b' = 98, 'c' = 99, dst.

Fungsi menjumlahkan nilai ASCII semua karakter dalam string, lalu mengurutkan dari nilai terkecil ke terbesar.

## 💡 Tips Penggunaan

1. **Cipher harus memiliki panjang yang sama atau lebih pendek** dari clues untuk menemukan anagram
2. **Huruf besar dan kecil dianggap berbeda** saat mencari anagram
3. **Hasil akhir selalu dalam huruf kapital atau spasi** karena proses transformasi
4. Fungsi case-sensitive, jadi "ABC" dan "abc" berbeda

## ⚠️ Catatan

- Fungsi ini **case-sensitive**, artinya 'a' dan 'A' dianggap karakter yang berbeda
- Jika tidak ada anagram yang ditemukan, akan mengembalikan string khusus
- Proses pencarian dilakukan untuk setiap kemungkinan substring, jadi bisa menemukan anagram yang sama lebih dari sekali dalam satu clue

---

📚 **Dibuat untuk pembelajaran JavaScript** - Fungsi untuk memahami konsep string manipulation, anagram, dan transformasi karakter.
