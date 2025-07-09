# 🔍 Tantangan Count Substring Occurrences

## 📊 Tingkat Kesulitan
**Easy**

## 🎯 Tujuan
Buat sebuah function bernama `countSubstringOccurrences` yang menganalisis pola string dan menghitung kemunculan substring tertentu.

## 📝 Persyaratan Function

### Function Signature
```javascript
function countSubstringOccurrences(str, substr, maxLen)
```

### Parameter
- **`str`** (string): String utama yang akan dicari
- **`substr`** (string): Substring yang harus ada dalam hasil
- **`maxLen`** (number): Panjang maksimal yang diizinkan untuk substring yang ditemukan

### Return Value
- **Object**: Key adalah substring yang ditemukan, value adalah jumlah kemunculan
- **Empty Object**: Jika `substr` kosong atau `maxLen` adalah 0

## 🔧 Spesifikasi Function

Function harus:

1. **Menemukan substring unik** dari `str` yang memenuhi SEMUA kriteria:
   - ✅ Mengandung `substr` sebagai substring
   - ✅ Panjang ≤ `maxLen`
   - ✅ Tidak mengandung digit (0-9)

2. **Menghitung kemunculan** setiap substring yang valid dalam string asli

3. **Mengembalikan data terstruktur** sebagai object dengan pasangan substring-count

## 📋 Edge Cases

- Jika `substr` adalah **string kosong** → return `{}`
- Jika `maxLen` adalah **0** → return `{}`
- Substring yang mengandung **digit** akan dikecualikan

## 💡 Contoh

### Input
```javascript
str = "abcabc"
substr = "ab"
maxLen = 4
```

### Output
```javascript
{
  "ab": 2,
  "abc": 2,
  "abca": 1,
  "abcab": 1
}
```

### Penjelasan Step-by-Step

| Substring | Mengandung "ab"? | Panjang ≤ 4? | Tidak Ada Digit? | Jumlah dalam "abcabc" |
|-----------|------------------|-------------|------------------|----------------------|
| `"ab"`    | ✅ Ya            | ✅ Ya (2)   | ✅ Ya            | **2**                |
| `"abc"`   | ✅ Ya            | ✅ Ya (3)   | ✅ Ya            | **2**                |
| `"abca"`  | ✅ Ya            | ✅ Ya (4)   | ✅ Ya            | **1**                |
| `"abcab"` | ✅ Ya            | ✅ Ya (4)   | ✅ Ya            | **1**                |
| `"abcabc"`| ✅ Ya            | ❌ Tidak (6)| ✅ Ya            | **Dikecualikan**     |

## 🎨 Pertimbangan Penting

- **Pattern Recognition**: Identifikasi semua substring yang mungkin dengan efisien
- **String Matching**: Pastikan `substr` ada dalam setiap hasil
- **Length Validation**: Patuhi batasan `maxLen`
- **Character Filtering**: Kecualikan substring yang mengandung digit
- **Counting Logic**: Hitung kemunculan yang overlap dengan akurat

## 🚀 Kriteria Sukses

Solusi Anda harus:
- Menangani semua edge cases dengan benar
- Mengembalikan jumlah kemunculan yang akurat
- Mempertahankan performa yang optimal
- Mengikuti function signature yang tepat
- Lulus semua skenario test

---

*Semoga berhasil dengan implementasinya! 🎯*
