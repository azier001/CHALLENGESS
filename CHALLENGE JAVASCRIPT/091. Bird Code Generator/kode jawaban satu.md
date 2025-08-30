# 🐦 Dokumentasi Fungsi `birdCode`

## 📝 Deskripsi Fungsi

Fungsi `birdCode` adalah sebuah fungsi JavaScript yang menganalisis nama burung dan menghasilkan kode numerik berdasarkan tiga kriteria khusus. Fungsi ini menggunakan fungsi helper untuk memeriksa karakteristik tertentu dari string nama burung dan memberikan kode yang sesuai dengan kondisi yang terpenuhi.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `birdName` | `string` | Nama burung yang akan dianalisis untuk menghasilkan kode |

## 📊 Tabel Karakter Kode

| Kode | Kondisi | Penjelasan |
|------|---------|------------|
| `1` | Jumlah huruf vokal adalah bilangan prima | Menghitung huruf vokal (a, e, i, o, u) dalam nama burung. Jika jumlahnya adalah bilangan prima, tambahkan "1" |
| `2` | Panjang nama adalah bilangan kuadrat sempurna | Jika panjang string nama burung adalah akar kuadrat sempurna (4, 9, 16, 25, dll), tambahkan "2" |
| `3` | Nama adalah palindrom | Jika nama burung dibaca dari depan dan belakang sama (case-sensitive), tambahkan "3" |
| `0` | Tidak memenuhi kondisi apapun | Jika tidak ada kondisi yang terpenuhi, return "0" |

## 💾 Kode Fungsi

```javascript
function birdCode(birdName) {
  let code = '';
  
  // Periksa apakah jumlah huruf vokal adalah bilangan prima
  const vowels = 'aeiouAEIOU';
  const vowelCount = birdName.split('').filter(char => vowels.includes(char)).length;
  
  if (isPrime(vowelCount)) {
    code += '1';
  }
  
  // Periksa apakah panjang nama adalah bilangan kuadrat sempurna
  const length = birdName.length;
  if (isPerfectSquare(length)) {
    code += '2';
  }
  
  // Periksa apakah nama adalah palindrom
  if (isPalindrome(birdName)) {
    code += '3';
  }
  
  // Return kode yang terbentuk, atau "0" jika tidak ada kondisi yang terpenuhi
  return code || '0';
}

// Fungsi helper untuk mengecek bilangan prima
function isPrime(num) {
  // Bilangan kurang dari atau sama dengan 1 bukan prima
  if (num <= 1) {
    return false;
  }
  
  // Cek pembagi dari 2 sampai akar kuadrat dari num
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) {
      return false;
    }
  }
  
  return true;
}

// Fungsi helper untuk mengecek bilangan kuadrat sempurna
function isPerfectSquare(num) {
  const sqrt = Math.sqrt(num);
  
  // Cek apakah hasil akar kuadrat adalah bilangan bulat
  return sqrt === Math.floor(sqrt);
}

// Fungsi helper untuk mengecek palindrom
function isPalindrome(word) {
  const reversed = word.split('').reverse().join('');
  
  // Bandingkan kata asli dengan kata yang dibalik
  return word === reversed;
}
```

## 🧮 Cara Kerja Fungsi

### Fungsi Utama `birdCode()`

1. **Pengecekan Huruf Vokal Prima**: 
   - Menghitung jumlah huruf vokal (a, e, i, o, u, A, E, I, O, U) dalam nama burung
   - Menggunakan fungsi `isPrime()` untuk mengecek apakah jumlah tersebut adalah bilangan prima
   - Jika ya, tambahkan "1" ke kode

2. **Pengecekan Kuadrat Sempurna**:
   - Mengambil panjang string nama burung
   - Menggunakan fungsi `isPerfectSquare()` untuk mengecek apakah panjang tersebut adalah bilangan kuadrat sempurna
   - Jika ya, tambahkan "2" ke kode

3. **Pengecekan Palindrom**:
   - Menggunakan fungsi `isPalindrome()` untuk mengecek apakah nama adalah palindrom
   - Jika ya, tambahkan "3" ke kode

4. **Return Hasil**:
   - Jika ada kondisi yang terpenuhi, return kode yang terbentuk
   - Jika tidak ada kondisi yang terpenuhi, return "0"

### Fungsi Helper

- **`isPrime(num)`**: Mengecek apakah sebuah angka adalah bilangan prima dengan cara mencari pembagi dari 2 hingga akar kuadrat angka tersebut
- **`isPerfectSquare(num)`**: Mengecek apakah sebuah angka adalah kuadrat sempurna dengan membandingkan hasil akar kuadrat dengan bilangan bulatnya
- **`isPalindrome(word)`**: Mengecek apakah sebuah kata adalah palindrom dengan membandingkan kata asli dengan kata yang dibalik

## 📋 Contoh Penggunaan dan Output

### Contoh 1: Nama dengan Huruf Vokal Prima
```javascript
birdCode("Eagle");
// Output: "1"
// - Huruf vokal: E, a, e = 3 huruf (3 adalah bilangan prima) → "1"
// - Panjang: 5 huruf, √5 ≈ 2.236 (bukan integer) → tidak dapat "2"
// - "Eagle" ≠ "elgaE" (bukan palindrom) → tidak dapat "3"
```

### Contoh 2: Nama dengan Panjang Kuadrat Sempurna
```javascript
birdCode("Hawk");
// Output: "2"
// - Huruf vokal: a = 1 huruf (1 bukan bilangan prima) → tidak dapat "1"
// - Panjang: 4 huruf, √4 = 2 (adalah kuadrat sempurna) → "2"
// - "Hawk" ≠ "kwaH" (bukan palindrom) → tidak dapat "3"
```

### Contoh 3: Nama Palindrom (Case-Sensitive)
```javascript
birdCode("Abba");
// Output: "12"
// - Huruf vokal: A, a = 2 huruf (2 adalah bilangan prima) → "1"
// - Panjang: 4 huruf, √4 = 2 (adalah kuadrat sempurna) → "2"
// - "Abba" ≠ "abbA" (bukan palindrom karena case-sensitive) → tidak dapat "3"
```

### Contoh 4: Palindrom Case-Sensitive yang Benar
```javascript
birdCode("abba");
// Output: "123"
// - Huruf vokal: a, a = 2 huruf (2 adalah bilangan prima) → "1"
// - Panjang: 4 huruf, √4 = 2 (adalah kuadrat sempurna) → "2"
// - "abba" = "abba" (palindrom) → "3"
```

### Contoh 5: Tidak Memenuhi Kondisi Apapun
```javascript
birdCode("Robin");
// Output: "1"
// - Huruf vokal: o, i = 2 huruf (2 adalah bilangan prima) → "1"
// - Panjang: 5 huruf (bukan kuadrat sempurna) → tidak dapat "2"
// - "Robin" ≠ "niboR" (bukan palindrom) → tidak dapat "3"
```

### Contoh 6: Benar-benar Tidak Memenuhi Kondisi
```javascript
birdCode("Crow");
// Output: "2"
// - Huruf vokal: o = 1 huruf (1 bukan bilangan prima) → tidak dapat "1"
// - Panjang: 4 huruf, √4 = 2 (adalah kuadrat sempurna) → "2"
// - "Crow" ≠ "worC" (bukan palindrom) → tidak dapat "3"
```

## 🎯 Tips Penggunaan

- Fungsi ini **case-sensitive** untuk penghitungan vokal (mengenali huruf besar dan kecil)
- Untuk pengecekan palindrom, fungsi menggunakan **case-sensitive** comparison (berbeda dengan versi sebelumnya)
- Jika tidak ada kondisi yang terpenuhi, fungsi akan mengembalikan string "0"
- Kode yang dihasilkan adalah gabungan dari semua kondisi yang terpenuhi (bisa "1", "2", "3", "12", "13", "23", "123", atau "0")
- Fungsi menggunakan helper functions yang terpisah untuk meningkatkan keterbacaan dan kemudahan maintenance

## ⚠️ Catatan Penting

- **Bilangan Prima**: Dimulai dari 2, sehingga jika nama burung tidak memiliki huruf vokal (jumlah = 0) atau hanya 1 huruf vokal, kondisi prima tidak terpenuhi
- **Kuadrat Sempurna**: Yang dimaksud adalah 1, 4, 9, 16, 25, 36, 49, dst.
- **Palindrom**: Diperiksa dengan **case-sensitive**, artinya "Abba" ≠ "abbA"
- **Modular Design**: Kode menggunakan fungsi helper yang terpisah untuk setiap pengecekan, membuatnya lebih mudah dibaca dan di-maintain

## 🔧 Keunggulan Struktur Kode

1. **Separation of Concerns**: Setiap fungsi helper memiliki tanggung jawab yang spesifik
2. **Reusability**: Fungsi helper dapat digunakan kembali di bagian lain dari kode
3. **Testability**: Setiap fungsi dapat ditest secara terpisah
4. **Readability**: Kode utama lebih mudah dibaca karena logic detail disembunyikan dalam helper functions
