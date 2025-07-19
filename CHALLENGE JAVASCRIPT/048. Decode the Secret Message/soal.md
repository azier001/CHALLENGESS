# 🔐 Challenge Decode Secret Message

> **Tingkat Kesulitan:** `Easy`  
> **Kategori:** Cryptography & String Manipulation

---

## 📋 Overview Challenge

Sebagai seorang **cryptography expert**, kamu telah mencegat sebuah encoded message dan memiliki akses ke codebook. Misimu adalah mendecode pesan tersebut menggunakan algoritma spesifik yang melibatkan reverse, split, dan validasi terhadap codebook.

---

## 🎯 Spesifikasi Function

### Function Signature
```javascript
function decodeSecretMessage(encodedMessage, codebook)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `encodedMessage` | `string` | Encoded message yang akan didecode |
| `codebook` | `string[]` | Array string yang merepresentasikan codebook |

### Return Value
- **Type:** `string`
- **Deskripsi:** Decoded message dengan kata-kata yang tidak sah diganti dengan "REDACTED"

---

## 🔧 Algoritma Decoding

Ikuti **6 langkah berurutan** berikut untuk mendecode pesan:

### Langkah 1: Reverse Message
```
Original: "dlrow olleh"
Reversed: "hello world"
```

### Langkah 2: Split ke dalam Words
```
Input: "hello world"
Output: ["hello", "world"]
```

### Langkah 3-4: Validasi terhadap Codebook
Untuk setiap word dalam split message:
- ✅ **Jika ditemukan di codebook** → Simpan word tersebut apa adanya
- ❌ **Jika TIDAK ditemukan di codebook** → Ganti dengan `"REDACTED"`

### Langkah 5: Join Words
```
Processed words: ["hello", "REDACTED"]
Result: "hello REDACTED"
```

### Langkah 6: Return Result
Return string yang telah didecode.

---

## 📝 Catatan Penting

> ⚠️ **Penanganan Punctuation**  
> Encoded message mungkin mengandung tanda baca. Perlakukan words yang dipisahkan spasi sebagai words individual, **terlepas dari punctuation**.

### Contoh Pemisahan Word:
- `"hello, world!"` → `["hello,", "world!"]`
- `"test-case"` → `["test-case"]` (single word)
- `"a b c"` → `["a", "b", "c"]`

---

## 🧪 Example Walkthrough

Mari kita trace melalui contoh lengkap:

```javascript
// Input
encodedMessage = "!dlrow ,olleh"
codebook = ["hello,", "world"]

// Langkah 1: Reverse
// "!dlrow ,olleh" → "hello, world!"

// Langkah 2: Split
// ["hello,", "world!"]

// Langkah 3-4: Check codebook
// "hello," ✅ (ditemukan di codebook)
// "world!" ❌ (tidak ditemukan di codebook) → "REDACTED"

// Langkah 5-6: Join dan return
// Result: "hello, REDACTED"
```

---

## 🚀 Tips Implementasi

- Gunakan built-in string methods untuk reverse dan split
- Pertimbangkan menggunakan array methods untuk lookup codebook yang efisien
- Ingat untuk handle edge cases (empty strings, single words, dll.)
- Test dengan berbagai skenario punctuation

---

## 📊 Analisis Complexity

- **Time Complexity:** O(n + m×k) dimana n = panjang message, m = jumlah words, k = ukuran codebook
- **Space Complexity:** O(n) untuk menyimpan reversed dan split message

---

*Selamat coding! 🎉*
