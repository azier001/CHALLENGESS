# 🌸 Dokumentasi Fungsi findFlower

## 📖 Deskripsi

Fungsi `findFlower` adalah sebuah fungsi JavaScript yang digunakan untuk mencari posisi atau indeks dari bunga tertentu dalam sebuah kebun (array). Fungsi ini menggunakan pendekatan yang lebih eksplisit dengan menyimpan hasil pencarian dalam variabel terlebih dahulu, kemudian melakukan pengecekan kondisi sebelum mengembalikan nilai. Fungsi akan mengembalikan indeks pertama dimana bunga tersebut ditemukan, atau -1 jika bunga tidak ditemukan dalam kebun.

## 🔧 Sintaks

```javascript
findFlower(garden, flower)
```

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `garden` | Array | Array yang berisi daftar bunga-bunga dalam kebun |
| `flower` | Any | Bunga yang ingin dicari dalam kebun |

## 📊 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Number` | Indeks posisi bunga dalam array (dimulai dari 0), atau -1 jika tidak ditemukan |

## 💻 Kode Fungsi

```javascript
function findFlower(garden, flower) {
    // Mencari indeks pertama dari bunga yang dicari dalam array garden
    const index = garden.indexOf(flower);
    
    // Mengecek apakah bunga ditemukan, jika ya return indeks, jika tidak return -1
    return index !== -1 ? index : -1;
}
```

## 🎯 Cara Kerja

1. Fungsi menerima dua parameter: `garden` (array bunga) dan `flower` (bunga yang dicari)
2. Menyimpan hasil pencarian menggunakan method `indexOf()` ke dalam variabel `index`
3. Menggunakan ternary operator untuk mengecek apakah `index` tidak sama dengan -1
4. Jika ditemukan (index !== -1), mengembalikan nilai `index`
5. Jika tidak ditemukan, mengembalikan -1

## 📋 Contoh Penggunaan

### Contoh 1: Bunga Ditemukan
```javascript
const kebunBunga = ['mawar', 'melati', 'tulip', 'anggrek', 'lily'];
const hasilPencarian = findFlower(kebunBunga, 'tulip');

console.log(hasilPencarian); 
// Output: 2 (tulip berada di indeks ke-2)
```

### Contoh 2: Bunga Tidak Ditemukan
```javascript
const kebunBunga = ['mawar', 'melati', 'tulip', 'anggrek', 'lily'];
const hasilPencarian = findFlower(kebunBunga, 'sakura');

console.log(hasilPencarian); 
// Output: -1 (sakura tidak ditemukan dalam kebun)
```

### Contoh 3: Array Kosong
```javascript
const kebunKosong = [];
const hasilPencarian = findFlower(kebunKosong, 'mawar');

console.log(hasilPencarian); 
// Output: -1 (tidak ada bunga dalam kebun kosong)
```

### Contoh 4: Pencarian dengan Berbagai Tipe Data
```javascript
const kebunCampur = ['mawar', 123, 'tulip', true, 'lily'];
const hasilAngka = findFlower(kebunCampur, 123);
const hasilBoolean = findFlower(kebunCampur, true);

console.log(hasilAngka);   // Output: 1
console.log(hasilBoolean); // Output: 3
```

## 📊 Tabel Karakter Khusus

| Karakter/Operator | Deskripsi | Fungsi |
|-------------------|-----------|---------|
| `[` `]` | Square brackets | Menandakan array dalam JavaScript |
| `'` `"` | Quote marks | Menandakan string literal |
| `const` | Keyword | Mendeklarasikan variabel yang tidak bisa diubah |
| `!==` | Strict inequality | Operator perbandingan tidak sama (nilai dan tipe) |
| `?` `:` | Ternary operator | Conditional operator untuk if-else singkat |
| `-1` | Angka negatif | Nilai return ketika elemen tidak ditemukan |

## 🔍 Penjelasan Ternary Operator

Bagian `index !== -1 ? index : -1` menggunakan **ternary operator** yang merupakan cara singkat menulis kondisi if-else:

```javascript
// Ternary operator (bentuk singkat)
return index !== -1 ? index : -1;

// Setara dengan if-else (bentuk panjang)
if (index !== -1) {
    return index;
} else {
    return -1;
}
```

## ⚠️ Hal Penting yang Perlu Diperhatikan

- Fungsi ini **case-sensitive**, artinya 'Mawar' dan 'mawar' dianggap berbeda
- Indeks array dimulai dari 0, bukan 1
- Jika ada bunga yang sama lebih dari satu, fungsi akan mengembalikan indeks yang pertama ditemukan
- Parameter `garden` harus berupa array, jika bukan array akan menyebabkan error
- Penggunaan `const` membuat variabel `index` tidak bisa diubah setelah dideklarasikan
- Ternary operator dalam kasus ini sebenarnya redundan karena `indexOf()` sudah mengembalikan -1 jika tidak ditemukan

## 🚀 Tips Penggunaan

1. **Validasi Input**: Pastikan parameter `garden` adalah array sebelum menggunakan fungsi
2. **Case Handling**: Pertimbangkan untuk mengkonversi ke lowercase jika ingin pencarian tidak case-sensitive
3. **Error Handling**: Selalu cek apakah hasil return adalah -1 untuk menangani kasus bunga tidak ditemukan
4. **Optimasi**: Kode bisa disederhanakan menjadi `return garden.indexOf(flower)` karena hasil sama

## 🔄 Versi yang Disederhanakan

```javascript
function findFlower(garden, flower) {
    // Versi yang lebih sederhana dengan hasil yang sama
    return garden.indexOf(flower);
}
```

## 🔍 Contoh Implementasi Lengkap

```javascript
function findFlower(garden, flower) {
    // Validasi input: pastikan garden adalah array
    if (!Array.isArray(garden)) {
        console.error('Parameter garden harus berupa array!');
        return -1;
    }
    
    // Mencari indeks pertama dari bunga yang dicari dalam array garden
    const index = garden.indexOf(flower);
    
    // Mengecek apakah bunga ditemukan, jika ya return indeks, jika tidak return -1
    return index !== -1 ? index : -1;
}

// Contoh penggunaan dengan validasi hasil
const myGarden = ['mawar', 'melati', 'tulip', 'anggrek'];
const searchFlower = 'melati';
const result = findFlower(myGarden, searchFlower);

if (result !== -1) {
    console.log(`Bunga ${searchFlower} ditemukan di posisi ${result}`);
} else {
    console.log(`Bunga ${searchFlower} tidak ditemukan dalam kebun`);
}

// Output: Bunga melati ditemukan di posisi 1
```

## 💡 Analisis Kode

**Kelebihan:**
- Kode lebih eksplisit dan mudah dibaca untuk pemula
- Variabel `index` memudahkan debugging
- Menunjukkan penggunaan ternary operator

**Kekurangan:**
- Sedikit lebih verbose dari yang diperlukan
- Ternary operator redundan dalam konteks ini
- Menggunakan memori tambahan untuk variabel `index`

---
*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi `findFlower` dengan pendekatan yang lebih eksplisit menggunakan ternary operator.* 🌺
