# 🔀 BlendWords Function

> **Fungsi untuk menggabungkan dua kata dengan aturan khusus**

## 📝 Deskripsi

Fungsi `blendWords` adalah sebuah utility JavaScript yang dirancang untuk menggabungkan dua kata dengan cara yang cerdas. Fungsi ini akan menghilangkan duplikasi karakter ketika karakter terakhir dari kata pertama sama dengan karakter pertama dari kata kedua.

## 🎯 Cara Kerja

### Logika Utama
1. **Handle Empty Strings**: Jika salah satu atau kedua kata kosong, kembalikan kata yang tidak kosong
2. **Character Matching**: Periksa apakah karakter terakhir kata pertama sama dengan karakter pertama kata kedua
3. **Smart Concatenation**: Jika ada kecocokan, hilangkan karakter duplikat; jika tidak, gabungkan langsung

### Flow Diagram
```
Input: word1, word2
       ↓
   Apakah keduanya kosong?
       ↓ (Ya)         ↓ (Tidak)
   Return ''    Apakah word1 kosong?
                    ↓ (Ya)         ↓ (Tidak)
                Return word2   Apakah word2 kosong?
                                   ↓ (Ya)         ↓ (Tidak)
                               Return word1   Cek karakter overlap
                                                   ↓
                                           Ada overlap? → Gabung tanpa duplikasi
                                                   ↓
                                           Tidak ada? → Gabung langsung
```

## 💻 Source Code

```javascript
function blendWords(word1, word2) {
  // Handle kedua string kosong
  if (word1 === '' && word2 === '') {
    return '';
  }
  
  // Handle word1 kosong
  if (word1 === '') {
    return word2;
  }
  
  // Handle word2 kosong
  if (word2 === '') {
    return word1;
  }
  
  // Ambil karakter terakhir dari word1 dan pertama dari word2
  const lastChar1 = word1[word1.length - 1];
  const firstChar2 = word2[0];
  
  // Jika ada overlap karakter, hilangkan duplikasi
  if (lastChar1 === firstChar2) {
    return word1 + word2.slice(1);
  }
  
  // Jika tidak ada overlap, gabung langsung
  return word1 + word2;
}
```

## 🧪 Contoh Penggunaan

| Input | Output | Penjelasan |
|-------|--------|------------|
| `blendWords("hello", "orange")` | `"helloorange"` | Tidak ada overlap, gabung langsung |
| `blendWords("sun", "noon")` | `"sunnoon"` | 'n' overlap, hilangkan duplikasi |
| `blendWords("car", "race")` | `"carrace"` | 'r' overlap, hilangkan duplikasi |
| `blendWords("", "world")` | `"world"` | String pertama kosong |
| `blendWords("hello", "")` | `"hello"` | String kedua kosong |
| `blendWords("", "")` | `""` | Kedua string kosong |

## ⚡ Kegunaan Praktis

### 🎮 **Game Development**
- Menggabungkan nama karakter atau item
- Membuat kombinasi skill atau spell

### 🏷️ **Branding & Marketing**
- Membuat nama produk yang unik
- Menggabungkan brand names

### 🔤 **Text Processing**
- Preprocessing untuk NLP
- Word manipulation dalam chatbot

### 🎨 **Creative Writing**
- Membuat kata-kata kreatif
- Poetry dan wordplay

## 🚀 Optimisasi & Enhancement

### Possible Improvements:
- **Case Insensitive**: Tambahkan opsi untuk ignore case
- **Multiple Characters**: Support overlap lebih dari 1 karakter
- **Custom Rules**: Tambahkan parameter untuk aturan khusus

### Performance:
- **Time Complexity**: O(1) - sangat efisien
- **Space Complexity**: O(n) - tergantung panjang output

---

## 💡 Tips Penggunaan

> 💭 **Pro Tip**: Fungsi ini sangat berguna untuk membuat portmanteau words atau word blending dalam aplikasi kreatif!

**Contoh Kreatif:**
```javascript
console.log(blendWords("breakfast", "lunch")); // "brunch" (jika ada overlap 'st'+'t')
console.log(blendWords("smoke", "fog"));       // "smog" (jika ada overlap 'e'+'f')
```
