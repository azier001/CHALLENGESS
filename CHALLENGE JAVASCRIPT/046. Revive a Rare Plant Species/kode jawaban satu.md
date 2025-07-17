# 🧬 Dokumentasi Fungsi `reviveRarePlant`

## 📋 Deskripsi

Fungsi `reviveRarePlant` adalah sebuah fungsi JavaScript yang digunakan untuk memproses sekuens DNA dengan cara membalik urutan karakter dan mengelompokkannya kembali menjadi format yang rapi. Fungsi ini mensimulasikan proses "menghidupkan kembali" tanaman langka melalui manipulasi sekuens DNA.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `dnaSequence` | String | Sekuens DNA yang akan diproses. Dapat berisi spasi sebagai pemisah grup karakter |

## ⚙️ Cara Kerja

1. **Pembersihan**: Menghapus semua spasi dari sekuens DNA
2. **Pembalikan**: Membalik urutan seluruh karakter dalam sekuens
3. **Pengelompokan**: Mengelompokkan kembali karakter menjadi grup berisi maksimal 4 karakter
4. **Format Output**: Menggabungkan grup dengan spasi sebagai pemisah

## 🧪 Karakter DNA yang Umum Digunakan

| Karakter | Nama | Deskripsi |
|----------|------|-----------|
| A | Adenine | Basa purin |
| T | Thymine | Basa pirimidin |
| G | Guanine | Basa purin |
| C | Cytosine | Basa pirimidin |

## 💻 Kode Lengkap

```javascript
function reviveRarePlant(dnaSequence) {
    // Menghapus spasi dan membalik seluruh sekuens
    const reversedSequence = dnaSequence
        .replace(/\s/g, '')
        .split('')
        .reverse()
        .join('');
    
    // Membagi sekuens yang sudah dibalik menjadi grup berisi 4 karakter dan menggabungkan dengan spasi
    const formattedSequence = reversedSequence
        .match(/.{1,4}/g)
        .join(' ');
    
    return formattedSequence;
}
```

## 📝 Contoh Penggunaan

### Contoh 1: Sekuens DNA Pendek
```javascript
const input1 = "ATCG GTAA";
const output1 = reviveRarePlant(input1);
console.log(output1);
// Output: "AATG GCTA"
```

### Contoh 2: Sekuens DNA Panjang
```javascript
const input2 = "ATCG GTAA CCTT GGAA";
const output2 = reviveRarePlant(input2);
console.log(output2);
// Output: "AAGG TTCC AATG GCTA"
```

### Contoh 3: Sekuens Tanpa Spasi
```javascript
const input3 = "ATCGGTAA";
const output3 = reviveRarePlant(input3);
console.log(output3);
// Output: "AATG GCTA"
```

### Contoh 4: Sekuens dengan Panjang Tidak Habis Dibagi 4
```javascript
const input4 = "ATCG GTA";
const output4 = reviveRarePlant(input4);
console.log(output4);
// Output: "ATGT GCT"
```

## 🔍 Penjelasan Step-by-Step

Untuk memahami cara kerja fungsi ini, mari kita ikuti contoh `"ATCG GTAA"`:

1. **Input awal**: `"ATCG GTAA"`
2. **Setelah menghapus spasi**: `"ATCGGTAA"`
3. **Setelah dibalik**: `"AATGCTAG"`
4. **Pengelompokan dengan regex `/.{1,4}/g`**:
   - Grup 1: `"AATG"` (4 karakter pertama)
   - Grup 2: `"CTAG"` (4 karakter berikutnya)
5. **Output akhir**: `"AATG CTAG"`

## 🔧 Penjelasan Teknis

### Regex Pattern `/.{1,4}/g`
- `.` : Mencocokkan karakter apa saja kecuali newline
- `{1,4}` : Mencocokkan 1 hingga 4 karakter
- `g` : Global flag, mencari semua kemunculan

### Method yang Digunakan
- `replace(/\s/g, '')` : Menghapus semua whitespace
- `split('')` : Memecah string menjadi array karakter
- `reverse()` : Membalik urutan array
- `join('')` : Menggabungkan array kembali menjadi string
- `match(/.{1,4}/g)` : Mengelompokkan karakter dengan regex
- `join(' ')` : Menggabungkan grup dengan spasi

## ⚠️ Catatan Penting

- Fungsi ini akan mengelompokkan karakter menjadi grup berisi maksimal 4 karakter
- Jika panjang sekuens tidak habis dibagi 4, grup terakhir akan berisi sisa karakter
- Spasi dalam input akan diabaikan dan tidak mempengaruhi hasil
- Fungsi ini case-sensitive (membedakan huruf besar dan kecil)
- Menggunakan regex `match()` lebih efisien dibanding loop manual

## 🚀 Penggunaan Praktis

Fungsi ini dapat digunakan untuk:
- Simulasi pengolahan data genetik
- Permainan puzzle DNA
- Pembelajaran tentang manipulasi string dan regex
- Proyek bioinformatika sederhana
- Enkripsi sederhana dengan pembalikan karakter

## 📚 Referensi

Fungsi ini menggunakan konsep dasar:
- String manipulation dengan `replace()`, `split()`, `reverse()`, `join()`
- Regular Expression (regex) dengan `match()`
- Array manipulation methods
- Pattern matching untuk pengelompokan karakter

## 🎯 Keunggulan Implementasi

- **Efisien**: Menggunakan regex untuk pengelompokan
- **Ringkas**: Kode yang lebih pendek dan mudah dibaca
- **Fleksibel**: Otomatis menangani sisa karakter yang tidak habis dibagi 4
- **Performant**: Menggunakan built-in JavaScript methods yang optimal
