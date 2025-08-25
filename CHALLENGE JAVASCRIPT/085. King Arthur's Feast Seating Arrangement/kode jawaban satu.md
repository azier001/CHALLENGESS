# 🍷 Dokumentasi Fungsi `feastArrangement`

## 📋 Deskripsi

Fungsi `feastArrangement` adalah fungsi JavaScript yang digunakan untuk membuat pengaturan tempat duduk dalam sebuah perjamuan ksatria. Fungsi ini akan mengatur posisi ksatria dan anggur secara bergantian, dimana setiap ksatria dipisahkan oleh anggur (kecuali ksatria terakhir).

## 🔧 Sintaks

```javascript
feastArrangement(numKnights)
```

## 📝 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `numKnights` | `number` | ✅ | Jumlah ksatria yang akan menghadiri perjamuan |

## ↩️ Return Value

- **Tipe**: `Array`
- **Deskripsi**: Array yang berisi pengaturan tempat duduk dengan elemen "knight" dan "wine"

## 🎭 Karakter dalam Pengaturan

| Karakter | Deskripsi |
|----------|-----------|
| `"knight"` | Mewakili posisi tempat duduk ksatria |
| `"wine"` | Mewakili posisi anggur sebagai pemisah antar ksatria |

## 💻 Kode Fungsi

```javascript
function feastArrangement(numKnights) {
  // Inisialisasi array kosong untuk menyimpan pengaturan tempat duduk
  const seatingArrangement = [];
  
  // Loop untuk setiap ksatria
  for (let i = 0; i < numKnights; i++) {
    // Tambahkan ksatria ke dalam pengaturan
    seatingArrangement.push("knight");
    
    // Tambahkan anggur sebagai pemisah (kecuali untuk ksatria terakhir)
    if (i < numKnights - 1) {
      seatingArrangement.push("wine");
    }
  }
  
  // Kembalikan pengaturan tempat duduk
  return seatingArrangement;
}
```

## 📊 Contoh Penggunaan dan Output

### Contoh 1: 1 Ksatria
```javascript
console.log(feastArrangement(1));
// Output: ["knight"]
```

### Contoh 2: 2 Ksatria
```javascript
console.log(feastArrangement(2));
// Output: ["knight", "wine", "knight"]
```

### Contoh 3: 3 Ksatria
```javascript
console.log(feastArrangement(3));
// Output: ["knight", "wine", "knight", "wine", "knight"]
```

### Contoh 4: 5 Ksatria
```javascript
console.log(feastArrangement(5));
// Output: ["knight", "wine", "knight", "wine", "knight", "wine", "knight", "wine", "knight"]
```

## 🔍 Cara Kerja

1. **Inisialisasi**: Membuat array kosong `seatingArrangement` untuk menyimpan hasil pengaturan
2. **Iterasi**: Loop melalui setiap ksatria dari 0 hingga `numKnights - 1`
3. **Penambahan Ksatria**: Pada setiap iterasi, tambahkan string "knight" ke array
4. **Penambahan Anggur**: Jika bukan ksatria terakhir, tambahkan string "wine" sebagai pemisah
5. **Return**: Mengembalikan array yang berisi pengaturan lengkap

## ⚠️ Catatan Penting

- Fungsi ini tidak melakukan validasi input, pastikan parameter `numKnights` adalah bilangan positif
- Jika `numKnights` adalah 0 atau negatif, fungsi akan mengembalikan array kosong
- Anggur hanya ditempatkan di antara ksatria, tidak di awal atau akhir pengaturan

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- Simulasi pengaturan tempat duduk dalam game strategy
- Membuat pola berselang-seling dalam aplikasi
- Educational purpose untuk memahami konsep loop dan array manipulation
- Template untuk pengaturan elemen dengan pola tertentu
