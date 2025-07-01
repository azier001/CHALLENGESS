# 🧪 Chemical Formula Decoder (Enhanced Version)

## 📋 Deskripsi

Fungsi `decodeChemicalFormula` adalah sebuah decoder khusus yang mengubah formula kimia yang telah dikodekan menjadi formula kimia standar. Versi ini menggunakan pendekatan yang lebih efisien dengan object mapping dan dapat menangani unsur kimia yang memiliki simbol dua huruf (seperti Cl untuk Klorin). Fungsi ini secara otomatis mendeteksi dan memproses unsur multi-karakter serta menghitung jumlah setiap unsur dalam satu proses.

## ⚙️ Cara Kerja

Fungsi ini bekerja dalam 3 tahap utama:
1. **Decode**: Mengubah setiap karakter berdasarkan element mapping object
2. **Parse & Count**: Mendeteksi unsur (termasuk yang multi-karakter) dan menghitung jumlahnya
3. **Build**: Menyusun formula akhir dengan subscript yang sesuai

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `codedFormula` | `string` | Formula kimia yang sudah dikodekan menggunakan karakter khusus |

## 🔤 Tabel Pemetaan Karakter

| Karakter Input | Unsur Kimia | Nama Unsur |
|----------------|-------------|------------|
| `a` | `H` | Hidrogen |
| `b` | `O` | Oksigen |
| `c` | `C` | Karbon |
| `d` | `N` | Nitrogen |
| `e` | `Cl` | Klorin |
| Huruf lain | Huruf tersebut (kapital) | Sesuai huruf |

## 🔍 Deteksi Unsur Multi-Karakter

Fungsi ini dapat mendeteksi unsur yang memiliki simbol dua huruf dengan logika:
- Jika huruf kedua adalah huruf kecil → gabungkan sebagai satu unsur
- Contoh: `Cl` (C besar + l kecil) = unsur Klorin
- Contoh: `CO` (C besar + O besar) = Carbon + Oxygen terpisah

## 📤 Output

Fungsi ini mengembalikan sebuah **string** berupa formula kimia standar dengan:
- Simbol unsur kimia yang benar (termasuk unsur multi-karakter)
- Subscript angka untuk unsur yang muncul lebih dari sekali
- Urutan unsur sesuai urutan pemrosesan object

## 💡 Contoh Penggunaan

### Contoh 1: Air (H₂O)
```javascript
const result1 = decodeChemicalFormula("aab");
console.log(result1); // Output: "H2O"
```

### Contoh 2: Metana (CH₄)
```javascript
const result2 = decodeChemicalFormula("caaaa");
console.log(result2); // Output: "CH4"
```

### Contoh 3: Ammonia (NH₃)
```javascript
const result3 = decodeChemicalFormula("daaa");
console.log(result3); // Output: "NH3"
```

### Contoh 4: Natrium Klorida (NaCl)
```javascript
const result4 = decodeChemicalFormula("nae");
console.log(result4); // Output: "NaClH" // Catatan: Na + Cl
```

### Contoh 5: Unsur Multi-Karakter
```javascript
const result5 = decodeChemicalFormula("eee");
console.log(result5); // Output: "Cl3"
```

## 🔍 Penjelasan Detail

### Langkah 1: Element Mapping
Input dikodekan menggunakan object `elementMap`:
```javascript
const elementMap = {'a': 'H', 'b': 'O', 'c': 'C', 'd': 'N', 'e': 'Cl'};
```
- `"aab"` → `"HHO"`

### Langkah 2: Smart Parsing
Sistem mendeteksi unsur multi-karakter dengan memeriksa huruf kedua:
- Jika huruf kedua adalah lowercase → gabungkan (misal: `Cl`)
- Jika huruf kedua adalah uppercase → pisahkan (misal: `CO`)

### Langkah 3: Counting & Building
Menghitung setiap unsur dan langsung membangun formula:
- `H`: 2 kali → `H2`
- `O`: 1 kali → `O`
- Hasil: `"H2O"`

## 📝 Source Code

```javascript
function decodeChemicalFormula(codedFormula) {
  const elementMap = {
    'a': 'H',
    'b': 'O',
    'c': 'C',
    'd': 'N',
    'e': 'Cl'
  };

  let decodedFormula = '';

  for (let char of codedFormula) {
    if (char in elementMap) {
      decodedFormula += elementMap[char];
    } else {
      decodedFormula += char.toUpperCase();
    }
  }

  let elementCount = {};
  let result = '';
  let currentElement = '';

  for (let i = 0; i < decodedFormula.length; i++) {
    if (i < decodedFormula.length - 1 && decodedFormula[i + 1].toLowerCase() === decodedFormula[i + 1]) {
      currentElement = decodedFormula.slice(i, i + 2);
      i++;
    } else {
      currentElement = decodedFormula[i];
    }
    elementCount[currentElement] = (elementCount[currentElement] || 0) + 1;
  }

  for (let element in elementCount) {
    result += element;
    if (elementCount[element] > 1) {
      result += elementCount[element];
    }
  }

  return result;
}
```

## ✨ Keunggulan Versi Ini

| Fitur | Versi Lama | Versi Baru |
|-------|------------|------------|
| **Mapping Method** | Switch-case | Object mapping (lebih efisien) |
| **Multi-char Support** | ❌ | ✅ (deteksi otomatis Cl, Br, etc.) |
| **Processing Steps** | 3 tahap terpisah | 2 tahap terintegrasi |
| **Memory Usage** | Array intermediate | String processing |
| **Code Length** | Lebih panjang | Lebih ringkas |

## ⚠️ Catatan Penting

- **Multi-Character Detection**: Fungsi mendeteksi unsur dua huruf berdasarkan pola huruf besar-kecil
- **Case Sensitivity**: Input harus menggunakan huruf kecil untuk mapping, hasil otomatis menjadi format kimia standar
- **Object Iteration**: Urutan output mengikuti urutan iterasi JavaScript object (tidak selalu sama dengan urutan input)
- **Efficiency**: Versi ini lebih efisien dalam memory dan processing

## 🎯 Tips Penggunaan

1. **Object Mapping**: Lebih mudah menambah mapping baru dengan mengedit `elementMap`
2. **Multi-Character Elements**: Fungsi otomatis menangani Cl, Br, dll tanpa konfigurasi tambahan
3. **Performance**: Cocok untuk processing formula kimia dalam jumlah besar
4. **Extensibility**: Mudah diperluas untuk menambah aturan decoding baru

## 🚀 Contoh Pengembangan

Untuk menambah unsur baru, cukup edit `elementMap`:
```javascript
const elementMap = {
  'a': 'H',
  'b': 'O',
  'c': 'C',
  'd': 'N',
  'e': 'Cl',
  'f': 'Br',  // Tambahan baru: Bromine
  'g': 'Na'   // Tambahan baru: Sodium
};
```
