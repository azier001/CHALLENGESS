# 🧌 Palindrome Monster Detector

## 📋 Gambaran Challenge

**Difficulty Level:** `Easy` 🟢

Buat sebuah function yang mendeteksi palindrome monster yang bersembunyi dalam string teks! Misi Anda adalah membangun detector khusus yang dapat mengidentifikasi makhluk licik ini yang bersembunyi dalam kata dan frasa.

---

## 🎯 Tujuan

Buat sebuah function bernama `isMonsterPalindrome` yang menerima parameter `string` dan menentukan apakah palindrome monster ada atau tidak.

### 📝 Spesifikasi Function

- **Function Name:** `isMonsterPalindrome`
- **Parameter:** `string` (teks yang akan dianalisis)
- **Return Type:** `string` (pesan peringatan)

---

## 🔍 Aturan Deteksi

Palindrome monster detector Anda harus:

- ✅ Mengecek apakah string yang diberikan adalah palindrome (dibaca sama dari depan dan belakang)
- ✅ **Mengabaikan spasi dan tanda baca** selama pengecekan palindrome
- ✅ Case-insensitive (menganggap huruf besar dan kecil sama)

---

## ⚡ Return Values

### 🚨 Monster Terdeteksi
Jika string **ADALAH** palindrome:
```
"Beware, a palindrome monster is near!"
```

### 🛡️ Zona Aman
Jika string **BUKAN** palindrome:
```
"You are safe from palindrome monsters... for now."
```

---

## 📚 Contoh

| Input | Palindrome? | Expected Output |
|-------|-------------|-----------------|
| `"racecar"` | ✅ Ya | `"Beware, a palindrome monster is near!"` |
| `"A man, a plan, a canal: Panama"` | ✅ Ya | `"Beware, a palindrome monster is near!"` |
| `"race a car"` | ❌ Tidak | `"You are safe from palindrome monsters... for now."` |
| `"hello"` | ❌ Tidak | `"You are safe from palindrome monsters... for now."` |

---

## 💡 Petunjuk Implementasi

1. **Preprocessing:** Bersihkan string dengan menghapus spasi, tanda baca, dan mengubah ke lowercase
2. **Comparison:** Bandingkan string yang sudah dibersihkan dengan kebalikannya
3. **String Methods:** Pertimbangkan menggunakan method seperti:
   - `replace()` dengan regular expressions
   - `toLowerCase()` atau `toUpperCase()`
   - Teknik string reversal

---

## 🏆 Kriteria Keberhasilan

- [ ] Function mengidentifikasi palindrome dengan benar
- [ ] Mengabaikan spasi dan tanda baca
- [ ] Case-insensitive comparison
- [ ] Mengembalikan pesan yang sesuai spesifikasi
- [ ] Menangani edge cases (string kosong, karakter tunggal, dll.)

---

## 🚀 Siap Berburu Monster?

Saatnya implementasikan palindrome monster detector Anda dan jaga dunia dari makhluk teks licik ini! Ingat, mereka bisa bersembunyi di balik spasi dan tanda baca, jadi detector Anda harus tajam dan teliti.

Semoga berhasil, pemburu monster! 🗡️✨
