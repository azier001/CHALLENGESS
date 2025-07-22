# 🌸 Dokumentasi Fungsi findFlower

## 📖 Deskripsi

Fungsi `findFlower` adalah sebuah fungsi JavaScript yang digunakan untuk mencari posisi atau indeks dari bunga tertentu dalam sebuah kebun (array). Fungsi ini akan mengembalikan indeks pertama dimana bunga tersebut ditemukan, atau -1 jika bunga tidak ditemukan dalam kebun.

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
    return garden.indexOf(flower);
}
```

## 🎯 Cara Kerja

1. Fungsi menerima dua parameter: `garden` (array bunga) dan `flower` (bunga yang dicari)
2. Menggunakan method `indexOf()` untuk mencari posisi pertama bunga dalam array
3. Mengembalikan indeks jika ditemukan, atau -1 jika tidak ditemukan

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

## 📊 Tabel Karakter Khusus

| Karakter | Deskripsi | Fungsi |
|----------|-----------|---------|
| `[` `]` | Square brackets | Menandakan array dalam JavaScript |
| `'` `"` | Quote marks | Menandakan string literal |
| `-1` | Angka negatif | Nilai return ketika elemen tidak ditemukan |

## ⚠️ Hal Penting yang Perlu Diperhatikan

- Fungsi ini **case-sensitive**, artinya 'Mawar' dan 'mawar' dianggap berbeda
- Indeks array dimulai dari 0, bukan 1
- Jika ada bunga yang sama lebih dari satu, fungsi akan mengembalikan indeks yang pertama ditemukan
- Parameter `garden` harus berupa array, jika bukan array akan menyebabkan error

## 🚀 Tips Penggunaan

1. **Validasi Input**: Pastikan parameter `garden` adalah array sebelum menggunakan fungsi
2. **Case Handling**: Pertimbangkan untuk mengkonversi ke lowercase jika ingin pencarian tidak case-sensitive
3. **Error Handling**: Selalu cek apakah hasil return adalah -1 untuk menangani kasus bunga tidak ditemukan

## 🔍 Contoh Implementasi Lengkap

```javascript
function findFlower(garden, flower) {
    // Validasi input: pastikan garden adalah array
    if (!Array.isArray(garden)) {
        console.error('Parameter garden harus berupa array!');
        return -1;
    }
    
    // Mencari indeks pertama dari bunga yang dicari dalam array garden
    return garden.indexOf(flower);
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
```

---
*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi `findFlower` dengan mudah dan jelas.* 🌺
