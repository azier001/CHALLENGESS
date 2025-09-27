# 🌻 Temukan Postcard di Garden Party yang Berantakan

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Buat sebuah function bernama `findReversePostcard` yang membantu menemukan postcard tertentu dalam tumpukan yang secara tidak sengaja tertumpuk dalam urutan terbalik setelah garden party yang kacau.

---

## 🎯 Deskripsi Challenge

Bayangkan kamu sedang berada di garden party yang berantakan dimana para tamu telah bertukar postcard yang aneh. Setelah pesta berakhir, postcard-postcard tersebut secara tidak sengaja tertumpuk dalam urutan terbalik, menciptakan kekacauan! Misi kamu adalah membantu menemukan postcard tertentu dalam tumpukan yang berantakan ini.

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
findReversePostcard(postcards, message)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `postcards` | `Array<String>` | Sebuah array string, dimana setiap string mewakili pesan pada sebuah postcard |
| `message` | `String` | Pesan spesifik yang akan dicari di antara postcard-postcard |

### Return Value
- **Type:** `Number`
- **Deskripsi:** Index dari postcard yang ditemukan dalam array yang sudah dibalik, atau `-1` jika pesan tidak ditemukan

---

## 📝 Langkah-langkah Algorithm

Function harus melakukan operasi berikut secara berurutan:

1. **🔄 Reverse Array**
   - Balikkan urutan array postcards untuk mensimulasikan kekacauan dari pesta

2. **🔍 Cari Message**
   - Cari pesan yang ditentukan dalam array postcards yang sudah dibalik

3. **📍 Return Index**
   - Jika message ditemukan → return index postcard dalam array yang sudah dibalik
   - Jika message tidak ditemukan → return `-1`

---

## 💡 Contoh Penggunaan

```javascript
// Contoh postcards dari garden party
const postcards = [
    "Hello from the rose garden!",
    "The sunflowers are blooming beautifully",
    "Thanks for the lovely tea party",
    "See you next spring!"
];

const targetMessage = "Thanks for the lovely tea party";

// Function call
const result = findReversePostcard(postcards, targetMessage);

// Expected behavior:
// 1. Reversed array: ["See you next spring!", "Thanks for the lovely tea party", "The sunflowers are blooming beautifully", "Hello from the rose garden!"]
// 2. Search for "Thanks for the lovely tea party"
// 3. Found at index 1 in the reversed array
// 4. Return: 1
```

---

## ⚡ Poin Penting yang Perlu Diingat

- 🔄 Selalu reverse array **terlebih dahulu** sebelum searching
- 📍 Return index dari **reversed array**, bukan array asli
- ❌ Return `-1` ketika message tidak ditemukan
- 🎯 Diperlukan exact string matching

---

## 🏷️ Tags

`Array Manipulation` • `String Search` • `Index Finding` • `Algorithm` • `Easy Challenge`
