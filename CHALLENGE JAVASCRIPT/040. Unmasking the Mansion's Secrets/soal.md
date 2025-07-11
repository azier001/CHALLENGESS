# 🏚️ Mengungkap Rahasia Mansion

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang dapat mendekode pesan misterius yang ditemukan di dalam mansion tua dengan menerapkan teknik transformasi khusus.

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `decodeMessage` yang menerima sebuah pesan dan mendekodenya menggunakan algoritma khusus yang melibatkan pembalikan string dan concatenation.

---

## 🔧 Spesifikasi Function

### Nama Function
```
decodeMessage
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `message` | `string` | Pesan asli yang akan didekode |

### Return Value
- **Type:** `string`
- **Deskripsi:** Pesan yang telah didekode setelah transformasi

---

## 📝 Langkah-langkah Implementasi

Ikuti langkah-langkah berikut untuk menyelesaikan challenge:

1. **Reverse Message**
   - Ambil input `message` string
   - Balikkan urutan karakternya

2. **Concatenate String**
   - Gabungkan reversed message dengan original message
   - Urutan: `reversed_message + original_message`

3. **Return Result**
   - Return string yang telah digabungkan

---

## 💡 Contoh

```javascript
// Contoh penggunaan
decodeMessage("hello")
// Langkah 1: Reverse "hello" → "olleh"
// Langkah 2: Concatenate "olleh" + "hello" → "ollehhello"
// Returns: "ollehhello"
```

---

## 🏗️ Template Solusi

```javascript
function decodeMessage(message) {
    // Langkah 1: Reverse message
    
    // Langkah 2: Concatenate reversed + original
    
    // Langkah 3: Return hasilnya
}
```

---

## ✅ Kriteria Keberhasilan

Function Anda harus:
- ✓ Menerima parameter string bernama `message`
- ✓ Membalikkan input string dengan benar
- ✓ Menggabungkan reversed string dengan yang asli
- ✓ Mengembalikan decoded message yang sudah diformat dengan benar

---

## 🔍 Testing Solusi Anda

Pastikan untuk test function Anda dengan berbagai input:
- String karakter tunggal
- String kosong
- String dengan spasi
- String dengan karakter khusus

---

*Semoga berhasil mengungkap rahasia mansion yang tersembunyi! 🔓*
