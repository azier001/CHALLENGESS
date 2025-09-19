# 🔄 Dokumentasi Fungsi `reverseThoughts`

## 📝 Deskripsi

Fungsi `reverseThoughts` adalah sebuah fungsi JavaScript yang digunakan untuk membalik urutan kata-kata dalam sebuah string **DAN** membalik karakter dalam setiap kata secara bersamaan. Fungsi ini sangat berguna untuk transformasi teks atau mungkin untuk keperluan enkripsi sederhana.

## ⚙️ Cara Kerja

Fungsi ini bekerja dalam 4 langkah utama:
1. **Memecah** string input menjadi array kata-kata
2. **Membalik urutan** kata-kata dalam array
3. **Membalik karakter** dalam setiap kata
4. **Menggabungkan** kembali kata-kata menjadi string tunggal

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
    // Langkah 1: Memecah string input menjadi array kata-kata
    const words = patientThoughts.split(' ');
    
    // Langkah 2: Membalik urutan kata-kata secara manual
    const reversedWords = [];
    for (let i = words.length - 1; i >= 0; i--) {
        reversedWords.push(words[i]);
    }
    
    // Langkah 3: Membalik karakter dalam setiap kata secara manual
    const reversedWordsWithReversedChars = [];
    for (let i = 0; i < reversedWords.length; i++) {
        let reversedWord = '';
        for (let j = reversedWords[i].length - 1; j >= 0; j--) {
            reversedWord += reversedWords[i][j];
        }
        reversedWordsWithReversedChars.push(reversedWord);
    }
    
    // Langkah 4: Menggabungkan kata-kata yang sudah dibalik menjadi string tunggal
    return reversedWordsWithReversedChars.join(' ');
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

## 📊 Tabel Transformasi Karakter

Berikut contoh bagaimana transformasi karakter bekerja:

| Input Original | Urutan Kata Dibalik | Karakter Setiap Kata Dibalik | Output Final |
|----------------|---------------------|-------------------------------|--------------|
| `"Hello World"` | `["World", "Hello"]` | `["dlroW", "olleH"]` | `"dlroW olleH"` |
| `"Java Script"` | `["Script", "Java"]` | `["tpircS", "avaJ"]` | `"tpircS avaJ"` |
| `"ABC DEF"` | `["DEF", "ABC"]` | `["FED", "CBA"]` | `"FED CBA"` |

## 🎯 Kegunaan Praktis

- **Enkripsi sederhana**: Untuk menyembunyikan teks dengan transformasi sederhana
- **Game puzzle**: Untuk membuat teka-teki kata
- **Testing**: Untuk menguji algoritma string manipulation
- **Pembelajaran**: Untuk memahami konsep array dan string manipulation

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** (membedakan huruf besar dan kecil)
- Spasi antar kata akan tetap dipertahankan
- Fungsi hanya bekerja dengan karakter yang dipisahkan oleh spasi tunggal
- Input kosong atau `null` dapat menyebabkan error

## 🔧 Tips Pengembangan

Untuk penggunaan production, pertimbangkan untuk menambahkan:
- Validasi input (null check, type check)
- Handling untuk multiple spaces
- Support untuk karakter khusus dan punctuation
