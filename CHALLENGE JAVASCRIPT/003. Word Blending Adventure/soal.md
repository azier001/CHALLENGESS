# 🎯 Word Blend Adventure
## Tantangan Pemrograman - Level Mudah

---

## 📋 **Deskripsi Tantangan**
Create a function named `blendWords` that receives `word1` and `word2` as parameters.

*Buat sebuah fungsi bernama `blendWords` yang menerima parameter `word1` dan `word2`.*

---

## 🔧 **Cara Kerja Fungsi**
This function concatenates the two words, omitting one of the duplicate letters if the last letter of word1 and the first letter of word2 are the same.

*Fungsi ini menggabungkan dua kata dengan menghilangkan salah satu huruf duplikat jika huruf terakhir dari kata1 sama dengan huruf pertama dari kata2.*

---

## 📝 **Aturan yang Harus Ditangani**

### 🔄 **Kasus 1: Huruf Sama**
If the last letter of word1 and the first letter of word2 are the same, omit one of the duplicate letters.

*Jika huruf terakhir dari kata1 dan huruf pertama dari kata2 sama, hilangkan salah satu huruf duplikat.*

**Contoh:**
- `word1 = "hello"`, `word2 = "orange"` → `"helloorange"` (tidak ada duplikat)
- `word1 = "car"`, `word2 = "radio"` → `"carradio"` (huruf 'r' duplikat, hilangkan satu)

### 📭 **Kasus 2: Kata Kosong**
If either word1 or word2 is empty, return the non-empty string.

*Jika salah satu dari kata1 atau kata2 kosong, kembalikan string yang tidak kosong.*

**Contoh:**
- `word1 = ""`, `word2 = "world"` → `"world"`
- `word1 = "hello"`, `word2 = ""` → `"hello"`

### 🚫 **Kasus 3: Kedua Kata Kosong**
If both are empty, return an empty string.

*Jika kedua kata kosong, kembalikan string kosong.*

**Contoh:**
- `word1 = ""`, `word2 = ""` → `""`

---

## 📊 **Parameter dan Return Value**

### 📥 **Parameter:**
| Parameter | Tipe | Deskripsi (English) | Deskripsi (Indonesia) |
|-----------|------|---------------------|----------------------|
| `word1` | string | The first word | Kata pertama |
| `word2` | string | The second word | Kata kedua |

### 📤 **Return Value:**
Returns a string, the result of blending word1 and word2.

*Mengembalikan sebuah string, hasil penggabungan word1 dan word2.*



---

## 🧪 **Test Cases**

| Input | Output | Penjelasan |
|-------|--------|------------|
| `blendWords("sun", "noon")` | `"sunoon"` | 'n' duplikat, hilangkan satu |
| `blendWords("hello", "world")` | `"helloworld"` | Tidak ada duplikat |
| `blendWords("", "test")` | `"test"` | Kata pertama kosong |
| `blendWords("code", "")` | `"code"` | Kata kedua kosong |
| `blendWords("", "")` | `""` | Kedua kata kosong |

---

## 🎯 **Tips Sukses**
- ✅ Periksa kondisi string kosong terlebih dahulu
- ✅ Gunakan indexing untuk mengakses huruf pertama dan terakhir
- ✅ Gunakan `slice()` untuk memotong string
- ✅ Test semua kasus edge case

**Selamat mengoding! 🚀**
