# 🌊 Dokumentasi Fungsi `navigateOcean`

## 📋 Deskripsi

Fungsi `navigateOcean` adalah fungsi yang digunakan untuk memeriksa apakah sebuah posisi dapat mencapai tujuan dalam satu langkah lurus (horizontal atau vertikal). Fungsi ini mengembalikan nilai `true` jika posisi saat ini dan tujuan berada pada baris yang sama ATAU kolom yang sama.

Fungsi ini menggunakan sistem koordinat seperti papan catur, di mana:
- **Huruf (Letter)** merepresentasikan kolom (A, B, C, dst.)
- **Angka (Number)** merepresentasikan baris (1, 2, 3, dst.)

Fungsi ini berguna untuk:
- 🗺️ Validasi pergerakan dalam grid/papan permainan
- 🚢 Pengecekan jalur navigasi sederhana
- ♟️ Logika permainan catur atau strategi berbasis koordinat
- 🎯 Sistem navigasi berbasis koordinat huruf-angka

---

## 📝 Kode Fungsi

```javascript
function navigateOcean(currentPosition, destination) {
  // Mengambil huruf (kolom) dari posisi saat ini
  const currentLetter = currentPosition[0];
  
  // Mengambil angka (baris) dari posisi saat ini
  const currentNumber = currentPosition[1];
  
  // Mengambil huruf (kolom) dari tujuan
  const destinationLetter = destination[0];
  
  // Mengambil angka (baris) dari tujuan
  const destinationNumber = destination[1];
  
  // Mengecek apakah berada di kolom yang sama ATAU baris yang sama
  if (currentLetter === destinationLetter || currentNumber === destinationNumber) {
    return true;  // Dapat bergerak lurus (horizontal atau vertikal)
  } else {
    return false; // Tidak dapat bergerak lurus (diagonal atau tidak terhubung)
  }
}
```

---

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `currentPosition` | `Array [letter, number]` | Array berisi 2 elemen yang merepresentasikan koordinat posisi saat ini. Elemen pertama adalah huruf/kolom (letter), elemen kedua adalah angka/baris (number) |
| `destination` | `Array [letter, number]` | Array berisi 2 elemen yang merepresentasikan koordinat tujuan. Elemen pertama adalah huruf/kolom (letter), elemen kedua adalah angka/baris (number) |

### Penjelasan Detail Parameter:

- **currentPosition[0]** (currentLetter): Huruf yang merepresentasikan kolom dari posisi saat ini (misal: 'A', 'B', 'C')
- **currentPosition[1]** (currentNumber): Angka yang merepresentasikan baris dari posisi saat ini (misal: 1, 2, 3)
- **destination[0]** (destinationLetter): Huruf yang merepresentasikan kolom tujuan
- **destination[1]** (destinationNumber): Angka yang merepresentasikan baris tujuan

---

## 🔄 Return Value

| Tipe | Nilai | Kondisi |
|------|-------|---------|
| `Boolean` | `true` | Jika posisi dan tujuan berada di kolom yang sama (huruf sama) ATAU baris yang sama (angka sama) |
| `Boolean` | `false` | Jika posisi dan tujuan tidak berada di kolom atau baris yang sama (pergerakan diagonal) |

---

## 💡 Cara Kerja

Fungsi ini bekerja dalam 3 tahap:

### 1️⃣ Ekstraksi Koordinat
Memisahkan komponen huruf (kolom) dan angka (baris) dari kedua posisi:
```javascript
const currentLetter = currentPosition[0];    // Huruf posisi saat ini
const currentNumber = currentPosition[1];    // Angka posisi saat ini
const destinationLetter = destination[0];    // Huruf tujuan
const destinationNumber = destination[1];    // Angka tujuan
```

### 2️⃣ Pengecekan Kondisi
Menggunakan operator logika OR (`||`) untuk memeriksa dua kondisi:
- **Kondisi Pertama**: `currentLetter === destinationLetter` → Kolom sama (pergerakan vertikal)
- **Kondisi Kedua**: `currentNumber === destinationNumber` → Baris sama (pergerakan horizontal)

### 3️⃣ Return Hasil
- Jika salah satu kondisi terpenuhi → `return true`
- Jika tidak ada kondisi yang terpenuhi → `return false`

---

## 📊 Visualisasi Grid (Papan Catur)

Berikut contoh visualisasi menggunakan notasi papan catur:

```
     A   B   C   D   E
   +---+---+---+---+---+
 5 | 🚢|   |   |   | 🎯|  ← Baris 5 (horizontal)
   +---+---+---+---+---+
 4 |   |   | ⚓|   |   |
   +---+---+---+---+---+
 3 |   |   | 🏴|   |   |  ← Kolom C (vertikal dengan ⚓)
   +---+---+---+---+---+
 2 |   |   |   |   |   |
   +---+---+---+---+---+
 1 |   |   |   |   |   |
   +---+---+---+---+---+
```

| Simbol | Posisi | Tujuan | Hasil | Alasan |
|--------|--------|--------|-------|--------|
| 🚢 → 🎯 | ['A', 5] | ['E', 5] | ✅ `true` | Berada di baris yang sama (baris 5) |
| ⚓ → 🏴 | ['C', 4] | ['C', 3] | ✅ `true` | Berada di kolom yang sama (kolom C) |
| 🚢 → ⚓ | ['A', 5] | ['C', 4] | ❌ `false` | Tidak di baris atau kolom yang sama |

---

## 🔍 Contoh Penggunaan

### Contoh 1: Pergerakan Horizontal (Baris Sama) ✅

```javascript
const posisiSekarang = ['B', 3];
const tujuan = ['F', 3];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: true
// Penjelasan: Berada di baris yang sama (baris 3), kolom berbeda (B → F)
// Pergerakan: Horizontal dari kolom B ke kolom F
```

### Contoh 2: Pergerakan Vertikal (Kolom Sama) ✅

```javascript
const posisiSekarang = ['D', 1];
const tujuan = ['D', 8];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: true
// Penjelasan: Berada di kolom yang sama (kolom D), baris berbeda (1 → 8)
// Pergerakan: Vertikal dari baris 1 ke baris 8
```

### Contoh 3: Pergerakan Diagonal ❌

```javascript
const posisiSekarang = ['A', 1];
const tujuan = ['C', 3];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: false
// Penjelasan: Kolom berbeda (A ≠ C) DAN baris berbeda (1 ≠ 3)
// Pergerakan: Diagonal (tidak diperbolehkan)
```

### Contoh 4: Posisi yang Sama ✅

```javascript
const posisiSekarang = ['E', 5];
const tujuan = ['E', 5];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: true
// Penjelasan: Kolom DAN baris sama (posisi identik)
// Kapal sudah berada di tujuan
```

### Contoh 5: Notasi Catur Real ♟️

```javascript
// Seperti pergerakan Rook (Benteng) di catur
const rookPosition = ['H', 1];
const targetSquare = ['H', 8];

const canRookMove = navigateOcean(rookPosition, targetSquare);
console.log(canRookMove); 
// Output: true
// Penjelasan: Benteng dapat bergerak vertikal dari H1 ke H8
```

---

## 🎮 Use Case & Implementasi

### 1. Permainan Catur ♟️
```javascript
// Validasi pergerakan Rook (Benteng)
function isValidRookMove(from, to) {
  return navigateOcean(from, to);
}

console.log(isValidRookMove(['A', 1], ['A', 8])); // true - vertikal
console.log(isValidRookMove(['A', 1], ['H', 1])); // true - horizontal
console.log(isValidRookMove(['A', 1], ['B', 2])); // false - diagonal
```

### 2. Battleship (Perang Kapal) 🚢
```javascript
// Pengecekan penempatan kapal (harus lurus)
function isValidShipPlacement(startPos, endPos) {
  return navigateOcean(startPos, endPos);
}

console.log(isValidShipPlacement(['A', 1], ['A', 5])); // true - kapal vertikal
console.log(isValidShipPlacement(['B', 3], ['E', 3])); // true - kapal horizontal
```

### 3. Grid Navigation System 🗺️
```javascript
// Sistem navigasi berbasis grid
function canMoveInOneLine(current, target) {
  if (navigateOcean(current, target)) {
    console.log(`✅ Dapat bergerak lurus dari ${current} ke ${target}`);
    return true;
  } else {
    console.log(`❌ Perlu bergerak diagonal atau memutar dari ${current} ke ${target}`);
    return false;
  }
}
```

---

## 🔄 Perbandingan dengan Versi Ringkas

### Versi Saat Ini (Eksplisit)
```javascript
function navigateOcean(currentPosition, destination) {
  const currentLetter = currentPosition[0];
  const currentNumber = currentPosition[1];
  const destinationLetter = destination[0];
  const destinationNumber = destination[1];
  
  if (currentLetter === destinationLetter || currentNumber === destinationNumber) {
    return true;
  } else {
    return false;
  }
}
```

**Kelebihan:**
- ✅ Mudah dibaca dan dipahami pemula
- ✅ Nama variabel jelas dan deskriptif
- ✅ Struktur kode terorganisir dengan baik
- ✅ Mudah untuk di-debug

### Versi Ringkas (Alternatif)
```javascript
function navigateOcean(currentPosition, destination) {
  return currentPosition[0] === destination[0] || 
         currentPosition[1] === destination[1];
}
```

**Kelebihan:**
- ✅ Lebih singkat (1 baris)
- ✅ Lebih efisien (tidak perlu variabel tambahan)

---

## ⚠️ Catatan Penting

### ⚡ Hal yang Perlu Diperhatikan:

1. **Format Input**: Fungsi mengharapkan format array `[huruf, angka]`
   ```javascript
   ✅ Benar: ['A', 1], ['B', 5], ['H', 8]
   ❌ Salah: [1, 'A'], 'A1', {col: 'A', row: 1}
   ```

2. **Case Sensitivity**: Huruf bersifat case-sensitive
   ```javascript
   ['A', 1] ≠ ['a', 1]  // 'A' dan 'a' dianggap berbeda
   ```

3. **Tipe Data**: Angka bisa berupa number atau string
   ```javascript
   ['A', 1] vs ['A', '1']  // Keduanya berbeda!
   ```

4. **Tidak Memeriksa Rintangan**: Fungsi hanya mengecek jalur lurus, bukan validasi lengkap
   ```javascript
   // Tidak memeriksa apakah ada obstacle di tengah jalur
   navigateOcean(['A', 1], ['A', 8]); // true, tapi mungkin ada penghalang
   ```

5. **Tidak Validasi Batas**: Tidak mengecek apakah koordinat valid
   ```javascript
   navigateOcean(['Z', 99], ['Z', 100]); // true, walaupun di luar papan
   ```

---

## 🚀 Pengembangan Lebih Lanjut

### 1. Tambahan Validasi Input
```javascript
function navigateOceanWithValidation(currentPosition, destination) {
  // Validasi format input
  if (!Array.isArray(currentPosition) || !Array.isArray(destination)) {
    throw new Error('Input harus berupa array!');
  }
  
  if (currentPosition.length !== 2 || destination.length !== 2) {
    throw new Error('Array harus memiliki 2 elemen [huruf, angka]!');
  }
  
  // Ekstraksi koordinat
  const currentLetter = currentPosition[0];
  const currentNumber = currentPosition[1];
  const destinationLetter = destination[0];
  const destinationNumber = destination[1];
  
  // Pengecekan jalur lurus
  if (currentLetter === destinationLetter || currentNumber === destinationNumber) {
    return true;
  } else {
    return false;
  }
}
```

### 2. Dengan Pengecekan Batas Papan
```javascript
function navigateOceanWithBounds(currentPosition, destination) {
  const validLetters = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H'];
  const validNumbers = [1, 2, 3, 4, 5, 6, 7, 8];
  
  const currentLetter = currentPosition[0];
  const currentNumber = currentPosition[1];
  const destinationLetter = destination[0];
  const destinationNumber = destination[1];
  
  // Cek apakah koordinat valid
  const isValid = validLetters.includes(currentLetter) &&
                  validLetters.includes(destinationLetter) &&
                  validNumbers.includes(currentNumber) &&
                  validNumbers.includes(destinationNumber);
  
  if (!isValid) {
    return false; // Koordinat di luar papan
  }
  
  // Cek jalur lurus
  if (currentLetter === destinationLetter || currentNumber === destinationNumber) {
    return true;
  } else {
    return false;
  }
}
```

### 3. Dengan Informasi Arah Pergerakan
```javascript
function navigateOceanWithDirection(currentPosition, destination) {
  const currentLetter = currentPosition[0];
  const currentNumber = currentPosition[1];
  const destinationLetter = destination[0];
  const destinationNumber = destination[1];
  
  // Sama kolom - pergerakan vertikal
  if (currentLetter === destinationLetter) {
    const direction = currentNumber < destinationNumber ? 'ke atas' : 'ke bawah';
    return { 
      canMove: true, 
      type: 'vertical',
      direction: direction
    };
  }
  
  // Sama baris - pergerakan horizontal
  if (currentNumber === destinationNumber) {
    const direction = currentLetter < destinationLetter ? 'ke kanan' : 'ke kiri';
    return { 
      canMove: true, 
      type: 'horizontal',
      direction: direction
    };
  }
  
  // Diagonal atau tidak terhubung
  return { 
    canMove: false, 
    type: 'diagonal',
    direction: null
  };
}

// Contoh penggunaan:
const result = navigateOceanWithDirection(['A', 1], ['A', 5]);
console.log(result); 
// Output: { canMove: true, type: 'vertical', direction: 'ke atas' }
```

---

## 📚 Referensi

- [MDN - Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [MDN - Array Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
- [MDN - Logical OR (||)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR)
- [MDN - Strict Equality (===)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality)
- [MDN - if...else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
- [Chess Notation](https://en.wikipedia.org/wiki/Algebraic_notation_(chess))

---

## 💬 FAQ (Frequently Asked Questions)

### Q: Apakah fungsi ini bisa digunakan untuk papan dengan ukuran berbeda?
**A:** Ya, fungsi ini bekerja untuk papan dengan ukuran apapun karena tidak ada batasan hardcoded. Namun, Anda perlu menambahkan validasi jika ingin membatasi ukuran papan tertentu.

### Q: Bagaimana jika ingin mengecek pergerakan diagonal?
**A:** Fungsi ini sengaja dirancang hanya untuk pergerakan lurus (horizontal/vertikal). Untuk diagonal, Anda perlu membuat fungsi terpisah atau memodifikasi logikanya.

### Q: Apakah huruf harus kapital?
**A:** Ya, karena menggunakan strict equality (`===`), huruf 'A' berbeda dengan 'a'. Jika ingin case-insensitive, gunakan `.toLowerCase()` atau `.toUpperCase()` pada huruf sebelum perbandingan.

### Q: Kenapa menggunakan variabel terpisah untuk setiap komponen?
**A:** Untuk meningkatkan readability (keterbacaan) kode. Nama variabel yang deskriptif seperti `currentLetter` dan `destinationNumber` membuat kode lebih mudah dipahami dibanding langsung mengakses `currentPosition[0]`.

---

<div align="center">

**🌊 Selamat Berlayar dengan Code yang Rapi! ⛵**

---

Dibuat dengan ❤️ untuk pembelajaran pemrograman JavaScript

**[⬆ Kembali ke Atas](#-dokumentasi-fungsi-navigateocean)**

</div>
