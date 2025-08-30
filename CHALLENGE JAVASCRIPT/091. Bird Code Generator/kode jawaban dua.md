# 🐦 Dokumentasi Fungsi `birdCode`

## 📝 Deskripsi Fungsi

Fungsi `birdCode` adalah sebuah fungsi JavaScript yang menganalisis nama burung dan menghasilkan kode numerik berdasarkan tiga kriteria khusus. Fungsi ini akan memeriksa karakteristik tertentu dari string nama burung dan memberikan kode yang sesuai dengan kondisi yang terpenuhi.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `birdName` | `string` | Nama burung yang akan dianalisis untuk menghasilkan kode |

## 📊 Tabel Karakter Kode

| Kode | Kondisi | Penjelasan |
|------|---------|------------|
| `1` | Jumlah huruf vokal adalah bilangan prima | Menghitung huruf vokal (a, e, i, o, u) dalam nama burung. Jika jumlahnya adalah bilangan prima, tambahkan "1" |
| `2` | Panjang nama adalah bilangan kuadrat sempurna | Jika panjang string nama burung adalah akar kuadrat sempurna (4, 9, 16, 25, dll), tambahkan "2" |
| `3` | Nama adalah palindrom | Jika nama burung dibaca dari depan dan belakang sama (tidak case-sensitive), tambahkan "3" |
| `0` | Tidak memenuhi kondisi apapun | Jika tidak ada kondisi yang terpenuhi, return "0" |

## 💾 Kode Fungsi

```javascript
function birdCode(birdName) {
    let code = "";
    
    // Periksa apakah jumlah huruf vokal adalah bilangan prima
    const vowels = "aeiouAEIOU";
    const vowelCount = birdName.split('').filter(char => vowels.includes(char)).length;
    
    // Fungsi untuk mengecek bilangan prima
    function isPrime(n) {
        if (n < 2) return false;
        
        for (let i = 2; i <= Math.sqrt(n); i++) {
            if (n % i === 0) return false;
        }
        
        return true;
    }
    
    // Jika jumlah vokal adalah prima, tambahkan "1"
    if (isPrime(vowelCount)) {
        code += "1";
    }
    
    // Periksa apakah panjang nama adalah bilangan kuadrat sempurna
    const length = birdName.length;
    if (Number.isInteger(Math.sqrt(length))) {
        code += "2";
    }
    
    // Periksa apakah nama adalah palindrom (tidak case-sensitive)
    const normalized = birdName.toLowerCase();
    if (normalized === normalized.split('').reverse().join('')) {
        code += "3";
    }
    
    // Return kode yang terbentuk, atau "0" jika tidak ada kondisi yang terpenuhi
    return code || "0";
}
```

## 🧮 Cara Kerja Fungsi

1. **Pengecekan Huruf Vokal Prima**: 
   - Menghitung jumlah huruf vokal (a, e, i, o, u) dalam nama burung
   - Menggunakan fungsi `isPrime()` untuk mengecek apakah jumlah tersebut adalah bilangan prima
   - Jika ya, tambahkan "1" ke kode

2. **Pengecekan Kuadrat Sempurna**:
   - Mengambil panjang string nama burung
   - Mengecek apakah panjang tersebut adalah bilangan kuadrat sempurna menggunakan `Math.sqrt()`
   - Jika ya, tambahkan "2" ke kode

3. **Pengecekan Palindrom**:
   - Mengkonversi nama ke huruf kecil untuk perbandingan yang tidak case-sensitive
   - Membandingkan string asli dengan versi terbaliknya
   - Jika sama, tambahkan "3" ke kode

4. **Return Hasil**:
   - Jika ada kondisi yang terpenuhi, return kode yang terbentuk
   - Jika tidak ada kondisi yang terpenuhi, return "0"

## 📋 Contoh Penggunaan dan Output

### Contoh 1: Nama dengan Huruf Vokal Prima
```javascript
birdCode("Eagle");
// Output: "12"
// - Huruf vokal: E, a, e = 3 huruf (3 adalah bilangan prima) → "1"
// - Panjang: 5 huruf (bukan kuadrat sempurna)
// - Bukan palindrom
// - Panjang: 5 huruf, √5 ≈ 2.236 (bukan integer) → tidak dapat "2"
```

### Contoh 2: Nama Palindrom
```javascript
birdCode("Anna");
// Output: "3"
// - Huruf vokal: A, a = 2 huruf (2 adalah bilangan prima) → "1"
// - Panjang: 4 huruf, √4 = 2 (adalah kuadrat sempurna) → "2"
// - "anna" = "anna" (palindrom) → "3"
// - Hasil: "123"
```

### Contoh 3: Tidak Memenuhi Kondisi
```javascript
birdCode("Robin");
// Output: "0"
// - Huruf vokal: o, i = 2 huruf (2 adalah bilangan prima) → "1"
// - Panjang: 5 huruf (bukan kuadrat sempurna)
// - Bukan palindrom
// - Hasil akhir: "1"
```

### Contoh 4: Memenuhi Semua Kondisi
```javascript
birdCode("Abba");
// Output: "123"
// - Huruf vokal: A, a = 2 huruf (2 adalah bilangan prima) → "1"
// - Panjang: 4 huruf, √4 = 2 (adalah kuadrat sempurna) → "2"
// - "abba" = "abba" (palindrom) → "3"
// - Hasil: "123"
```

## 🎯 Tips Penggunaan

- Fungsi ini **case-sensitive** untuk penghitungan vokal (mengenali huruf besar dan kecil)
- Untuk pengecekan palindrom, fungsi menggunakan **case-insensitive** comparison
- Jika tidak ada kondisi yang terpenuhi, fungsi akan mengembalikan string "0"
- Kode yang dihasilkan adalah gabungan dari semua kondisi yang terpenuhi (bisa "1", "2", "3", "12", "13", "23", "123", atau "0")

## ⚠️ Catatan Penting

- Bilangan prima dimulai dari 2, sehingga jika nama burung tidak memiliki huruf vokal (jumlah = 0) atau hanya 1 huruf vokal, kondisi prima tidak terpenuhi
- Kuadrat sempurna yang dimaksud adalah 1, 4, 9, 16, 25, 36, 49, dst.
- Palindrom diperiksa setelah mengkonversi semua huruf menjadi huruf kecil
