# 🦋 Dokumentasi Fungsi `countButterflyColors`

## 📋 Deskripsi

Fungsi `countButterflyColors` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung jumlah kemunculan setiap warna kupu-kupu dalam sebuah array. Fungsi ini sangat berguna ketika Anda ingin mengetahui berapa banyak kupu-kupu dari setiap warna yang ada dalam koleksi data Anda.

## 🔧 Sintaks

```javascript
countButterflyColors(colors)
```

## 📝 Parameter

| Parameter | Tipe    | Wajib | Deskripsi |
|-----------|---------|-------|-----------|
| `colors`  | Array   | Ya    | Array yang berisi nama-nama warna kupu-kupu (string) |

### Detail Parameter:
- **colors**: Array berisi string yang merepresentasikan warna kupu-kupu
- Contoh: `['merah', 'biru', 'kuning', 'merah', 'hijau']`

## 🎯 Return Value

Fungsi ini mengembalikan sebuah **Object** yang berisi:
- **Key**: Nama warna (string)
- **Value**: Jumlah kemunculan warna tersebut (number)

## 💻 Kode Fungsi

```javascript
function countButterflyColors(colors) {
    // Membuat objek kosong untuk menyimpan hitungan warna
    const colorCounts = {};
    
    // Melakukan iterasi untuk setiap warna dalam array
    for (const color of colors) {
        // Jika warna sudah ada, tambahkan 1. Jika belum ada, mulai dari 1
        colorCounts[color] = (colorCounts[color] || 0) + 1;
    }
    
    // Mengembalikan objek yang berisi hitungan setiap warna
    return colorCounts;
}
```

## 🎨 Tabel Warna Kupu-kupu yang Didukung

| 🎨 Warna | Deskripsi | Contoh Penggunaan |
|----------|-----------|-------------------|
| merah | Kupu-kupu berwarna merah | `'merah'` |
| biru | Kupu-kupu berwarna biru | `'biru'` |
| kuning | Kupu-kupu berwarna kuning | `'kuning'` |
| hijau | Kupu-kupu berwarna hijau | `'hijau'` |
| ungu | Kupu-kupu berwarna ungu | `'ungu'` |
| oranye | Kupu-kupu berwarna oranye | `'oranye'` |

*Catatan: Fungsi ini mendukung semua nama warna dalam bentuk string*

## 📖 Contoh Penggunaan

### Contoh 1: Data Sederhana
```javascript
const warnaKupuKupu = ['merah', 'biru', 'kuning', 'merah', 'hijau'];
const hasil = countButterflyColors(warnaKupuKupu);

console.log(hasil);
```

**Output:**
```javascript
{
    merah: 2,
    biru: 1,
    kuning: 1,
    hijau: 1
}
```

### Contoh 2: Data dengan Banyak Warna
```javascript
const warnaKupuKupu = [
    'merah', 'biru', 'kuning', 'merah', 'hijau',
    'ungu', 'biru', 'merah', 'oranye', 'kuning'
];

const hasil = countButterflyColors(warnaKupuKupu);

console.log(hasil);
```

**Output:**
```javascript
{
    merah: 3,
    biru: 2,
    kuning: 2,
    hijau: 1,
    ungu: 1,
    oranye: 1
}
```

### Contoh 3: Array Kosong
```javascript
const warnaKosong = [];
const hasil = countButterflyColors(warnaKosong);

console.log(hasil);
```

**Output:**
```javascript
{}
```

## 🚀 Cara Kerja Fungsi

1. **Inisialisasi**: Membuat objek kosong `colorCounts` untuk menyimpan hasil hitungan
2. **Iterasi**: Menggunakan loop `for...of` untuk mengiterasi setiap elemen dalam array `colors`
3. **Penghitungan**: Untuk setiap warna:
   - Jika warna sudah ada dalam objek, tambahkan 1
   - Jika warna belum ada, inisialisasi dengan nilai 1
4. **Return**: Mengembalikan objek yang berisi hitungan setiap warna

## 💡 Tips Penggunaan

- ✅ Pastikan input berupa array yang berisi string
- ✅ Nama warna harus konsisten (huruf besar/kecil)
- ✅ Fungsi ini case-sensitive: `'Merah'` dan `'merah'` dianggap berbeda
- ✅ Dapat digunakan untuk menghitung frekuensi elemen apapun, tidak hanya warna

## ⚠️ Hal yang Perlu Diperhatikan

- Fungsi ini tidak melakukan validasi input
- Nama warna yang berbeda penulisan akan dianggap sebagai warna yang berbeda
- Input harus berupa array, jika tidak akan menghasilkan error

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- 📊 Analisis data warna kupu-kupu dalam penelitian
- 🎮 Game yang melibatkan koleksi kupu-kupu
- 📈 Dashboard statistik warna
- 🔍 Filtering dan sorting data berdasarkan warna
