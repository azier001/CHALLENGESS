# 🎉 Guest Name Formatter

## 📝 Ringkasan Tantangan

**Tingkat Kesulitan:** 🟢 Mudah

Buatlah fungsi bernama `formatGuestNames` yang memformat daftar nama tamu menjadi string sapaan yang ramah dan tata bahasa yang benar.

---

## 📥 Masukan

Sebuah **string** yang berisi daftar nama tamu, dipisahkan dengan koma.

---

## 📤 Keluaran

Sebuah **string yang diformat** dengan benar untuk menyapa para tamu, tergantung pada jumlah nama yang diberikan.

---

## 🧠 Aturan Pemformatan

| Jumlah Nama     | Contoh Format |
|-----------------|----------------|
| 1 Nama          | `Alice` → `Alice` |
| 2 Nama          | `Alice,Bob` → `Alice dan Bob` |
| 3+ Nama         | `Alice,Charlie,Bob` → `Alice, Charlie, dan Bob` |

---

## 🛠️ Langkah Penyelesaian

1. **Pisahkan** string menggunakan `split(",")`.
2. **Cek panjang** array hasil split:
   - Jika **1**, kembalikan nama tersebut apa adanya.
   - Jika **2**, gabungkan dengan `" dan "`.
   - Jika **lebih dari 2**:
     - Gabungkan semua kecuali nama terakhir dengan `", "`.
     - Tambahkan `", dan "` diikuti dengan nama terakhir.
3. **Kembalikan** string yang sudah diformat.

---

## 📦 Parameter

- `guestNames` (`string`): String nama-nama tamu yang dipisahkan dengan koma.

## ✅ Keluaran

- `string`: String sapaan yang sudah diformat.

---

## 🔍 Contoh

```javascript
formatGuestNames("Alice") 
// Output: "Alice"

formatGuestNames("Alice,Bob") 
// Output: "Alice dan Bob"

formatGuestNames("Alice,Charlie,Bob") 
// Output: "Alice, Charlie, dan Bob"
```

---

Selamat Coding! 🎊
