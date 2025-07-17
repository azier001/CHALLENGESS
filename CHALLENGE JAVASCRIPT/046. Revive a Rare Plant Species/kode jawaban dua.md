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
3. **Pengelompokan**: Mengelompokkan kembali karakter menjadi grup berisi 4 karakter
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
    
    // Mengelompokkan sekuens yang sudah dibalik ke dalam grup berisi 4 karakter dengan spasi
    const result = [];
    
    for (let i = 0; i < reversedSequence.length; i += 4) {
        result.push(reversedSequence.slice(i, i + 4));
    }
    
    return result.join(' ');
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

## 🔍 Penjelasan Step-by-Step

Untuk memahami cara kerja fungsi ini, mari kita ikuti contoh `"ATCG GTAA"`:

1. **Input awal**: `"ATCG GTAA"`
2. **Setelah menghapus spasi**: `"ATCGGTAA"`
3. **Setelah dibalik**: `"AATGCGTA"`
4. **Pengelompokan**:
   - Grup 1: `"AATG"` (posisi 0-3)
   - Grup 2: `"CGTA"` (posisi 4-7)
5. **Output akhir**: `"AATG CGTA"`

## ⚠️ Catatan Penting

- Fungsi ini akan mengelompokkan karakter menjadi grup berisi 4 karakter
- Jika panjang sekuens tidak habis dibagi 4, grup terakhir akan berisi sisa karakter
- Spasi dalam input akan diabaikan dan tidak mempengaruhi hasil
- Fungsi ini case-sensitive (membedakan huruf besar dan kecil)

## 🚀 Penggunaan Praktis

Fungsi ini dapat digunakan untuk:
- Simulasi pengolahan data genetik
- Permainan puzzle DNA
- Pembelajaran tentang manipulasi string
- Proyek bioinformatika sederhana

## 📚 Referensi

Fungsi ini menggunakan konsep dasar:
- String manipulation dengan `replace()`, `split()`, `reverse()`, `join()`
- Array manipulation dengan `slice()` dan `push()`
- Loop `for` untuk iterasi dan pengelompokan
