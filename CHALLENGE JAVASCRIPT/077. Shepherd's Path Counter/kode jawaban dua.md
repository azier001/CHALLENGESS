# 🐑 Count Shepherd Moves

## 📋 Deskripsi
Fungsi `countShepherdMoves` digunakan untuk menghitung jumlah perpindahan yang dilakukan oleh seorang gembala dalam mengelola kawanan domba di lapangan. Fungsi ini menganalisis urutan posisi atau status domba dan menghitung berapa kali gembala harus berpindah untuk mengurus kawanan yang berbeda.

## 🔧 Sintaks
```javascript
countShepherdMoves(field)
```

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `field` | Array | Array yang berisi representasi lapangan atau urutan posisi/status domba |

## 🔄 Return Value
- **Tipe**: `number`
- **Deskripsi**: Jumlah perpindahan yang harus dilakukan gembala

## 💻 Kode Fungsi

```javascript
function countShepherdMoves(field) {
    let moves = 0; // Inisialisasi counter untuk perpindahan
    
    // Loop melalui array mulai dari index 1
    for (let i = 1; i < field.length; i++) {
        // Jika elemen saat ini berbeda dengan elemen sebelumnya
        if (field[i] !== field[i - 1]) {
            moves++; // Tambah counter perpindahan
        }
    }
    
    return moves; // Kembalikan total perpindahan
}
```

## 🎯 Cara Kerja
1. Fungsi memulai dengan menginisialisasi variabel `moves` dengan nilai 0
2. Loop dimulai dari index 1 (elemen kedua) hingga akhir array
3. Setiap iterasi membandingkan elemen saat ini dengan elemen sebelumnya
4. Jika kedua elemen berbeda, berarti gembala perlu berpindah, maka counter `moves` ditambah 1
5. Fungsi mengembalikan total jumlah perpindahan

## 📊 Contoh Penggunaan

### Contoh 1: Kawanan dengan Berbagai Status
```javascript
const field1 = ['A', 'A', 'B', 'B', 'A', 'C'];
console.log(countShepherdMoves(field1));
// Output: 3
// Penjelasan: A→A (0), A→B (1), B→B (0), B→A (2), A→C (3)
```

### Contoh 2: Kawanan Homogen
```javascript
const field2 = ['sheep', 'sheep', 'sheep', 'sheep'];
console.log(countShepherdMoves(field2));
// Output: 0
// Penjelasan: Semua domba sama, tidak perlu perpindahan
```

### Contoh 3: Setiap Posisi Berbeda
```javascript
const field3 = [1, 2, 3, 4, 5];
console.log(countShepherdMoves(field3));
// Output: 4
// Penjelasan: Setiap posisi berbeda, butuh 4 perpindahan
```

### Contoh 4: Array Kosong atau Satu Elemen
```javascript
const field4 = [];
console.log(countShepherdMoves(field4)); // Output: 0

const field5 = ['A'];
console.log(countShepherdMoves(field5)); // Output: 0
```

## 🎨 Visualisasi
Misalnya kita punya field: `['A', 'A', 'B', 'C', 'C']`

```
Posisi:  0   1   2   3   4
Field:  [A] [A] [B] [C] [C]
         ↓   ↓   ↓   ↓   ↓
Cek:     -  sama beda beda sama
Moves:   -   0   1   2   2
```

Total perpindahan: **2**

## ⚠️ Catatan Penting
- Fungsi akan mengembalikan `0` jika array kosong atau hanya memiliki satu elemen
- Fungsi menggunakan strict equality (`!==`) untuk membandingkan elemen
- Pastikan array yang dimasukkan tidak `null` atau `undefined`

## 🔍 Kompleksitas
- **Time Complexity**: O(n) - dimana n adalah panjang array
- **Space Complexity**: O(1) - hanya menggunakan variabel tambahan yang konstan
