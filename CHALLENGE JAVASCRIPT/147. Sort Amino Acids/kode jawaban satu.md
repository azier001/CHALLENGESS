# 🧬 Dokumentasi Fungsi `sortProtein`

## 📋 Deskripsi

Fungsi `sortProtein` digunakan untuk **memfilter dan mengurutkan** daftar asam amino berdasarkan 20 asam amino standar yang valid. Fungsi ini akan:
1. Menyaring hanya asam amino yang valid
2. Mengurutkannya secara alfabetis (A-Z)

Fungsi ini sangat berguna ketika Anda memiliki daftar asam amino yang mungkin mengandung nilai yang tidak valid, dan Anda ingin mendapatkan daftar yang bersih dan terurut.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `aminoAcids` | Array | Array yang berisi nama-nama asam amino (dalam bahasa Inggris) yang akan difilter dan diurutkan |

---

## 📊 Daftar Asam Amino Valid

Fungsi ini hanya menerima 20 asam amino standar berikut:

| No | Nama Asam Amino | Simbol 3 Huruf | Simbol 1 Huruf |
|----|-----------------|----------------|----------------|
| 1 | Alanine | Ala | A |
| 2 | Arginine | Arg | R |
| 3 | Asparagine | Asn | N |
| 4 | Aspartic acid | Asp | D |
| 5 | Cysteine | Cys | C |
| 6 | Glutamic acid | Glu | E |
| 7 | Glutamine | Gln | Q |
| 8 | Glycine | Gly | G |
| 9 | Histidine | His | H |
| 10 | Isoleucine | Ile | I |
| 11 | Leucine | Leu | L |
| 12 | Lysine | Lys | K |
| 13 | Methionine | Met | M |
| 14 | Phenylalanine | Phe | F |
| 15 | Proline | Pro | P |
| 16 | Serine | Ser | S |
| 17 | Threonine | Thr | T |
| 18 | Tryptophan | Trp | W |
| 19 | Tyrosine | Tyr | Y |
| 20 | Valine | Val | V |

---

## 💻 Kode Fungsi

```javascript
function sortProtein(aminoAcids) {
    // Daftar 20 asam amino standar yang valid
    const validAminoAcids = [
        'Alanine',
        'Arginine',
        'Asparagine',
        'Aspartic acid',
        'Cysteine',
        'Glutamic acid',
        'Glutamine',
        'Glycine',
        'Histidine',
        'Isoleucine',
        'Leucine',
        'Lysine',
        'Methionine',
        'Phenylalanine',
        'Proline',
        'Serine',
        'Threonine',
        'Tryptophan',
        'Tyrosine',
        'Valine'
    ];
    
    // Filter hanya asam amino yang valid, lalu urutkan secara alfabetis
    return aminoAcids
        .filter(acid => validAminoAcids.includes(acid))
        .sort();
}
```

---

## 📖 Cara Kerja

1. **Filter**: Menggunakan method `.filter()` untuk menyaring array input
   - Hanya asam amino yang ada di dalam daftar `validAminoAcids` yang akan lolos
   
2. **Sort**: Menggunakan method `.sort()` untuk mengurutkan hasil filter
   - Pengurutan dilakukan secara alfabetis (A-Z)

---

## 🎯 Contoh Penggunaan

### Contoh 1: Input dengan semua asam amino valid

```javascript
const input1 = ['Glycine', 'Alanine', 'Leucine', 'Valine'];
const result1 = sortProtein(input1);

console.log(result1);
```

**Output:**
```javascript
['Alanine', 'Glycine', 'Leucine', 'Valine']
```

**Penjelasan:** Semua asam amino valid dan sudah diurutkan dari A ke Z.

---

### Contoh 2: Input dengan asam amino tidak valid

```javascript
const input2 = ['Glycine', 'Protein', 'Alanine', 'Unknown', 'Leucine'];
const result2 = sortProtein(input2);

console.log(result2);
```

**Output:**
```javascript
['Alanine', 'Glycine', 'Leucine']
```

**Penjelasan:** 'Protein' dan 'Unknown' dibuang karena bukan asam amino valid.

---

### Contoh 3: Input dengan urutan acak

```javascript
const input3 = ['Tyrosine', 'Alanine', 'Methionine', 'Cysteine'];
const result3 = sortProtein(input3);

console.log(result3);
```

**Output:**
```javascript
['Alanine', 'Cysteine', 'Methionine', 'Tyrosine']
```

**Penjelasan:** Asam amino diurutkan sesuai abjad.

---

### Contoh 4: Input kosong

```javascript
const input4 = [];
const result4 = sortProtein(input4);

console.log(result4);
```

**Output:**
```javascript
[]
```

**Penjelasan:** Array kosong akan menghasilkan array kosong.

---

### Contoh 5: Input dengan asam amino duplikat

```javascript
const input5 = ['Alanine', 'Glycine', 'Alanine', 'Glycine'];
const result5 = sortProtein(input5);

console.log(result5);
```

**Output:**
```javascript
['Alanine', 'Alanine', 'Glycine', 'Glycine']
```

**Penjelasan:** Fungsi ini tidak menghilangkan duplikat, hanya memfilter dan mengurutkan.

---

## ⚠️ Catatan Penting

- **Case Sensitive**: Nama asam amino harus ditulis persis seperti dalam daftar (huruf kapital di awal)
  - ✅ `'Alanine'` → Valid
  - ❌ `'alanine'` → Tidak valid
  - ❌ `'ALANINE'` → Tidak valid

- **Duplikat**: Fungsi ini tidak menghilangkan duplikat secara otomatis

- **Return Value**: Fungsi mengembalikan array baru, tidak mengubah array asli

---

## 🚀 Tips Penggunaan

Jika Anda ingin menghilangkan duplikat sebelum mengurutkan, Anda bisa menggunakan `Set`:

```javascript
function sortProteinUnique(aminoAcids) {
    const validAminoAcids = [
        'Alanine', 'Arginine', 'Asparagine', 'Aspartic acid',
        'Cysteine', 'Glutamic acid', 'Glutamine', 'Glycine',
        'Histidine', 'Isoleucine', 'Leucine', 'Lysine',
        'Methionine', 'Phenylalanine', 'Proline', 'Serine',
        'Threonine', 'Tryptophan', 'Tyrosine', 'Valine'
    ];
    
    // Hilangkan duplikat dengan Set
    const uniqueAcids = [...new Set(aminoAcids)];
    
    // Filter dan urutkan
    return uniqueAcids
        .filter(acid => validAminoAcids.includes(acid))
        .sort();
}
```

---

## 📚 Referensi

- [Array.prototype.filter() - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Array.prototype.sort() - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
- [20 Asam Amino Standar](https://en.wikipedia.org/wiki/Proteinogenic_amino_acid)

---

## 📝 Lisensi

Fungsi ini dapat digunakan secara bebas untuk keperluan pembelajaran dan pengembangan aplikasi.

---

**Dibuat dengan ❤️ untuk memudahkan pengolahan data protein**
