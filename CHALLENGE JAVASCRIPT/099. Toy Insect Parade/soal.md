# 🐛 Challenge Toy Insect Parade

> **Tingkat Kesulitan:** `Easy` 🟢

## 📋 Gambaran Challenge

Buat sebuah function yang menyenangkan untuk mensimulasikan parade serangga mainan di ruang bermain anak! Tugas Anda adalah membuat function `toyInsectParade` yang menciptakan string berformat yang menggambarkan barisan serangga mainan yang berbaris.

---

## 🎯 Requirements Function

### Function Signature
```javascript
function toyInsectParade(insects, repeatCount)
```

### Parameters
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `insects` | `Array<string>` | Array string yang mewakili berbagai serangga mainan |
| `repeatCount` | `number` | Integer yang menentukan berapa kali setiap serangga muncul dalam parade |

### Return Value
- **String**: Representasi parade yang terformat
- **Kasus khusus**: `"No parade today!"` ketika kondisi tidak terpenuhi

---

## 🎪 Format Parade

Parade mengikuti struktur berikut:
```
Start -> [parade serangga] -> Finish
```

### Rules:
- 🚀 **Start marker**: Selalu dimulai dengan `"Start"`
- 🔄 **Repetition**: Setiap serangga muncul `repeatCount` kali secara berurutan  
- 🏹 **Separator**: Elemen dihubungkan dengan ` -> `
- 🏁 **End marker**: Selalu diakhiri dengan `"Finish"`

---

## ✨ Contoh

### Contoh 1: Parade Normal
**Input:**
```javascript
insects = ["ant", "butterfly", "ladybug"]
repeatCount = 2
```

**Output:**
```javascript
"Start -> ant -> ant -> butterfly -> butterfly -> ladybug -> ladybug -> Finish"
```

### Contoh 2: Single Repetition
**Input:**
```javascript
insects = ["bee", "cricket"]  
repeatCount = 1
```

**Output:**
```javascript
"Start -> bee -> cricket -> Finish"
```

### Contoh 3: Skenario No Parade
**Input:**
```javascript
insects = []           // Array kosong
repeatCount = 2
```
**Output:**
```javascript
"No parade today!"
```

**Input:**
```javascript
insects = ["ant"]      // Repeat count nol atau negatif
repeatCount = 0
```
**Output:**
```javascript
"No parade today!"
```

---

## ⚠️ Edge Cases yang Harus Ditangani

- 📭 **Array insects kosong** (`[]`)
- 🚫 **Repeat count nol** (`repeatCount = 0`)  
- ➖ **Repeat count negatif** (`repeatCount < 0`)

> **Penting:** Semua edge cases harus return `"No parade today!"`

---

## 🎨 Guidelines Implementasi

- ✅ **Batas baris**: Pertahankan solusi dalam **10-19 baris**
- 🧪 **Testing**: Verifikasi semua edge cases bekerja dengan benar
- 🎯 **Fokus**: Code yang bersih dan mudah dibaca yang menangani semua requirements
- 🔍 **Validasi**: Pastikan input validation yang tepat

---

## 🏆 Kriteria Sukses

Function Anda harus:
1. ✅ Menangani skenario parade normal dengan benar
2. ✅ Mengelola semua edge cases yang ditentukan  
3. ✅ Return string yang terformat dengan tepat
4. ✅ Tetap dalam batas baris yang ditentukan
5. ✅ Bersih dan mudah di-maintain

Selamat coding! 🎉
