# 🏖️ Dokumentasi Fungsi `sunnyBeachDay`

## 📋 Deskripsi

Fungsi `sunnyBeachDay` adalah sebuah fungsi JavaScript yang mensimulasikan pengaturan kerang-kerang di pantai berdasarkan posisi matahari. Fungsi ini melakukan beberapa transformasi pada array kerang:

1. **Membalik urutan** kerang di kiri dan kanan posisi matahari
2. **Memindahkan** kerang di posisi matahari ke posisi terakhir
3. **Mengubah** semua kerang bernilai 3 menjadi 2
4. **Mengurutkan** dengan menempatkan semua kerang bernilai 5 di depan

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
    // Ambil kerang di sebelah kiri posisi matahari dan balik urutannya
    const left = seashells.slice(0, sunPosition).reverse();
    
    // Ambil kerang yang berada di posisi matahari
    const middle = seashells[sunPosition];
    
    // Ambil kerang di sebelah kanan posisi matahari dan balik urutannya  
    const right = seashells.slice(sunPosition + 1).reverse();
    
    // Gabungkan kerang kiri, kanan, lalu kerang tengah di akhir
    let arranged = [...left, ...right, middle];
    
    // Ubah semua kerang bernilai 3 menjadi 2 (transformasi kerang ajaib)
    arranged = arranged.map(shell => (shell === 3 ? 2 : shell));
    
    // Pisahkan kerang emas (nilai 5) dan kerang lainnya
    const fives = arranged.filter(shell => shell === 5);
    const others = arranged.filter(shell => shell !== 5);
    
    // Kembalikan dengan kerang emas di depan, diikuti kerang lainnya
    return [...fives, ...others];
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

**Output:** `[5, 2, 1, 4, 2]`

**Penjelasan langkah demi langkah:**
1. Array awal: `[1, 2, 3, 4, 5]`, posisi matahari: `2` (kerang bernilai 3)
2. Kiri dari posisi 2: `[1, 2]` → dibalik: `[2, 1]`
3. Tengah: `3`
4. Kanan dari posisi 2: `[4, 5]` → dibalik: `[5, 4]`
5. Gabung: `[2, 1, 5, 4, 3]`
6. Ubah 3 menjadi 2: `[2, 1, 5, 4, 2]`
7. Kerang emas (5): `[5]`
8. Kerang lainnya: `[2, 1, 4, 2]`
9. Hasil akhir: `[5, 2, 1, 4, 2]`

### Contoh 2: Dengan Kerang Emas di Tengah
```javascript
const kerang = [1, 4, 5, 2, 3];
const posisiMatahari = 2;

const hasil = sunnyBeachDay(kerang, posisiMatahari);
console.log(hasil);
```

**Output:** `[4, 1, 3, 2]`

### Contoh 3: Posisi Matahari di Awal
```javascript
const kerang = [3, 1, 2, 5, 4];
const posisiMatahari = 0;

const hasil = sunnyBeachDay(kerang, posisiMatahari);
console.log(hasil);
```

**Output:** `[5, 4, 2, 1, 2]`

## ⚠️ Catatan Penting

- **Indeks dimulai dari 0**: Posisi matahari menggunakan sistem indeks JavaScript (0, 1, 2, ...)
- **Kerang ajaib berubah**: Semua kerang bernilai 3 akan berubah menjadi 2
- **Prioritas kerang emas**: Kerang bernilai 5 selalu berada di depan hasil akhir
- **Validasi input**: Pastikan `sunPosition` tidak melebihi panjang array

## 🎯 Use Case

Fungsi ini cocok untuk:
- **Game simulation**: Simulasi permainan pantai atau puzzle
- **Array manipulation**: Pembelajaran konsep pengolahan array
- **Algorithm practice**: Latihan algoritma sorting dan filtering
- **Educational purpose**: Mengajarkan konsep transformasi data

---

*Dibuat dengan ❤️ untuk membantu memahami manipulasi array JavaScript*
