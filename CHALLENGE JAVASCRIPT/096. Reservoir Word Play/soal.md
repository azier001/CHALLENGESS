# 🌊 Reservoir Word Play Challenge

## 📋 Gambaran Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function yang memanipulasi string berdasarkan deteksi palindrome. Challenge ini menggabungkan manipulasi string, pengecekan palindrome, dan logika kondisional.

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `reservoirWordPlay` yang memproses input string secara berbeda berdasarkan apakah string tersebut palindrome atau tidak.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function reservoirWordPlay(word)
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `word` | `string` | Input string yang akan dimanipulasi |

### Return Value
- **Type:** `string`
- **Deskripsi:** String yang telah dimanipulasi berdasarkan kondisi palindrome

---

## ⚡ Logika Algorithm

Function mengikuti proses keputusan dua langkah:

### 🔄 Kasus 1: Palindrome Terdeteksi
> Ketika input string terbaca sama dari depan dan belakang

**Aksi:** Hapus semua vowel
- **Target vowel:** `a`, `e`, `i`, `o`, `u` (case-insensitive)
- **Proses:** Filter karakter vowel dari string
- **Return:** String yang telah dimodifikasi tanpa vowel

### 🔄 Kasus 2: Bukan Palindrome
> Ketika input string terbaca berbeda dari depan dan belakang

**Aksi:** Reverse string
- **Proses:** Balik urutan karakter
- **Return:** String yang telah di-reverse

---

## 📝 Contoh

### Contoh 1: Input Palindrome
```
Input: "racecar"
✓ Is palindrome: true
→ Remove vowels: "rccr"
Output: "rccr"
```

### Contoh 2: Input Non-Palindrome
```
Input: "hello"
✗ Is palindrome: false
→ Reverse string: "olleh"
Output: "olleh"
```

### Contoh 3: Palindrome dengan Mixed Case
```
Input: "Level"
✓ Is palindrome: true (pengecekan case-insensitive)
→ Remove vowels: "Lvl"
Output: "Lvl"
```

---

## 🧪 Test Case

| Input | Is Palindrome? | Aksi | Expected Output |
|-------|----------------|------|-----------------|
| `"racecar"` | ✅ Ya | Remove vowels | `"rccr"` |
| `"hello"` | ❌ Tidak | Reverse | `"olleh"` |
| `"madam"` | ✅ Ya | Remove vowels | `"mdm"` |
| `"world"` | ❌ Tidak | Reverse | `"dlrow"` |
| `"noon"` | ✅ Ya | Remove vowels | `"nn"` |

---

## 💡 Tips Implementasi

1. **Pengecekan Palindrome:** Bandingkan string dengan versi reverse-nya (case-insensitive)
2. **Penghapusan Vowel:** Gunakan regular expression atau method string untuk filter vowel
3. **String Reversal:** Manfaatkan built-in string method atau manipulasi array
4. **Edge Case:** Pertimbangkan empty string, single character, dan special character

---
