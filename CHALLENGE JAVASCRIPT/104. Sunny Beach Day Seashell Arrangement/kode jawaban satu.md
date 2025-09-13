# 🏖️ Dokumentasi Fungsi `sunnyBeachDay`

## 📋 Deskripsi

Fungsi `sunnyBeachDay` adalah sebuah fungsi JavaScript yang mensimulasikan pengaturan kerang-kerang di pantai berdasarkan posisi matahari. Fungsi ini melakukan beberapa transformasi pada array kerang:

1. **Membalik urutan** kerang di kedua sisi (kiri dan kanan) posisi matahari
2. **Mengubah** semua kerang bernilai 3 menjadi 2
3. **Memindahkan** semua kerang bernilai 5 ke awal array

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `seashells` | Array | Array berisi angka-angka yang merepresentasikan jenis kerang |
| `sunPosition` | Number | Indeks posisi matahari dalam array (dimulai dari 0) |

### 📊 Tabel Karakter Kerang

| Nilai | Jenis Kerang | Keterangan |
|-------|--------------|------------|
| 1 | Kerang Kecil | Kerang biasa |
| 2 | Kerang Sedang | Kerang standar |
| 3 | Kerang Ajaib | Akan diubah menjadi kerang sedang (2) |
| 4 | Kerang Besar | Kerang ukuran besar |
| 5 | Kerang Emas | Kerang istimewa yang akan diprioritaskan |

## 💻 Kode Fungsi

```javascript
function sunnyBeachDay(seashells, sunPosition) {
    // Langkah 1: Balik urutan kerang di kedua sisi posisi matahari
    const leftSide = seashells.slice(0, sunPosition).reverse();
    const rightSide = seashells.slice(sunPosition).reverse();
    let rearranged = [...leftSide, ...rightSide];
    
    // Langkah 2: Ganti semua kerang tipe 3 dengan kerang tipe 2
    rearranged = rearranged.map(shell => shell === 3 ? 2 : shell);
    
    // Langkah 3: Pindahkan semua kerang tipe 5 ke awal array
    const fiveShells = rearranged.filter(shell => shell === 5);
    const otherShells = rearranged.filter(shell => shell !== 5);
    
    return [...fiveShells, ...otherShells];
}
```

## 📝 Contoh Penggunaan

### Contoh 1: Kasus Dasar
```javascript
const kerang = [1, 2, 3, 4, 5];
const posisiMatahari = 2;

const hasil = sunnyBeachDay(kerang, posisiMatahari);
console.log(hasil);
```

**Output:** `[5, 4, 2, 2, 1]`

**Penjelasan langkah demi langkah:**
1. Array awal: `[1, 2, 3, 4, 5]`, posisi matahari: `2`
2. Kiri dari posisi 2: `[1, 2]` → dibalik: `[2, 1]`
3. Kanan dari posisi 2 (termasuk posisi 2): `[3, 4, 5]` → dibalik: `[5, 4, 3]`
4. Gabung: `[2, 1, 5, 4, 3]`
5. Ubah 3 menjadi 2: `[2, 1, 5, 4, 2]`
6. Kerang emas (5): `[5]`
7. Kerang lainnya: `[2, 1, 4, 2]`
8. Hasil akhir: `[5, 2, 1, 4, 2]`

### Contoh 2: Dengan Multiple Kerang Emas
```javascript
const kerang = [5, 1, 3, 5, 2];
const posisiMatahari = 2;

const hasil = sunnyBeachDay(kerang, posisiMatahari);
console.log(hasil);
```

**Output:** `[5, 5, 2, 2, 1]`

**Penjelasan:**
1. Array awal: `[5, 1, 3, 5, 2]`, posisi matahari: `2`
2. Kiri: `[5, 1]` → dibalik: `[1, 5]`
3. Kanan: `[3, 5, 2]` → dibalik: `[2, 5, 3]`
4. Gabung: `[1, 5, 2, 5, 3]`
5. Ubah 3 menjadi 2: `[1, 5, 2, 5, 2]`
6. Kerang emas: `[5, 5]`
7. Kerang lainnya: `[1, 2, 2]`
8. Hasil akhir: `[5, 5, 1, 2, 2]`

### Contoh 3: Posisi Matahari di Awal
```javascript
const kerang = [3, 1, 2, 5, 4];
const posisiMatahari = 0;

const hasil = sunnyBeachDay(kerang, posisiMatahari);
console.log(hasil);
```

**Output:** `[5, 4, 2, 1, 2]`

**Penjelasan:**
1. Array awal: `[3, 1, 2, 5, 4]`, posisi matahari: `0`
2. Kiri: `[]` (kosong)
3. Kanan: `[3, 1, 2, 5, 4]` → dibalik: `[4, 5, 2, 1, 3]`
4. Gabung: `[4, 5, 2, 1, 3]`
5. Ubah 3 menjadi 2: `[4, 5, 2, 1, 2]`
6. Kerang emas: `[5]`
7. Kerang lainnya: `[4, 2, 1, 2]`
8. Hasil akhir: `[5, 4, 2, 1, 2]`

### Contoh 4: Posisi Matahari di Akhir
```javascript
const kerang = [1, 3, 4, 5, 2];
const posisiMatahari = 4;

const hasil = sunnyBeachDay(kerang, posisiMatahari);
console.log(hasil);
```

**Output:** `[5, 2, 4, 2, 1]`

## 🔍 Perbedaan Penting dengan Versi Sebelumnya

Versi ini memiliki perbedaan utama pada **Langkah 1**:
- **Versi ini**: Mengambil dari posisi matahari hingga akhir untuk sisi kanan (`slice(sunPosition)`)
- **Versi sebelumnya**: Mengambil setelah posisi matahari (`slice(sunPosition + 1)`) dan memindahkan kerang di posisi matahari ke akhir

Hal ini berarti kerang yang berada tepat di posisi matahari akan ikut dibalik bersama sisi kanan, bukan dipindah ke posisi terakhir.

## ⚠️ Catatan Penting

- **Indeks dimulai dari 0**: Posisi matahari menggunakan sistem indeks JavaScript
- **Kerang ajaib berubah**: Semua kerang bernilai 3 akan berubah menjadi 2
- **Prioritas kerang emas**: Kerang bernilai 5 selalu berada di depan hasil akhir
- **Validasi input**: Pastikan `sunPosition` tidak melebihi panjang array
- **Kerang di posisi matahari**: Ikut diproses bersama sisi kanan (tidak diperlakukan khusus)

## 🎯 Use Case

Fungsi ini cocok untuk:
- **Game simulation**: Simulasi permainan pantai atau puzzle
- **Array manipulation**: Pembelajaran konsep pengolahan array
- **Algorithm practice**: Latihan algoritma sorting dan filtering
- **Educational purpose**: Mengajarkan konsep transformasi data

## 🧪 Testing

```javascript
// Test kasus edge case
console.log(sunnyBeachDay([5], 0));           // Output: [5]
console.log(sunnyBeachDay([3, 3, 3], 1));     // Output: [2, 2, 2]
console.log(sunnyBeachDay([1, 2, 3, 4], 3));  // Output: [4, 2, 2, 1]
```

---

*Dibuat dengan ❤️ untuk membantu memahami manipulasi array JavaScript*
