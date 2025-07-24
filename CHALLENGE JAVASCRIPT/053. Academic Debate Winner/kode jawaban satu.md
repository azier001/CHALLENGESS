# 🏆 Fungsi debateWinner

## 📝 Deskripsi

Fungsi `debateWinner` adalah sebuah fungsi JavaScript yang menentukan pemenang debat antara dua sarjana berdasarkan panjang argumen dan jumlah argumen yang mereka berikan. Fungsi ini membandingkan setiap argumen dari kedua sarjana dan memberikan poin kepada sarjana yang memiliki argumen lebih panjang. Jika salah satu sarjana memiliki lebih banyak argumen, sarjana tersebut mendapat poin tambahan untuk setiap argumen ekstra.

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `scholar1Arguments` | Array | Array berisi argumen-argumen dari sarjana pertama (berupa string) |
| `scholar2Arguments` | Array | Array berisi argumen-argumen dari sarjana kedua (berupa string) |

## 🔄 Return Value

Fungsi ini mengembalikan string dengan kemungkinan nilai:
- `"Scholar 1 wins!"` - Jika sarjana 1 memiliki total poin lebih tinggi
- `"Scholar 2 wins!"` - Jika sarjana 2 memiliki total poin lebih tinggi  
- `"It's a tie!"` - Jika kedua sarjana memiliki poin yang sama

## 📊 Cara Kerja

1. **Inisialisasi Poin**: Kedua sarjana dimulai dengan poin 0
2. **Perbandingan Jumlah Argumen**: Menentukan jumlah maksimum argumen dari kedua sarjana
3. **Iterasi dan Pemberian Poin**:
   - Jika sarjana 1 kehabisan argumen, sarjana 2 mendapat poin
   - Jika sarjana 2 kehabisan argumen, sarjana 1 mendapat poin
   - Jika keduanya masih punya argumen, bandingkan panjang karakter
4. **Penentuan Pemenang**: Sarjana dengan total poin tertinggi dinyatakan menang

## 💻 Kode Fungsi

```javascript
function debateWinner(scholar1Arguments, scholar2Arguments) {
    let scholar1Points = 0;
    let scholar2Points = 0;
    
    // Menentukan panjang maksimum dari kedua array argumen
    const maxLength = Math.max(scholar1Arguments.length, scholar2Arguments.length);
    
    // Melakukan iterasi sebanyak argumen terbanyak
    for (let i = 0; i < maxLength; i++) {
        // Jika scholar1 kehabisan argumen, scholar2 mendapat poin
        if (i >= scholar1Arguments.length) {
            scholar2Points++;
        } 
        // Jika scholar2 kehabisan argumen, scholar1 mendapat poin
        else if (i >= scholar2Arguments.length) {
            scholar1Points++;
        } 
        // Jika keduanya masih memiliki argumen, bandingkan panjangnya
        else {
            const arg1Length = scholar1Arguments[i].length;
            const arg2Length = scholar2Arguments[i].length;
            
            // Berikan poin kepada scholar dengan argumen lebih panjang
            if (arg1Length > arg2Length) {
                scholar1Points++;
            } else if (arg2Length > arg1Length) {
                scholar2Points++;
            }
            // Jika panjang sama, tidak ada poin yang diberikan
        }
    }
    
    // Menentukan pemenang berdasarkan total poin
    if (scholar1Points > scholar2Points) {
        return "Scholar 1 wins!";
    } else if (scholar2Points > scholar1Points) {
        return "Scholar 2 wins!";
    } else {
        return "It's a tie!";
    }
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Scholar 1 Menang (Lebih Banyak Argumen)
```javascript
const scholar1Args = [
    "Teknologi AI sangat bermanfaat",
    "Implementasi yang tepat penting",
    "Masa depan cerah dengan AI",
    "Argumen tambahan keempat"
];

const scholar2Args = [
    "AI berbahaya bagi manusia",
    "Tidak setuju dengan pendapat itu"
];

console.log(debateWinner(scholar1Args, scholar2Args));
// Output: "Scholar 1 wins!"
```

### Contoh 2: Scholar 2 Menang (Argumen Lebih Panjang)
```javascript
const scholar1Args = [
    "Ya",
    "Benar",
    "Setuju"
];

const scholar2Args = [
    "Saya sangat tidak setuju dengan pendapat tersebut karena tidak berdasar",
    "Argumen yang sangat lemah dan tidak didukung data yang valid",
    "Kesimpulan yang salah total dan menyesatkan pembaca"
];

console.log(debateWinner(scholar1Args, scholar2Args));
// Output: "Scholar 2 wins!"
```

### Contoh 3: Hasil Seri
```javascript
const scholar1Args = [
    "Argumen pertama yang sangat kuat dan berdasar",
    "Pendek"
];

const scholar2Args = [
    "Lemah",
    "Argumen kedua yang sangat panjang dan detail"
];

console.log(debateWinner(scholar1Args, scholar2Args));
// Output: "It's a tie!"
```

### Contoh 4: Scholar 2 Menang (Kehabisan Argumen)
```javascript
const scholar1Args = [
    "Argumen tunggal"
];

const scholar2Args = [
    "Argumen pertama",
    "Argumen kedua yang lebih panjang",
    "Argumen ketiga untuk kemenangan"
];

console.log(debateWinner(scholar1Args, scholar2Args));
// Output: "Scholar 2 wins!"
```

## 📋 Tabel Perbandingan Contoh

| Contoh | Scholar 1 Args | Scholar 2 Args | Scholar 1 Poin | Scholar 2 Poin | Hasil |
|--------|----------------|----------------|----------------|----------------|-------|
| Contoh 1 | 4 argumen | 2 argumen | 3 | 1 | Scholar 1 wins! |
| Contoh 2 | 3 argumen | 3 argumen | 0 | 3 | Scholar 2 wins! |
| Contoh 3 | 2 argumen | 2 argumen | 1 | 1 | It's a tie! |
| Contoh 4 | 1 argumen | 3 argumen | 0 | 3 | Scholar 2 wins! |

## 📈 Detail Poin Contoh 1
| Index | Scholar 1 | Scholar 2 | Poin Untuk |
|-------|-----------|-----------|------------|
| 0 | "Teknologi AI sangat bermanfaat" (26) | "AI berbahaya bagi manusia" (23) | Scholar 1 |
| 1 | "Implementasi yang tepat penting" (28) | "Tidak setuju dengan pendapat itu" (31) | Scholar 2 |
| 2 | "Masa depan cerah dengan AI" (24) | - (kosong) | Scholar 1 |
| 3 | "Argumen tambahan keempat" (24) | - (kosong) | Scholar 1 |

## ⚠️ Catatan Penting

- Fungsi ini mempertimbangkan **panjang argumen** dan **jumlah argumen**
- Sarjana dengan lebih banyak argumen mendapat keuntungan poin otomatis
- Jika salah satu array lebih pendek, posisi yang kosong memberikan poin kepada lawan
- Argumen dengan panjang yang sama tidak memberikan poin kepada siapa pun
- Fungsi ini case-sensitive dan menghitung semua karakter termasuk spasi

## 🔄 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Lama | Versi Baru |
|-------|------------|------------|
| **Argumen Kosong** | Dianggap string kosong `""` | Memberikan poin langsung ke lawan |
| **Keadilan** | Kurang adil untuk yang punya lebih banyak argumen | Lebih adil, reward untuk jumlah argumen |
| **Logika** | Hanya bandingkan panjang | Bandingkan panjang + jumlah argumen |

## 🚀 Tips Penggunaan

1. **Validasi Input**: Pastikan kedua parameter adalah array yang valid berisi string
2. **Strategi Debat**: Fungsi ini reward baik kualitas (panjang) maupun kuantitas argumen
3. **Performa**: Fungsi memiliki kompleksitas waktu O(n) dimana n adalah jumlah argumen terbanyak
4. **Use Case**: Cocok untuk sistem penilaian debat yang mempertimbangkan kelengkapan argumen
