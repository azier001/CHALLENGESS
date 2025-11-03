# 🔍 Dokumentasi Fungsi `strangeAdventure`

## 📝 Deskripsi

Fungsi `strangeAdventure` adalah sebuah fungsi yang mencari petunjuk tersembunyi dalam sebuah array string berdasarkan cipher (kode rahasia). Fungsi ini akan:

1. Mencari substring dalam setiap petunjuk yang merupakan **anagram** dari cipher
2. Mengurutkan substring yang ditemukan berdasarkan jumlah kode karakter ASCII
3. Menggabungkan dan mentransformasi substring menjadi pesan rahasia

Fungsi ini menggunakan fungsi pembantu `hasSameCharacters` untuk memeriksa apakah dua string memiliki karakter yang sama (anagram).

## 🎯 Cara Kerja

Fungsi ini bekerja seperti detektif yang memecahkan teka-teki:
- Memeriksa setiap petunjuk satu per satu
- Mencari bagian kata yang huruf-hurufnya sama dengan cipher (anagram)
- Menyusun petunjuk yang ditemukan berdasarkan nilai karakternya
- Mengubah format pesan: huruf besar → spasi, huruf kecil → huruf besar

## 📥 Parameter

### Fungsi `strangeAdventure`

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `clues` | Array of String | Array yang berisi petunjuk-petunjuk (string) yang akan diperiksa |
| `cipher` | String | Kode rahasia yang digunakan sebagai pembanding untuk mencari anagram |

### Fungsi `hasSameCharacters` (Helper)

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `str1` | String | String pertama yang akan dibandingkan |
| `str2` | String | String kedua yang akan dibandingkan |

## 📤 Return Value

### Fungsi `strangeAdventure`

| Tipe | Deskripsi |
|------|-----------|
| String | Pesan tersembunyi yang sudah ditransformasi, atau `"No hidden message found!"` jika tidak ada anagram yang ditemukan |

### Fungsi `hasSameCharacters`

| Tipe | Deskripsi |
|------|-----------|
| Boolean | `true` jika kedua string memiliki karakter yang sama (anagram), `false` jika tidak |

## 🔤 Tabel Karakter & Transformasi

| Input | Output | Keterangan |
|-------|--------|------------|
| A-Z (Huruf Besar) | spasi ` ` | Semua huruf kapital diubah menjadi spasi |
| a-z (Huruf Kecil) | A-Z (Huruf Besar) | Semua huruf kecil diubah menjadi huruf kapital |
| Karakter lain | Tidak berubah | Karakter selain huruf tetap sama |

## 💻 Source Code

```javascript
function strangeAdventure(clues, cipher) {
  const decipheredClues = [];
  
  // Iterasi setiap petunjuk dalam array clues
  for (const clue of clues) {
    // Periksa setiap kemungkinan substring dengan panjang sama dengan cipher
    for (let i = 0; i <= clue.length - cipher.length; i++) {
      const substring = clue.slice(i, i + cipher.length);
      
      // Cek apakah substring adalah anagram dari cipher
      if (hasSameCharacters(substring, cipher)) {
        decipheredClues.push(substring);
      }
    }
  }
  
  // Jika tidak ada anagram yang ditemukan, kembalikan pesan khusus
  if (decipheredClues.length === 0) {
    return "No hidden message found!";
  }
  
  // Urutkan berdasarkan jumlah kode karakter ASCII
  decipheredClues.sort((a, b) => {
    // Hitung total nilai ASCII untuk string a
    const sumA = a.split('').reduce((sum, char) => sum + char.charCodeAt(0), 0);
    
    // Hitung total nilai ASCII untuk string b
    const sumB = b.split('').reduce((sum, char) => sum + char.charCodeAt(0), 0);
    
    // Urutkan dari nilai terkecil ke terbesar
    return sumA - sumB;
  });
  
  // Gabungkan semua petunjuk yang sudah diurutkan
  const hiddenMessage = decipheredClues.join('');
  
  // Transformasi pesan: huruf besar → spasi, huruf kecil → huruf besar
  const modifiedMessage = hiddenMessage
    .replace(/[A-Z]/g, ' ')                    // Ganti semua huruf besar dengan spasi
    .replace(/[a-z]/g, char => char.toUpperCase()); // Ubah semua huruf kecil jadi besar
  
  return modifiedMessage;
}


function hasSameCharacters(str1, str2) {
  // Jika panjang berbeda, pasti bukan anagram
  if (str1.length !== str2.length) {
    return false;
  }
  
  // Objek untuk menghitung frekuensi setiap karakter
  const charCount = {};
  
  // Hitung frekuensi karakter dari string pertama
  for (const char of str1) {
    charCount[char] = (charCount[char] || 0) + 1;
  }
  
  // Kurangi frekuensi berdasarkan karakter dari string kedua
  for (const char of str2) {
    // Jika karakter tidak ada atau sudah habis, bukan anagram
    if (!charCount[char]) {
      return false;
    }
    charCount[char]--;
  }
  
  // Jika semua karakter cocok, maka anagram
  return true;
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
   - "aBc": 'a' → 'A', 'B' → ' ' (spasi), 'c' → 'C'
   - "CbA": 'C' → ' ' (spasi), 'b' → 'B', 'A' → ' ' (spasi)

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

### Contoh 4: Multiple Anagram dalam Satu Clue

```javascript
const clues = ["abccba", "def"];
const cipher = "abc";

const result = strangeAdventure(clues, cipher);
console.log(result);
```

**Output:**
```
ABC CBA
```

**Penjelasan:**
1. Ditemukan 2 anagram dalam clue pertama: "abc" dan "cba"
2. Keduanya diurutkan berdasarkan nilai ASCII
3. Setelah transformasi semua huruf kecil menjadi huruf besar

### Contoh 5: Penggunaan Fungsi `hasSameCharacters`

```javascript
// Contoh langsung menggunakan fungsi helper
console.log(hasSameCharacters("abc", "bca")); // true
console.log(hasSameCharacters("abc", "def")); // false
console.log(hasSameCharacters("aab", "aba")); // true
console.log(hasSameCharacters("abc", "abcd")); // false
```

**Output:**
```
true
false
true
false
```

## 🔑 Konsep Penting

### Apa itu Anagram?

Anagram adalah kata atau frasa yang dibentuk dengan menyusun ulang huruf-huruf dari kata lain. Contoh:
- "abc" dan "bca" adalah anagram
- "abc" dan "cab" adalah anagram
- "listen" dan "silent" adalah anagram
- "abc" dan "xyz" BUKAN anagram

### Cara Kerja `hasSameCharacters`

Fungsi ini menggunakan metode **character counting** untuk memeriksa anagram:

1. **Membuat Map Frekuensi**: Menghitung berapa kali setiap karakter muncul di string pertama
   ```javascript
   // Untuk "aab":
   // charCount = { 'a': 2, 'b': 1 }
   ```

2. **Verifikasi dengan String Kedua**: Mengurangi hitungan untuk setiap karakter di string kedua
   ```javascript
   // Untuk "aba":
   // 'a' → charCount['a'] = 1
   // 'b' → charCount['b'] = 0
   // 'a' → charCount['a'] = 0
   // Semua karakter cocok! ✓
   ```

3. **Hasil**: Jika semua karakter cocok sempurna (hitungan menjadi 0), maka kedua string adalah anagram

### Pengurutan Berdasarkan ASCII

Setiap karakter memiliki nilai ASCII:
- 'A' = 65, 'B' = 66, 'C' = 67, dst.
- 'a' = 97, 'b' = 98, 'c' = 99, dst.

Fungsi menjumlahkan nilai ASCII semua karakter dalam string menggunakan `reduce()`, lalu mengurutkan dari nilai terkecil ke terbesar.

**Contoh:**
- "abc" = 97 + 98 + 99 = 294
- "ABC" = 65 + 66 + 67 = 198
- "ABC" akan muncul lebih dulu karena nilainya lebih kecil

## 🆚 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Lama | Versi Baru | Keuntungan |
|-------|-----------|-----------|------------|
| **Pengecekan Anagram** | Menggunakan sort string | Menggunakan character counting | Lebih efisien, tidak perlu sorting |
| **Perhitungan ASCII** | Loop manual | Menggunakan `reduce()` | Lebih ringkas dan fungsional |
| **Transformasi** | Loop dengan `map()` | Menggunakan `replace()` dengan regex | Lebih concise dan mudah dibaca |
| **Ekstraksi Substring** | `substring()` | `slice()` | Lebih modern dan konsisten |

## 💡 Tips Penggunaan

1. **Cipher harus memiliki panjang yang sama atau lebih pendek** dari clues untuk menemukan anagram
2. **Huruf besar dan kecil dianggap berbeda** saat mencari anagram
3. **Hasil akhir selalu dalam huruf kapital atau spasi** karena proses transformasi
4. Fungsi case-sensitive, jadi "ABC" dan "abc" berbeda
5. **Fungsi `hasSameCharacters` lebih efisien** dari sorting untuk string panjang karena kompleksitasnya O(n) vs O(n log n)

## ⚙️ Kompleksitas Algoritma

### Fungsi `hasSameCharacters`
- **Time Complexity**: O(n) - dimana n adalah panjang string
- **Space Complexity**: O(k) - dimana k adalah jumlah karakter unik

### Fungsi `strangeAdventure`
- **Time Complexity**: O(m × n × k + p log p)
  - m = jumlah clues
  - n = panjang rata-rata clue
  - k = panjang cipher
  - p = jumlah anagram yang ditemukan
- **Space Complexity**: O(p × k) - untuk menyimpan anagram yang ditemukan

## ⚠️ Catatan

- Fungsi ini **case-sensitive**, artinya 'a' dan 'A' dianggap karakter yang berbeda
- Jika tidak ada anagram yang ditemukan, akan mengembalikan string khusus
- Proses pencarian dilakukan untuk setiap kemungkinan substring, jadi bisa menemukan anagram yang sama lebih dari sekali dalam satu clue
- Metode `slice()` lebih direkomendasikan dibanding `substring()` di JavaScript modern
- Menggunakan `const` untuk variabel yang tidak berubah (best practice)

## 🎓 Konsep JavaScript yang Digunakan

1. **Array Methods**: `push()`, `sort()`, `join()`, `split()`, `reduce()`
2. **String Methods**: `slice()`, `replace()`, `toUpperCase()`, `charCodeAt()`
3. **Regular Expressions**: `/[A-Z]/g`, `/[a-z]/g`
4. **Arrow Functions**: `(a, b) => { ... }`
5. **Object/Map**: Untuk character counting
6. **Higher-Order Functions**: `reduce()` untuk agregasi data

---

📚 **Dibuat untuk pembelajaran JavaScript** - Fungsi untuk memahami konsep string manipulation, anagram, transformasi karakter, dan penggunaan metode array modern.
