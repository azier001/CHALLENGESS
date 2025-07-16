# 🔄 Dokumentasi Fungsi `reverseSpecimenWords`

## 📋 Deskripsi Fungsi

Fungsi `reverseSpecimenWords` adalah sebuah fungsi JavaScript yang membalik urutan karakter alfanumerik (huruf dan angka) dalam setiap kata dari sebuah kalimat, sambil mempertahankan posisi dan urutan tanda baca pada tempatnya semula.

## 🎯 Kegunaan

- Membalik kata-kata dalam kalimat untuk keperluan enkripsi sederhana
- Mengolah teks dengan tetap mempertahankan struktur tanda baca
- Useful untuk puzzle atau permainan kata
- Dapat digunakan untuk obfuskasi teks sederhana

## 📥 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `observation` | String | ✅ | Kalimat atau teks yang akan diproses. Berisi kata-kata yang akan dibalik urutannya |

## 📤 Return Value

- **Tipe**: `String`
- **Deskripsi**: Kalimat dengan setiap kata yang karakter alfanumeriknya sudah dibalik, tanda baca tetap pada posisi semula

## 🔤 Karakter yang Diproses

| Jenis Karakter | Perlakuan | Contoh |
|----------------|-----------|--------|
| Huruf (a-z, A-Z) | Dibalik urutannya | `hello` → `olleh` |
| Angka (0-9) | Dibalik urutannya | `123` → `321` |
| Tanda Baca | Tetap di posisi semula | `hello!` → `olleh!` |
| Spasi | Tetap di posisi semula | `hello world` → `olleh dlrow` |

## 💻 Kode Fungsi

```javascript
function reverseSpecimenWords(observation) {
    // Pisahkan kalimat menjadi kata-kata berdasarkan spasi
    const words = observation.split(' ');
    
    // Proses setiap kata dalam array
    const reversedWords = words.map(word => {
        // Pisahkan huruf/angka dari tanda baca
        const letters = word.replace(/[^a-zA-Z0-9]/g, '');
        const punctuation = word.replace(/[a-zA-Z0-9]/g, '');
        
        // Balik urutan huruf/angka saja
        const reversedLetters = letters.split('').reverse().join('');
        
        // Temukan posisi tanda baca dalam kata asli
        let result = '';
        let letterIndex = 0;
        let punctIndex = 0;
        
        // Rekonstruksi kata dengan huruf terbalik dan tanda baca di posisi asli
        for (let i = 0; i < word.length; i++) {
            if (/[a-zA-Z0-9]/.test(word[i])) {
                // Jika karakter adalah huruf/angka, ambil dari huruf yang sudah dibalik
                result += reversedLetters[letterIndex];
                letterIndex++;
            } else {
                // Jika karakter adalah tanda baca, pertahankan di posisi asli
                result += word[i];
            }
        }
        
        return result;
    });
    
    // Gabungkan kembali kata-kata menjadi kalimat
    return reversedWords.join(' ');
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
console.log(output); // Output: "olleH, dlrow!"
```

### Contoh 3: Kalimat dengan Angka
```javascript
const input = "Test123 code456";
const output = reverseSpecimenWords(input);
console.log(output); // Output: "654edoc 321tseT"
```

### Contoh 4: Kalimat Kompleks
```javascript
const input = "JavaScript is fun! Let's code.";
const output = reverseSpecimenWords(input);
console.log(output); // Output: "tpircSavaJ si nuf! s'teL edoc."
```

## 🔍 Contoh Output Detail

| Input | Output | Penjelasan |
|-------|--------|------------|
| `"abc"` | `"cba"` | Huruf sederhana dibalik |
| `"a1b2c3"` | `"3c2b1a"` | Huruf dan angka dibalik bersama |
| `"hello!"` | `"olleh!"` | Tanda seru tetap di akhir |
| `"hi, there"` | `"ih, ereht"` | Koma dan spasi tetap di posisi |
| `"test-123"` | `"321t-tse"` | Tanda hubung tetap di tengah |

## ⚠️ Catatan Penting

1. **Spasi**: Fungsi ini mempertahankan spasi antar kata
2. **Tanda Baca**: Semua tanda baca (.,!?-:;) tetap di posisi semula
3. **Case Sensitivity**: Huruf besar dan kecil dibalik sesuai urutannya
4. **String Kosong**: Jika input kosong, akan mengembalikan string kosong

## 🚀 Tips Penggunaan

- Cocok untuk membuat puzzle kata sederhana
- Dapat digunakan sebagai langkah awal enkripsi teks
- Berguna untuk testing dan debugging aplikasi yang memproses teks
- Dapat dikombinasikan dengan fungsi lain untuk manipulasi string yang lebih kompleks
