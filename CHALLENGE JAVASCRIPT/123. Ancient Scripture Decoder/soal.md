# 📜 Ancient Scripture Decoder

## Gambaran Umum Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Dekode pesan tersembunyi dengan menggabungkan kata-kata dari dua baris naskah kuno!

---

## 🎯 Tujuan

Buat sebuah function bernama `decodeScripture` yang mengungkap pesan rahasia dengan menggabungkan kata-kata dari dua baris teks yang berbeda.

### Cara Kerja

Decoder mengekstrak **dua kata terakhir** dari baris tambahan dan menambahkannya ke baris asli, membentuk pesan yang sudah terdekode.

---

## 📋 Spesifikasi Function

### Nama Function
```
decodeScripture
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `originalLine` | `array of strings` | Kata-kata dari baris naskah asli |
| `additionalLine` | `array of strings` | Kata-kata dari baris tambahan (dua kata terakhir akan diekstrak) |

### Return Value

- **Tipe:** `array of strings`
- **Deskripsi:** Pesan yang sudah terdekode menggabungkan kata-kata dari kedua baris

---

## 🔍 Proses Decoding

1. **Mulai** dengan array `originalLine`
2. **Ekstrak** dua kata terakhir dari `additionalLine`
3. **Tambahkan** kedua kata tersebut ke `originalLine`
4. **Return** array gabungan sebagai pesan yang sudah terdekode

---

## 💡 Contoh

```javascript
// Input
originalLine = ["The", "ancient", "wisdom"]
additionalLine = ["is", "hidden", "within", "the", "scrolls"]

// Proses
// Dua kata terakhir dari additionalLine: ["the", "scrolls"]

// Output
decodeScripture(originalLine, additionalLine)
// Returns: ["The", "ancient", "wisdom", "the", "scrolls"]
```

---

## ✅ Checklist Requirements

- [ ] Function harus diberi nama `decodeScripture`
- [ ] Menerima dua parameter: `originalLine` dan `additionalLine`
- [ ] Ekstrak tepat **dua kata terakhir** dari `additionalLine`
- [ ] Tambahkan kata-kata yang diekstrak ke `originalLine`
- [ ] Return hasil sebagai array of strings

---

## 🚀 Memulai

Implementasikan function mengikuti spesifikasi di atas. Ingat untuk menangani edge cases dan pastikan solusi Anda bekerja dengan berbagai ukuran input!

**Semangat, decoder! 🔓**
