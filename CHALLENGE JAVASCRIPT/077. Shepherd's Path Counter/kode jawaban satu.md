# 🐑 Count Shepherd Moves

## 📋 Deskripsi
Fungsi `countShepherdMoves` digunakan untuk menghitung jumlah perpindahan yang dilakukan oleh seorang gembala dalam mengelola kawanan domba di lapangan. Fungsi ini menganalisis urutan posisi di field dan menghitung berapa kali gembala harus berpindah antara posisi kosong (`.`) dan posisi yang berisi domba (`s`). Setiap kali ada perubahan dari posisi kosong ke posisi berisi domba atau sebaliknya, dihitung sebagai satu perpindahan.

## 🔧 Sintaks
```javascript
countShepherdMoves(field)
```

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `field` | Array | Array yang berisi representasi lapangan dengan karakter '.' (kosong) dan 's' (domba) |

## 🎯 Karakter yang Digunakan

| Karakter | Deskripsi | Contoh |
|----------|-----------|---------|
| `'.'` | Posisi kosong di lapangan | Tidak ada domba |
| `'s'` | Posisi yang berisi domba | Ada domba (sheep) |

## 🔄 Return Value
- **Tipe**: `number`
- **Deskripsi**: Jumlah perpindahan yang harus dilakukan gembala antara posisi kosong dan posisi berisi domba

## 💻 Kode Fungsi

```javascript
function countShepherdMoves(field) {
    let moves = 0; // Inisialisasi counter untuk perpindahan
    
    // Loop melalui array mulai dari index 1
    for (let i = 1; i < field.length; i++) {
        // Jika ada perpindahan dari posisi kosong ke domba ATAU dari domba ke posisi kosong
        if ((field[i] === '.' && field[i - 1] === 's') || 
            (field[i] === 's' && field[i - 1] === '.')) {
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
4. Jika terjadi perpindahan dari:
   - Posisi kosong (`.`) ke posisi berisi domba (`s`), atau
   - Posisi berisi domba (`s`) ke posisi kosong (`.`)
   
   Maka counter `moves` ditambah 1
5. Fungsi mengembalikan total jumlah perpindahan

## 📊 Contoh Penggunaan

### Contoh 1: Field dengan Beberapa Perpindahan
```javascript
const field1 = ['.', 's', 's', '.', 's'];
console.log(countShepherdMoves(field1));
// Output: 3
// Penjelasan: . → s (1), s → s (0), s → . (2), . → s (3)
```

### Contoh 2: Field Tanpa Perpindahan
```javascript
const field2 = ['s', 's', 's', 's'];
console.log(countShepherdMoves(field2));
// Output: 0
// Penjelasan: Semua posisi berisi domba, tidak ada perpindahan
```

### Contoh 3: Field Kosong Semua
```javascript
const field3 = ['.', '.', '.', '.'];
console.log(countShepherdMoves(field3));
// Output: 0
// Penjelasan: Semua posisi kosong, tidak ada perpindahan
```

### Contoh 4: Field Bergantian
```javascript
const field4 = ['s', '.', 's', '.', 's'];
console.log(countShepherdMoves(field4));
// Output: 4
// Penjelasan: s → . (1), . → s (2), s → . (3), . → s (4)
```

### Contoh 5: Array Satu Elemen
```javascript
const field5 = ['s'];
console.log(countShepherdMoves(field5)); // Output: 0

const field6 = ['.'];
console.log(countShepherdMoves(field6)); // Output: 0
```

## 🎨 Visualisasi
Misalnya kita punya field: `['.', 's', 's', '.', 's']`

```
Posisi:   0   1   2   3   4
Field:   [.] [s] [s] [.] [s]
          ↓   ↓   ↓   ↓   ↓
Cek:      -  .→s s→s s→. .→s
Moves:    -   1   1   2   3
```

**Penjelasan langkah demi langkah:**
- Index 1: `.` → `s` (kosong ke domba) = **Move 1** ✅
- Index 2: `s` → `s` (domba ke domba) = **Tidak dihitung**
- Index 3: `s` → `.` (domba ke kosong) = **Move 2** ✅ 
- Index 4: `.` → `s` (kosong ke domba) = **Move 3** ✅

**Total perpindahan: 3**

## ⚠️ Catatan Penting
- Fungsi hanya menghitung perpindahan antara karakter `.` dan `s`
- Perpindahan dari `s` ke `s` atau dari `.` ke `.` tidak dihitung
- Fungsi akan mengembalikan `0` jika array kosong atau hanya memiliki satu elemen
- Pastikan array hanya berisi karakter `.` dan `s` untuk hasil yang akurat
- Karakter lain akan diabaikan dalam perhitungan

## 🔍 Kompleksitas
- **Time Complexity**: O(n) - dimana n adalah panjang array
- **Space Complexity**: O(1) - hanya menggunakan variabel tambahan yang konstan

## 🎮 Use Case
Fungsi ini berguna untuk:
- Game simulasi peternakan
- Algoritma pathfinding sederhana
- Menghitung perubahan state dalam sistem binary
- Analisis pola perpindahan dalam data sequential
