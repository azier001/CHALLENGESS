# 🥗 Dokumentasi Fungsi `tropicalFruitSalad`

## 📖 Deskripsi

Fungsi `tropicalFruitSalad` adalah sebuah fungsi JavaScript yang mensimulasikan proses pembuatan salad buah tropis. Fungsi ini mengambil array buah-buahan dan memproses mereka melalui beberapa langkah untuk menghasilkan salad buah yang "dimodifikasi".

## ⚙️ Sintaks

```javascript
tropicalFruitSalad(fruits)
```

## 📋 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `fruits` | Array | Ya | Array berisi nama-nama buah dalam bentuk string |

## 🔄 Proses Kerja Fungsi

Fungsi ini bekerja dalam 4 langkah utama:

1. **🗑️ Buang buah pertama dan terakhir**: Menghilangkan elemen pertama dan terakhir dari array
2. **🍯 Proses berdasarkan indeks genap**: Menambahkan huruf 'y' di akhir nama buah (pemanis)
3. **🔪 Proses berdasarkan indeks ganjil**: Menghapus karakter terakhir dari nama buah (dipotong)
4. **🔄 Balik urutan**: Membalik urutan array untuk "mencampur" salad

## 💻 Kode Fungsi

```javascript
function tropicalFruitSalad(fruits) {
    // Langkah 1: Buang buah pertama dan terakhir
    if (fruits.length <= 2) {
        return [];
    }
    
    let processedFruits = fruits.slice(1, -1);
    
    // Langkah 2 & 3: Proses setiap buah berdasarkan indeks
    for (let i = 0; i < processedFruits.length; i++) {
        if (i % 2 === 0) {
            // Indeks genap: tambah 'y' di akhir (pemanis)
            processedFruits[i] += 'y';
        } else {
            // Indeks ganjil: hapus karakter terakhir (dipotong)
            processedFruits[i] = processedFruits[i].slice(0, -1);
        }
    }
    
    // Langkah 4: Balik urutan (campur saladnya)
    return processedFruits.reverse();
}
```

## 📊 Tabel Karakteristik Proses

| Indeks | Tipe | Operasi | Simbol | Contoh |
|--------|------|---------|---------|---------|
| 0, 2, 4, ... | Genap | Tambah 'y' | `+y` | `"mango"` → `"mangoy"` |
| 1, 3, 5, ... | Ganjil | Hapus karakter terakhir | `slice(0, -1)` | `"banana"` → `"banan"` |

## 🎯 Nilai Kembalian

- **Tipe**: Array
- **Isi**: Array buah yang sudah diproses dan dibalik urutannya
- **Kondisi khusus**: Mengembalikan array kosong `[]` jika input memiliki 2 elemen atau kurang

## 📝 Contoh Penggunaan

### Contoh 1: Array Normal
```javascript
const buahTropis = ["apple", "mango", "banana", "papaya", "orange"];
const hasil = tropicalFruitSalad(buahTropis);
console.log(hasil);
```

**Output:**
```javascript
["papay", "bananay", "mango"]
```

**Penjelasan proses:**
1. **Input**: `["apple", "mango", "banana", "papaya", "orange"]`
2. **Setelah buang pertama & terakhir**: `["mango", "banana", "papaya"]`
3. **Setelah diproses**:
   - `"mango"` (indeks 0, genap) → `"mangoy"`
   - `"banana"` (indeks 1, ganjil) → `"banan"`
   - `"papaya"` (indeks 2, genap) → `"papayay"`
4. **Setelah dibalik**: `["papayay", "banan", "mangoy"]`

### Contoh 2: Array Pendek
```javascript
const buahSedikit = ["apple", "mango"];
const hasil = tropicalFruitSalad(buahSedikit);
console.log(hasil);
```

**Output:**
```javascript
[]
```

### Contoh 3: Array dengan 3 Elemen
```javascript
const tigaBuah = ["kiwi", "durian", "rambutan"];
const hasil = tropicalFruitSalad(tigaBuah);
console.log(hasil);
```

**Output:**
```javascript
["duriany"]
```

**Penjelasan proses:**
1. **Input**: `["kiwi", "durian", "rambutan"]`
2. **Setelah buang pertama & terakhir**: `["durian"]`
3. **Setelah diproses**: `["duriany"]` (indeks 0, genap, tambah 'y')
4. **Setelah dibalik**: `["duriany"]` (hanya 1 elemen)

## 🚨 Catatan Penting

- ⚠️ Fungsi ini akan mengembalikan array kosong jika input memiliki 2 elemen atau kurang
- 🔤 Semua elemen dalam array harus berupa string
- 📏 Minimal diperlukan 3 elemen untuk mendapatkan output yang bermakna
- 🔄 Urutan hasil akan selalu terbalik dari urutan awal (setelah dibuang elemen pertama dan terakhir)

## 🎨 Use Case

Fungsi ini cocok untuk:
- 🎲 Permainan kata atau puzzle
- 🧪 Demonstrasi manipulasi array dan string
- 📚 Materi pembelajaran tentang operasi array dalam JavaScript
- 🎯 Latihan algoritma sederhana
