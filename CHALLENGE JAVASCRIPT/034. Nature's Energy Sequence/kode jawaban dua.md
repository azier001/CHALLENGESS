# 🌿 Dokumentasi Fungsi exploreNatureSequence

## 📋 Deskripsi Fungsi

Fungsi `exploreNatureSequence` digunakan untuk menjelajahi urutan elemen alam dan menghitung total energi berdasarkan aturan-aturan tertentu. Fungsi ini akan menganalisis setiap elemen dalam urutan dan memberikan bonus atau penalti energi tergantung pada jenis elemen dan pola yang ditemukan.

## 🎯 Cara Kerja

Fungsi ini bekerja dengan cara:
1. **Bonus Bunga**: Setiap menemukan elemen 'F' (Flower/Bunga), energi bertambah 2 poin
2. **Bonus Kemiripan**: Jika dua elemen yang bersebelahan sama, energi bertambah 1 poin
3. **Penalti Perbedaan**: Jika dua elemen yang bersebelahan berbeda, energi berkurang 1 poin

## 📊 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `sequence` | Array/String | Urutan elemen alam yang akan dijelajahi |
| `energy` | Number | Nilai energi awal yang dimiliki |

## 🎨 Tabel Karakter Elemen

| Karakter | Nama | Deskripsi | Efek Energi |
|----------|------|-----------|-------------|
| `F` | Flower (Bunga) | Elemen bunga yang memberikan energi | +2 energi |
| Lainnya | Elemen Alam | Elemen alam lainnya (pohon, batu, dll) | Tidak ada bonus khusus |

## 💻 Kode Fungsi

```javascript
function exploreNatureSequence(sequence, energy) {
    // Perulangan melalui urutan dimulai dari elemen pertama
    for (let i = 0; i < sequence.length; i++) {
        const currentElement = sequence[i];
        
        // Cek apakah elemen saat ini adalah Bunga dan tambahkan 2 energi
        if (currentElement === 'F') {
            energy += 2;
        }
        
        // Bandingkan dengan elemen selanjutnya jika ada
        if (i < sequence.length - 1) {
            const nextElement = sequence[i + 1];
            
            // Jika elemen yang bersebelahan sama, tambahkan energi 1
            if (currentElement === nextElement) {
                energy += 1;
            }
            // Jika elemen yang bersebelahan berbeda, kurangi energi 1
            else {
                energy -= 1;
            }
        }
    }
    
    return energy;
}
```

## 🧪 Contoh Penggunaan

### Contoh 1: Urutan dengan Bunga
```javascript
const sequence1 = ['F', 'T', 'F', 'F'];
const initialEnergy1 = 10;
const result1 = exploreNatureSequence(sequence1, initialEnergy1);
console.log(result1); // Output: 15
```

**Penjelasan perhitungan:**
- Energi awal: 10
- Elemen 'F' (posisi 0): +2 → Total: 12
- 'F' ≠ 'T': -1 → Total: 11
- Elemen 'T' (posisi 1): +0 → Total: 11
- 'T' ≠ 'F': -1 → Total: 10
- Elemen 'F' (posisi 2): +2 → Total: 12
- 'F' = 'F': +1 → Total: 13
- Elemen 'F' (posisi 3): +2 → Total: 15

### Contoh 2: Urutan tanpa Bunga
```javascript
const sequence2 = ['T', 'T', 'R', 'S'];
const initialEnergy2 = 5;
const result2 = exploreNatureSequence(sequence2, initialEnergy2);
console.log(result2); // Output: 3
```

**Penjelasan perhitungan:**
- Energi awal: 5
- Elemen 'T' (posisi 0): +0 → Total: 5
- 'T' = 'T': +1 → Total: 6
- Elemen 'T' (posisi 1): +0 → Total: 6
- 'T' ≠ 'R': -1 → Total: 5
- Elemen 'R' (posisi 2): +0 → Total: 5
- 'R' ≠ 'S': -1 → Total: 4
- Elemen 'S' (posisi 3): +0 → Total: 4

### Contoh 3: Urutan dengan banyak Bunga bersebelahan
```javascript
const sequence3 = ['F', 'F', 'F'];
const initialEnergy3 = 0;
const result3 = exploreNatureSequence(sequence3, initialEnergy3);
console.log(result3); // Output: 8
```

**Penjelasan perhitungan:**
- Energi awal: 0
- Elemen 'F' (posisi 0): +2 → Total: 2
- 'F' = 'F': +1 → Total: 3
- Elemen 'F' (posisi 1): +2 → Total: 5
- 'F' = 'F': +1 → Total: 6
- Elemen 'F' (posisi 2): +2 → Total: 8

## 🎯 Tips Penggunaan

1. **Posisikan Bunga Strategis**: Letakkan elemen 'F' secara bersebelahan untuk mendapatkan bonus ganda (bonus bunga + bonus kemiripan)

2. **Hindari Pergantian Elemen**: Urutan yang sering berganti-ganti akan mengurangi energi karena penalti perbedaan

3. **Energi Awal Penting**: Pastikan energi awal cukup untuk mengimbangi kemungkinan penalti dari perbedaan elemen

## 🔄 Nilai Kembalian

Fungsi ini mengembalikan nilai `Number` yang merupakan total energi akhir setelah menjelajahi seluruh urutan elemen.

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi exploreNatureSequence dengan mudah dan lengkap.*
