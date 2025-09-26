# 🦅 Soar Like an Eagle

## 📋 Informasi Challenge

| **Tingkat Kesulitan** | **Nama Function** | **Parameter** |
|----------------------|-------------------|---------------|
| Easy | `soarLikeEagle` | `string` str, `number` n |

## 🎯 Deskripsi Soal

Buat sebuah function yang mengubah string dengan mengulangi setiap karakter berdasarkan aturan khusus:

- **Karakter biasa**: Ulangi `n` kali
- **Vowel (a, e, i, o, u)**: Ulangi `n + 1` kali
- **Edge case**: Jika `n` bernilai 0 atau negatif, return string kosong

## 🔍 Function Signature

```javascript
function soarLikeEagle(str, n) {
    // Implementasi kode di sini
}
```

## 📝 Contoh

### Contoh 1
```javascript
soarLikeEagle("Hi", 2)
// Expected output: "HHiii"
```
**Penjelasan:**
- `H` (konsonan) → diulangi 2 kali → `HH`
- `i` (vowel) → diulangi 2+1=3 kali → `iii`

### Contoh 2
```javascript
soarLikeEagle("Hello", 3)
// Expected output: "HHHeeeelllllooo"
```
**Penjelasan:**
- `H` (konsonan) → diulangi 3 kali → `HHH`
- `e` (vowel) → diulangi 3+1=4 kali → `eeee`
- `l` (konsonan) → diulangi 3 kali → `lll`
- `l` (konsonan) → diulangi 3 kali → `lll`
- `o` (vowel) → diulangi 3+1=4 kali → `oooo`

### Contoh 3
```javascript
soarLikeEagle("Bye", 0)
// Expected output: ""
```
**Penjelasan:**
- Karena `n` bernilai 0, langsung return string kosong

## ✅ Requirements

- Handle uppercase dan lowercase vowel
- Return string kosong untuk `n ≤ 0`
- Proses setiap karakter secara berurutan
- Pertahankan case karakter asli

## 🧠 Key Concepts

- **Manipulasi string**
- **Logic kondisional**
- **Klasifikasi karakter**
- **Iterasi loop**
- **Penanganan edge case**

## 💡 Hints

- Pertimbangkan menggunakan method `includes()` untuk mengecek vowel
- Ingat untuk handle uppercase dan lowercase vowel
- Gunakan method pengulangan string seperti `repeat()`
- Jangan lupa validasi edge case

---

*Selamat coding! 🚀*
