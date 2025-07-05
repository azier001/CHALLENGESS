# 🌿 Dokumentasi Fungsi exploreNatureSequence

## 📋 Deskripsi Fungsi

Fungsi `exploreNatureSequence` digunakan untuk menjelajahi urutan elemen alam dan menghitung total energi berdasarkan aturan-aturan tertentu. Fungsi ini akan menganalisis setiap elemen dalam urutan dan memberikan bonus atau penalti energi tergantung pada jenis elemen dan pola yang ditemukan.

## 🎯 Cara Kerja

Fungsi ini bekerja dengan cara:
1. **Bonus Bunga**: Setiap menemukan elemen 'F' (Flower/Bunga), energi bertambah 2 poin
2. **Bonus Kemiripan**: Jika elemen saat ini sama dengan elemen sebelumnya, energi bertambah 1 poin
3. **Penalti Perbedaan**: Jika elemen saat ini berbeda dengan elemen sebelumnya, energi berkurang 1 poin

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
  // Perulangan melalui setiap elemen dalam urutan
  for (let i = 0; i < sequence.length; i++) {
    // Cek apakah elemen saat ini adalah Bunga dan tambahkan 2 energi
    if (sequence[i] === 'F') {
      energy += 2;
    }
    // Cek apakah bukan elemen pertama (ada elemen sebelumnya)
    if (i > 0) {
      // Jika elemen saat ini sama dengan elemen sebelumnya, tambahkan 1 energi
      if (sequence[i] === sequence[i - 1]) {
        energy += 1;
      } else {
        // Jika elemen saat ini berbeda dengan elemen sebelumnya, kurangi 1 energi
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
- Elemen 'F' (posisi 0): +2 → Total: 12 (tidak ada perbandingan karena elemen pertama)
- Elemen 'T' (posisi 1): +0, 'T' ≠ 'F': -1 → Total: 11
- Elemen 'F' (posisi 2): +2, 'F' ≠ 'T': -1 → Total: 12
- Elemen 'F' (posisi 3): +2, 'F' = 'F': +1 → Total: 15

### Contoh 2: Urutan tanpa Bunga
```javascript
const sequence2 = ['T', 'T', 'R', 'S'];
const initialEnergy2 = 5;
const result2 = exploreNatureSequence(sequence2, initialEnergy2);
console.log(result2); // Output: 3
```

**Penjelasan perhitungan:**
- Energi awal: 5
- Elemen 'T' (posisi 0): +0 → Total: 5 (tidak ada perbandingan karena elemen pertama)
- Elemen 'T' (posisi 1): +0, 'T' = 'T': +1 → Total: 6
- Elemen 'R' (posisi 2): +0, 'R' ≠ 'T': -1 → Total: 5
- Elemen 'S' (posisi 3): +0, 'S' ≠ 'R': -1 → Total: 4

### Contoh 3: Urutan dengan banyak Bunga bersebelahan
```javascript
const sequence3 = ['F', 'F', 'F'];
const initialEnergy3 = 0;
const result3 = exploreNatureSequence(sequence3, initialEnergy3);
console.log(result3); // Output: 8
```

**Penjelasan perhitungan:**
- Energi awal: 0
- Elemen 'F' (posisi 0): +2 → Total: 2 (tidak ada perbandingan karena elemen pertama)
- Elemen 'F' (posisi 1): +2, 'F' = 'F': +1 → Total: 5
- Elemen 'F' (posisi 2): +2, 'F' = 'F': +1 → Total: 8

### Contoh 4: Urutan dengan pola berganti-ganti
```javascript
const sequence4 = ['F', 'T', 'F', 'T'];
const initialEnergy4 = 8;
const result4 = exploreNatureSequence(sequence4, initialEnergy4);
console.log(result4); // Output: 10
```

**Penjelasan perhitungan:**
- Energi awal: 8
- Elemen 'F' (posisi 0): +2 → Total: 10 (tidak ada perbandingan karena elemen pertama)
- Elemen 'T' (posisi 1): +0, 'T' ≠ 'F': -1 → Total: 9
- Elemen 'F' (posisi 2): +2, 'F' ≠ 'T': -1 → Total: 10
- Elemen 'T' (posisi 3): +0, 'T' ≠ 'F': -1 → Total: 9

## 🔍 Perbedaan Penting

**Versi ini berbeda dari versi sebelumnya karena:**
- Membandingkan elemen saat ini dengan elemen **sebelumnya** (i-1), bukan elemen **selanjutnya** (i+1)
- Elemen pertama (indeks 0) tidak pernah dibandingkan karena tidak ada elemen sebelumnya
- Perbandingan dilakukan pada setiap elemen kecuali elemen pertama

## 🎯 Tips Penggunaan

1. **Posisikan Bunga Strategis**: Letakkan elemen 'F' secara bersebelahan untuk mendapatkan bonus ganda (bonus bunga + bonus kemiripan)

2. **Hindari Pergantian Elemen**: Urutan yang sering berganti-ganti akan mengurangi energi karena penalti perbedaan

3. **Energi Awal Penting**: Pastikan energi awal cukup untuk mengimbangi kemungkinan penalti dari perbedaan elemen

4. **Elemen Pertama Aman**: Elemen pertama hanya memberikan bonus bunga (jika 'F') tanpa penalti perbandingan

## 🔄 Nilai Kembalian

Fungsi ini mengembalikan nilai `Number` yang merupakan total energi akhir setelah menjelajahi seluruh urutan elemen.

## ⚖️ Strategi Optimal

Untuk memaksimalkan energi:
- Mulai dengan elemen yang sama dengan elemen kedua
- Kelompokkan elemen yang sama bersama-sama
- Letakkan bunga ('F') dalam kelompok yang sama
- Hindari pergantian elemen yang tidak perlu

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi exploreNatureSequence dengan mudah dan lengkap.*
