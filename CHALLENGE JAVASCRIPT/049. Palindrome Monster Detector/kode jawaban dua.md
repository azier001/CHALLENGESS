# 👹 Fungsi isMonsterPalindrome

## 📋 Deskripsi

Fungsi `isMonsterPalindrome` adalah sebuah fungsi JavaScript yang memeriksa apakah sebuah string merupakan palindrome (kata yang dibaca sama dari depan maupun belakang) dengan tema monster yang menyenangkan! 🎭

Fungsi ini akan membersihkan string input dari spasi, tanda baca, dan mengubahnya menjadi huruf kecil sebelum melakukan pengecekan palindrome. Jika string tersebut adalah palindrome, maka "monster palindrome" akan muncul!

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|--------|
| `str` | `string` | String yang akan dicek apakah palindrome atau bukan | `"A man, a plan, a canal: Panama"` |

## 🔄 Return Value

| Kondisi | Return Value |
|---------|--------------|
| String adalah palindrome | `"Beware, a palindrome monster is near!"` |
| String bukan palindrome | `"You are safe from palindrome monsters... for now."` |

## 💻 Kode Fungsi

```javascript
function isMonsterPalindrome(str) {
    // Hapus spasi, tanda baca, dan ubah ke huruf kecil
    const cleanStr = str.toLowerCase().replace(/[^a-z0-9]/g, '');
    
    // Periksa apakah string yang sudah dibersihkan adalah palindrome
    const reversed = cleanStr.split('').reverse().join('');
    
    if (cleanStr === reversed) {
        return "Beware, a palindrome monster is near!";
    } else {
        return "You are safe from palindrome monsters... for now.";
    }
}
```

## 🎯 Cara Kerja

1. **Pembersihan String**: Fungsi akan mengubah semua huruf menjadi kecil dan menghapus semua karakter yang bukan huruf atau angka
2. **Pembalikan String**: String yang sudah dibersihkan akan dibalik urutannya
3. **Perbandingan**: String asli (yang sudah dibersihkan) dibandingkan dengan string yang sudah dibalik
4. **Return Pesan**: Mengembalikan pesan sesuai hasil perbandingan

## 📝 Contoh Penggunaan

### Contoh 1: String Palindrome
```javascript
console.log(isMonsterPalindrome("A man, a plan, a canal: Panama"));
// Output: "Beware, a palindrome monster is near!"
```

### Contoh 2: String Bukan Palindrome
```javascript
console.log(isMonsterPalindrome("Hello World"));
// Output: "You are safe from palindrome monsters... for now."
```

### Contoh 3: Palindrome Sederhana
```javascript
console.log(isMonsterPalindrome("racecar"));
// Output: "Beware, a palindrome monster is near!"
```

### Contoh 4: Palindrome dengan Angka
```javascript
console.log(isMonsterPalindrome("A Santa at NASA"));
// Output: "Beware, a palindrome monster is near!"
```

## 📊 Tabel Contoh Input dan Output

| Input | String Bersih | Palindrome? | Output |
|-------|---------------|-------------|--------|
| `"racecar"` | `"racecar"` | ✅ Ya | `"Beware, a palindrome monster is near!"` |
| `"hello"` | `"hello"` | ❌ Tidak | `"You are safe from palindrome monsters... for now."` |
| `"A man, a plan, a canal: Panama"` | `"amanaplanacanalpanama"` | ✅ Ya | `"Beware, a palindrome monster is near!"` |
| `"race a car"` | `"raceacar"` | ❌ Tidak | `"You are safe from palindrome monsters... for now."` |
| `"Was it a car or a cat I saw?"` | `"wasitacaroracatisaw"` | ✅ Ya | `"Beware, a palindrome monster is near!"` |

## 🔍 Penjelasan Detail

### Regex Pattern `[^a-z0-9]`
- `^` dalam square brackets berarti "BUKAN"
- `a-z` berarti semua huruf kecil dari a sampai z
- `0-9` berarti semua angka dari 0 sampai 9
- Jadi pattern ini akan mencocokkan semua karakter yang BUKAN huruf atau angka

### Method yang Digunakan
- `toLowerCase()`: Mengubah semua huruf menjadi kecil
- `replace()`: Mengganti karakter yang cocok dengan pattern
- `split('')`: Memecah string menjadi array karakter
- `reverse()`: Membalik urutan array
- `join('')`: Menggabungkan array menjadi string kembali

## ⚠️ Catatan Penting

- Fungsi ini case-insensitive (tidak membedakan huruf besar/kecil)
- Spasi dan tanda baca akan diabaikan
- Hanya huruf (a-z) dan angka (0-9) yang diperhitungkan
- Fungsi ini cocok untuk pemula yang ingin belajar manipulasi string dan logika dasar

## 🎪 Fun Facts

Beberapa contoh palindrome terkenal yang bisa dicoba:
- "Madam"
- "A Toyota's a Toyota"
- "Never odd or even"
- "Do geese see God?"
