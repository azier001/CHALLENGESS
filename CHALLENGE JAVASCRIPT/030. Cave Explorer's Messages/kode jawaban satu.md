# 🕳️ Dokumentasi Fungsi `exploreCave`

## 📋 Deskripsi Fungsi

Fungsi `exploreCave` adalah sebuah fungsi JavaScript yang berperan seperti gua dengan efek gema. Ketika dua pesan yang sama dimasukkan ke dalam "gua", fungsi ini akan menghasilkan efek gema (echo). Jika pesannya berbeda, fungsi akan menggabungkan kedua pesan tersebut dengan penghubung "&".

---

## 🔧 Sintaks

```javascript
exploreCave(message1, message2)
```

---

## 📝 Parameter

| Parameter | Tipe Data | Wajib | Deskripsi |
|-----------|-----------|-------|-----------|
| `message1` | String | ✅ | Pesan pertama yang akan dimasukkan ke dalam gua |
| `message2` | String | ✅ | Pesan kedua yang akan dimasukkan ke dalam gua |

---

## 🎯 Return Value

| Kondisi | Return Value | Contoh |
|---------|--------------|--------|
| `message1 === message2` | `"Echo: " + message1` | `"Echo: Hello"` |
| `message1 !== message2` | `message1 + " & " + message2` | `"Hello & World"` |

---

## 💻 Source Code

```javascript
function exploreCave(message1, message2) {
  if (message1 === message2) {
    return "Echo: " + message1;
  } else {
    return message1 + " & " + message2;
  }
}
```

---

## 📚 Contoh Penggunaan

### 🔊 Contoh 1: Efek Gema (Echo)
```javascript
// Ketika kedua pesan sama
let result1 = exploreCave("Hello", "Hello");
console.log(result1); 
// Output: "Echo: Hello"

let result2 = exploreCave("JavaScript", "JavaScript");
console.log(result2);
// Output: "Echo: JavaScript"
```

### 🔗 Contoh 2: Penggabungan Pesan
```javascript
// Ketika kedua pesan berbeda
let result3 = exploreCave("Hello", "World");
console.log(result3);
// Output: "Hello & World"

let result4 = exploreCave("Coding", "Fun");
console.log(result4);
// Output: "Coding & Fun"
```

### 🎲 Contoh 3: Dengan Berbagai Tipe Input
```javascript
// Dengan angka (akan dikonversi ke string)
let result5 = exploreCave("123", "123");
console.log(result5);
// Output: "Echo: 123"

// Dengan string kosong
let result6 = exploreCave("", "Hello");
console.log(result6);
// Output: " & Hello"
```

---

## 🎨 Penjelasan Logic

Fungsi ini menggunakan konsep sederhana:

1. **Perbandingan Kesamaan**: Menggunakan operator `===` untuk membandingkan kedua parameter
2. **Conditional Logic**: 
   - Jika kedua pesan **sama** → menghasilkan efek gema dengan prefix "Echo: "
   - Jika kedua pesan **berbeda** → menggabungkan dengan tanda "&"
3. **String Concatenation**: Menggunakan operator `+` untuk menggabungkan string

---

## ⚠️ Catatan Penting

- Fungsi ini melakukan perbandingan **strict equality** (`===`)
- Huruf besar dan kecil dianggap berbeda (`"Hello" !== "hello"`)
- Spasi di awal/akhir juga mempengaruhi hasil (`"Hello" !== "Hello "`)
- Parameter yang bukan string akan dikonversi secara otomatis

---

## 🚀 Tips Penggunaan

- Gunakan fungsi ini untuk membuat sistem pesan interaktif
- Cocok untuk game text-based yang membutuhkan efek gema
- Bisa dikembangkan menjadi chatbot sederhana
- Ideal untuk pembelajaran konsep conditional statements

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi `exploreCave` dengan penjelasan yang mudah dipahami.* 🎓
