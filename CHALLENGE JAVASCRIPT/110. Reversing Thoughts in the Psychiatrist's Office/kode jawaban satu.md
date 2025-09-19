# 🔄 Dokumentasi Fungsi `reverseThoughts`

## 📝 Deskripsi

Fungsi `reverseThoughts` adalah sebuah fungsi JavaScript yang digunakan untuk membalik urutan kata-kata dalam sebuah string **DAN** membalik karakter dalam setiap kata secara bersamaan. Fungsi ini menggunakan kombinasi loop manual dan method `map()` untuk transformasi yang efisien. Sangat berguna untuk transformasi teks atau mungkin untuk keperluan enkripsi sederhana.

## ⚙️ Cara Kerja

Fungsi ini bekerja dalam 4 langkah utama:
1. **Memecah** string input menjadi array kata-kata menggunakan `split()`
2. **Membalik urutan** kata-kata dalam array menggunakan loop manual
3. **Membalik karakter** dalam setiap kata menggunakan `map()` dan loop manual
4. **Menggabungkan** kembali kata-kata menjadi string tunggal menggunakan `join()`

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `patientThoughts` | `string` | String input yang berisi kalimat atau pemikiran yang akan dibalik |

## 📤 Return Value

- **Tipe**: `string`
- **Deskripsi**: String yang telah dibalik urutan kata-katanya dan karakter dalam setiap kata

## 💻 Kode Fungsi

```javascript
function reverseThoughts(patientThoughts) {
  // Memecah string input menjadi array kata-kata
  let words = patientThoughts.split(' ');
  
  // Membalik urutan kata-kata dalam array
  let reversedArray = [];
  for (let i = words.length - 1; i >= 0; i--) {
    reversedArray.push(words[i]);
  }
  
  // Membalik karakter dalam setiap kata menggunakan map()
  let reversedWords = reversedArray.map(word => {
    let reversedWord = '';
    for (let i = word.length - 1; i >= 0; i--) {
      reversedWord += word[i];
    }
    return reversedWord;
  });
  
  // Menggabungkan kata-kata yang sudah dibalik menjadi string tunggal
  return reversedWords.join(' ');
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Kalimat Sederhana
```javascript
const input1 = "Saya suka programming";
const output1 = reverseThoughts(input1);
console.log(output1);
// Output: "gnimmargorb akus ayaS"
```

### Contoh 2: Kata Tunggal
```javascript
const input2 = "JavaScript";
const output2 = reverseThoughts(input2);
console.log(output2);
// Output: "tpircSavaJ"
```

### Contoh 3: Kalimat Panjang
```javascript
const input3 = "Belajar coding itu sangat menyenangkan";
const output3 = reverseThoughts(input3);
console.log(output3);
// Output: "nakgnanesynem tagnas uti gnidoc rajaleB"
```

### Contoh 4: Kata dengan Angka
```javascript
const input4 = "Hello World 123";
const output4 = reverseThoughts(input4);
console.log(output4);
// Output: "321 dlroW olleH"
```

## 📊 Tabel Transformasi Karakter

Berikut contoh bagaimana transformasi karakter bekerja step-by-step:

| Input Original | Step 1: Split | Step 2: Reverse Order | Step 3: Reverse Chars | Output Final |
|----------------|---------------|----------------------|----------------------|--------------|
| `"Hello World"` | `["Hello", "World"]` | `["World", "Hello"]` | `["dlroW", "olleH"]` | `"dlroW olleH"` |
| `"Java Script"` | `["Java", "Script"]` | `["Script", "Java"]` | `["tpircS", "avaJ"]` | `"tpircS avaJ"` |
| `"A B C"` | `["A", "B", "C"]` | `["C", "B", "A"]` | `["C", "B", "A"]` | `"C B A"` |

## 🔧 Fitur Teknis

### Method yang Digunakan:
- `split(' ')` - Memecah string berdasarkan spasi
- `push()` - Menambah elemen ke array
- `map()` - Transformasi setiap elemen array
- `join(' ')` - Menggabungkan array menjadi string

### Kompleksitas:
- **Time Complexity**: O(n × m) dimana n = jumlah kata, m = rata-rata panjang kata
- **Space Complexity**: O(n × m) untuk menyimpan array dan string hasil

## 🎯 Kegunaan Praktis

- **Enkripsi sederhana**: Untuk menyembunyikan teks dengan transformasi sederhana
- **Game puzzle**: Untuk membuat teka-teki kata atau cipher games
- **Text processing**: Untuk manipulasi data teks dalam aplikasi
- **Pembelajaran**: Untuk memahami konsep array manipulation dan string processing
- **Data obfuscation**: Menyamarkan data sensitif untuk keperluan testing

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** (membedakan huruf besar dan kecil)
- Spasi antar kata akan tetap dipertahankan (hanya 1 spasi)
- Fungsi hanya bekerja dengan karakter yang dipisahkan oleh spasi tunggal
- Input kosong (`""`) akan menghasilkan string kosong
- Input `null` atau `undefined` akan menyebabkan error

## 🔧 Tips Pengembangan

Untuk penggunaan production yang lebih robust, pertimbangkan untuk menambahkan:

```javascript
function reverseThoughtsEnhanced(patientThoughts) {
  // Validasi input
  if (!patientThoughts || typeof patientThoughts !== 'string') {
    return '';
  }
  
  // Trim whitespace dan handle multiple spaces
  const cleanInput = patientThoughts.trim().replace(/\s+/g, ' ');
  
  // Proses seperti biasa...
  let words = cleanInput.split(' ');
  // ... sisanya sama
}
```

### Improvement yang Bisa Ditambahkan:
- ✅ Validasi input (null check, type check)
- ✅ Handling untuk multiple spaces
- ✅ Trim whitespace di awal dan akhir
- ✅ Support untuk string kosong
- ✅ Error handling yang lebih baik
