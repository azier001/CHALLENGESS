# 🔐 Tantangan Decipher Encrypted Message

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`  
**Nama Function:** `decipherMessage`

---

## 🎯 Tujuan

Buat sebuah function yang mendecrypt pesan terenkripsi menggunakan cipher key array. Cipher key berisi indeks yang menentukan urutan karakter yang harus diekstrak dari encrypted message.

## 📝 Spesifikasi Function

### Function Signature
```javascript
function decipherMessage(encryptedMessage, cipherKey)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `encryptedMessage` | `string` | Pesan terenkripsi yang akan didecrypt |
| `cipherKey` | `array` | Array berisi indeks yang menunjukkan urutan ekstraksi karakter |

### Return Value
- **Type:** `string`
- **Deskripsi:** Pesan yang telah didecrypt

---

## 🔧 Cara Kerja

1. **Ekstrak karakter** dari `encryptedMessage` berdasarkan indeks dalam `cipherKey`
2. **Pindahkan setiap karakter** ke awal pesan yang sudah didecrypt
3. **Ulangi proses** hingga semua karakter telah diproses
4. **Return** pesan final yang sudah didecrypt

### Contoh Visual
```
Encrypted Message: "hello"
Cipher Key:        [4, 0, 3, 1, 2]

Step 1: Ekstrak indeks 4 ('o') → "o"
Step 2: Ekstrak indeks 0 ('h') → "ho" 
Step 3: Ekstrak indeks 3 ('l') → "lho"
Step 4: Ekstrak indeks 1 ('e') → "elho"
Step 5: Ekstrak indeks 2 ('l') → "lelho"

Hasil: "lelho"
```

---

## ⚠️ Batasan Penting

> **Character Set**
> - `encryptedMessage` hanya berisi **huruf kecil saja**

> **Properties Array**
> - `cipherKey` array berisi **semua indeks** dari `encryptedMessage`
> - Indeks diberikan dalam **urutan acak**
> - Panjang `cipherKey` **selalu sama** dengan panjang `encryptedMessage`

---

## 💡 Tips Implementasi

- Pertimbangkan menggunakan method manipulasi array
- Lacak karakter mana yang sudah diproses
- Pikirkan urutan operasi saat membangun result
- Ingat bahwa setiap karakter dipindah ke "awal" dari result saat ini

---

## 🧪 Test Cases

Pertimbangkan untuk testing dengan:
- Pesan dengan satu karakter
- Pesan dengan karakter berulang
- Pengaturan cipher key yang berbeda
- Edge cases dengan string kosong (jika berlaku)

---

*Semoga berhasil menyelesaikan tantangan cipher ini! 🚀*
