# 🔄 Dokumentasi Fungsi `reverseSpecimenWords`

## 📋 Deskripsi Fungsi

Fungsi `reverseSpecimenWords` adalah sebuah fungsi JavaScript yang membalik urutan semua karakter dalam setiap kata dari sebuah kalimat. Fungsi ini memproses setiap kata secara terpisah dan membalik seluruh karakternya, termasuk huruf, angka, dan tanda baca.

## 🎯 Kegunaan

- Membalik kata-kata dalam kalimat untuk keperluan enkripsi sederhana
- Mengolah teks untuk puzzle atau permainan kata
- Dapat digunakan untuk obfuskasi teks sederhana
- Berguna untuk manipulasi string dalam aplikasi text processing

## 📥 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `observation` | String | ✅ | Kalimat atau teks yang akan diproses. Berisi kata-kata yang akan dibalik urutannya |

## 📤 Return Value

- **Tipe**: `String`
- **Deskripsi**: Kalimat dengan setiap kata yang semua karakternya sudah dibalik urutannya

## 🔤 Karakter yang Diproses

| Jenis Karakter | Perlakuan | Contoh |
|----------------|-----------|--------|
| Huruf (a-z, A-Z) | Dibalik urutannya | `hello` → `olleh` |
| Angka (0-9) | Dibalik urutannya | `123` → `321` |
| Tanda Baca | Dibalik urutannya | `hello!` → `!olleh` |
| Semua Karakter | Dibalik dalam kata | `word.` → `.drow` |

## 💻 Kode Fungsi

```javascript
function reverseSpecimenWords(observation) {
  // Pisahkan kalimat menjadi array kata-kata berdasarkan spasi
  return observation.split(' ').map(word => {
    // Balik urutan semua karakter dalam setiap kata
    return word.split('').reverse().join('');
  }).join(' '); // Gabungkan kembali kata-kata dengan spasi
}
```

## 🧪 Contoh Penggunaan

### Contoh 1: Kalimat Sederhana
```javascript
const input = "Hello world";
const output = reverseSpecimenWords(input);
console.log(output); // Output: "olleH dlrow"
```

### Contoh 2: Kalimat dengan Tanda Baca
```javascript
const input = "Hello, world!";
const output = reverseSpecimenWords(input);
console.log(output); // Output: ",olleH !dlrow"
```

### Contoh 3: Kalimat dengan Angka
```javascript
const input = "Test123 code456";
const output = reverseSpecimenWords(input);
console.log(output); // Output: "321tseT 654edoc"
```

### Contoh 4: Kalimat Kompleks
```javascript
const input = "JavaScript is fun! Let's code.";
const output = reverseSpecimenWords(input);
console.log(output); // Output: "tpircSavaJ si !nuf s'teL .edoc"
```

## 🔍 Contoh Output Detail

| Input | Output | Penjelasan |
|-------|--------|------------|
| `"abc"` | `"cba"` | Huruf sederhana dibalik |
| `"a1b2c3"` | `"3c2b1a"` | Huruf dan angka dibalik bersama |
| `"hello!"` | `"!olleh"` | Tanda seru pindah ke awal |
| `"hi, there"` | `"ih, ereht"` | Koma pindah ke awal kata pertama |
| `"test-123"` | `"321-tset"` | Tanda hubung pindah ke tengah |
| `"word."` | `".drow"` | Titik pindah ke awal kata |

## ⚠️ Catatan Penting

1. **Spasi**: Fungsi ini mempertahankan spasi antar kata sebagai pemisah
2. **Tanda Baca**: Semua tanda baca ikut dibalik dalam kata, tidak tetap di posisi semula
3. **Case Sensitivity**: Huruf besar dan kecil dibalik sesuai urutannya
4. **String Kosong**: Jika input kosong, akan mengembalikan string kosong
5. **Sederhana**: Fungsi ini lebih sederhana karena membalik semua karakter tanpa pengecualian

## 🚀 Tips Penggunaan

- Cocok untuk membuat puzzle kata sederhana
- Dapat digunakan sebagai langkah awal enkripsi teks ringan
- Berguna untuk testing dan debugging aplikasi yang memproses teks
- Lebih mudah dipahami karena logika yang straightforward
- Dapat dikombinasikan dengan fungsi lain untuk manipulasi string yang lebih kompleks

## 🔧 Cara Kerja Fungsi

1. **Split**: Memisahkan kalimat input menjadi array kata-kata menggunakan spasi sebagai delimiter
2. **Map**: Memproses setiap kata dalam array dengan:
   - Memecah kata menjadi array karakter
   - Membalik urutan array karakter
   - Menggabungkan kembali karakter menjadi string
3. **Join**: Menggabungkan semua kata yang sudah dibalik menjadi satu kalimat dengan spasi sebagai pemisah

## 🆚 Perbedaan dengan Fungsi Sejenis

Fungsi ini berbeda dengan fungsi reverse yang hanya mempertahankan posisi tanda baca. Fungsi `reverseSpecimenWords` ini membalik **semua karakter** dalam setiap kata, sehingga hasilnya lebih sederhana dan konsisten.
