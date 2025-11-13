# 📚 Bookstore Anagram Display Groups

## Ringkasan Challenge

**Tingkat Kesulitan:** `Medium` 🟡

---

## 🎯 Tujuan

Buat sebuah fungsi `groupAnagramTitles` yang mengorganisir judul buku ke dalam kelompok berdasarkan hubungan anagram. Ini membantu Anda membuat tampilan kreatif di toko buku dengan mengelompokkan buku-buku yang memiliki huruf yang sama!

---

## 📋 Spesifikasi Fungsi

### Function Signature

```javascript
function groupAnagramTitles(bookTitles)
```

### Parameters

- **`bookTitles`** *(array)*  
  Array dari string judul buku yang akan dikelompokkan berdasarkan hubungan anagram.

### Returns

- **Array 2D** dari kelompok anagram  
  - Setiap sub-array berisi judul buku yang merupakan anagram satu sama lain
  - Format judul asli tetap dipertahankan
  - Format: `[["Title One", "Title Two"], ["Single Title"], ["Another", "Group"]]`

---

## 🔍 Logika & Persyaratan

Fungsi harus mengikuti langkah-langkah berikut:

1. **Buat Signature**  
   Untuk setiap judul, buat signature unik dengan:
   - Mengkonversi ke huruf dengan case yang sama (abaikan perbedaan case)
   - Menghilangkan spasi
   - Mengurutkan semua huruf secara alfabetis

2. **Kelompokkan berdasarkan Signature**  
   - Judul dengan signature identik adalah anagram
   - Tempatkan mereka bersama dalam sub-array yang sama

3. **Pertahankan Format Asli**  
   - Jaga kapitalisasi dan spasi asli dari judul
   - Jangan memodifikasi string input

4. **Tangani Judul Tunggal**  
   - Judul tanpa anagram tetap harus muncul dalam sub-array mereka sendiri
   - Setiap judul harus disertakan dalam output

---

## 💡 Contoh Skenario

### Contoh 1: Pengelompokan Anagram Dasar

**Input:**
```javascript
["Listen", "Silent", "Hello", "World"]
```

**Output:**
```javascript
[
  ["Listen", "Silent"],
  ["Hello"],
  ["World"]
]
```

---

### Contoh 2: Multiple Groups

**Input:**
```javascript
["The Eyes", "They See", "Act", "Cat", "Book"]
```

**Output:**
```javascript
[
  ["The Eyes", "They See"],
  ["Act", "Cat"],
  ["Book"]
]
```

---

## 🎨 Use Case

Sempurna untuk membuat display toko buku yang menarik dimana buku-buku dengan judul anagram dikelompokkan bersama, menambahkan elemen playful dan intelektual pada organisasi inventori Anda!

---

## ⚡ Poin-Poin Penting

- ✅ Perbandingan case-insensitive
- ✅ Abaikan spasi saat membandingkan
- ✅ Pertahankan format judul asli di output
- ✅ Setiap judul muncul tepat satu kali
- ✅ Judul tunggal mendapat sub-array sendiri

---

**Selamat Coding!** 🚀
