# Artistic Sign Creation Challenge

## 🎯 Difficulty Level
**Easy**
*Mudah*

## 📝 Description
Create a function named `createArtisticSign` that receives `text` and `decorations` as its parameters.

*Buat sebuah fungsi bernama `createArtisticSign` yang menerima parameter `text` dan `decorations`.*

This function aims to create a beautifully decorated sign by combining the provided text with the specified decorations.

*Fungsi ini bertujuan untuk membuat papan nama yang indah dengan menggabungkan teks yang diberikan dengan dekorasi yang ditentukan.*

## 🎨 Concept
- The `text` parameter represents the main message that will be inscribed on the sign
  
  *Parameter `text` mewakili pesan utama yang akan ditulis di papan nama*

- Imagine the text written in a gorgeous cursive font
  
  *Bayangkan teks ditulis dengan font kursif yang indah*

- The `decorations` parameter contains decorative elements that enhance the sign's appearance
  
  *Parameter `decorations` berisi elemen dekoratif yang mempercantik tampilan papan nama*

## 🔧 Parameters

### `text` (string)
- The main message to be inscribed on the sign
  
  *Pesan utama yang akan ditulis di papan nama*

- This will be the central content of your artistic sign
  
  *Ini akan menjadi konten utama dari papan nama artistik Anda*

### `decorations` (string)
- A string containing only two types of characters: `&` and `*`
  
  *String yang hanya berisi dua jenis karakter: `&` dan `*`*

- **`&` character**: Represents a lovely vine decoration
  - Should be placed **before** the text
  
  *Karakter `&`: Mewakili dekorasi sulur yang indah*
  - *Harus ditempatkan **sebelum** teks*

- **`*` character**: Represents a charming knot decoration
  - Should be placed **after** the text
  
  *Karakter `*`: Mewakili dekorasi simpul yang menarik*
  - *Harus ditempatkan **setelah** teks*

## 📋 Requirements
Your task is to create a function that:

*Tugas Anda adalah membuat fungsi yang:*

1. Takes the two parameters (`text` and `decorations`)
   
   *Menerima dua parameter (`text` dan `decorations`)*

2. Returns a beautifully decorated sign text
   
   *Mengembalikan teks papan nama yang indah dan terdekorasi*

3. Places vine decorations (`&`) on the left side of the text
   
   *Menempatkan dekorasi sulur (`&`) di sisi kiri teks*

4. Places knot decorations (`*`) on the right side of the text
   
   *Menempatkan dekorasi simpul (`*`) di sisi kanan teks*

## 🎯 Expected Output
The function should return a string representing the final decorated sign, with:

*Fungsi harus mengembalikan string yang mewakili papan nama terdekorasi final, dengan:*

- Text surrounded by vine decorations (`&`) on the left
  
  *Teks dikelilingi oleh dekorasi sulur (`&`) di sebelah kiri*

- Text surrounded by knot decorations (`*`) on the right
  
  *Teks dikelilingi oleh dekorasi simpul (`*`) di sebelah kanan*

## 💡 Example
```javascript
// Example usage:
createArtisticSign("Welcome", "&&**")
// Expected output: "&&Welcome**"

createArtisticSign("Hello World", "&*&*")
// Expected output: "&&Hello World**"
```

*Contoh penggunaan dan output yang diharapkan*

## 🚀 Implementation Tips
1. Separate the vine (`&`) and knot (`*`) characters from the decorations string
   
   *Pisahkan karakter sulur (`&`) dan simpul (`*`) dari string dekorasi*

2. Concatenate vine decorations + text + knot decorations
   
   *Gabungkan dekorasi sulur + teks + dekorasi simpul*

3. Return the final decorated string
   
   *Kembalikan string yang sudah terdekorasi*

---

*Happy coding! 🎨✨*
