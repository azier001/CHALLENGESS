# 🏆 Fungsi debateWinner

## 📝 Deskripsi

Fungsi `debateWinner` adalah sebuah fungsi JavaScript yang menentukan pemenang debat antara dua sarjana berdasarkan panjang argumen yang mereka berikan. Fungsi ini membandingkan setiap argumen dari kedua sarjana dan memberikan poin kepada sarjana yang memiliki argumen lebih panjang.

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

1. **Inisialisasi Skor**: Kedua sarjana dimulai dengan skor 0
2. **Perbandingan Argumen**: Setiap argumen dibandingkan berdasarkan panjang karakter
3. **Pemberian Poin**: Sarjana dengan argumen lebih panjang mendapat 1 poin
4. **Penentuan Pemenang**: Sarjana dengan total poin tertinggi dinyatakan menang

## 💻 Kode Fungsi

```javascript
function debateWinner(scholar1Arguments, scholar2Arguments) {
    let scholar1Score = 0;
    let scholar2Score = 0;
    
    // Menentukan jumlah maksimum argumen untuk dibandingkan
    const maxArguments = Math.max(scholar1Arguments.length, scholar2Arguments.length);
    
    // Membandingkan argumen satu per satu
    for (let i = 0; i < maxArguments; i++) {
        // Gunakan string kosong jika argumen tidak ada
        const arg1 = scholar1Arguments[i] || "";
        // Gunakan string kosong jika argumen tidak ada
        const arg2 = scholar2Arguments[i] || "";
        
        if (arg1.length > arg2.length) {
            scholar1Score++;
        } else if (arg2.length > arg1.length) {
            scholar2Score++;
        }
        // Jika panjang sama, tidak ada poin yang diberikan
    }
    
    // Menentukan pemenang
    if (scholar1Score > scholar2Score) {
        return "Scholar 1 wins!";
    } else if (scholar2Score > scholar1Score) {
        return "Scholar 2 wins!";
    } else {
        return "It's a tie!";
    }
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Scholar 1 Menang
```javascript
const scholar1Args = [
    "Teknologi AI akan mengubah dunia",
    "Implementasi yang tepat sangat penting",
    "Masa depan teknologi"
];

const scholar2Args = [
    "AI berbahaya",
    "Tidak setuju",
    "Buruk"
];

console.log(debateWinner(scholar1Args, scholar2Args));
// Output: "Scholar 1 wins!"
```

### Contoh 2: Scholar 2 Menang
```javascript
const scholar1Args = [
    "Ya",
    "Benar",
    "OK"
];

const scholar2Args = [
    "Saya tidak setuju dengan pendapat tersebut",
    "Argumen yang sangat lemah dan tidak berdasar",
    "Kesimpulan yang salah total"
];

console.log(debateWinner(scholar1Args, scholar2Args));
// Output: "Scholar 2 wins!"
```

### Contoh 3: Hasil Seri
```javascript
const scholar1Args = [
    "Argumen pertama yang kuat",
    "Pendek"
];

const scholar2Args = [
    "Lemah",
    "Argumen kedua yang sangat panjang"
];

console.log(debateWinner(scholar1Args, scholar2Args));
// Output: "It's a tie!"
```

## 📋 Tabel Perbandingan Contoh

| Contoh | Scholar 1 Poin | Scholar 2 Poin | Hasil |
|--------|----------------|----------------|-------|
| Contoh 1 | 3 | 0 | Scholar 1 wins! |
| Contoh 2 | 0 | 3 | Scholar 2 wins! |
| Contoh 3 | 1 | 1 | It's a tie! |

## ⚠️ Catatan Penting

- Fungsi ini hanya mempertimbangkan **panjang argumen**, bukan kualitas atau substansi argumen
- Jika salah satu array lebih pendek, posisi yang kosong dianggap sebagai string kosong (`""`)
- Argumen dengan panjang yang sama tidak memberikan poin kepada siapa pun
- Fungsi ini case-sensitive dan menghitung semua karakter termasuk spasi

## 🚀 Tips Penggunaan

1. **Validasi Input**: Pastikan kedua parameter adalah array yang valid
2. **Penanganan Edge Case**: Fungsi sudah menangani array dengan panjang berbeda
3. **Performa**: Fungsi memiliki kompleksitas waktu O(n) dimana n adalah jumlah argumen terbanyak
