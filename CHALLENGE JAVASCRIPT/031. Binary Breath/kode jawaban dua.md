# 🌬️ Fungsi binaryBreath

## 📋 Deskripsi

Fungsi `binaryBreath` adalah sebuah fungsi JavaScript yang menghasilkan pola string biner berdasarkan nilai input. Fungsi ini bekerja dengan cara mengiterasi dari 0 hingga nilai `n`, kemudian menambahkan pola karakter '10' atau '01' berdasarkan apakah indeks tersebut genap atau ganjil.

## 🔧 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `n` | Number | ✅ | Nilai batas atas untuk iterasi (dari 0 hingga n) |

## 💻 Code Asli

```javascript
function binaryBreath(n) {
    let breath = '';
    
    for (let i = 0; i <= n; i++) {
        if (i % 2 === 0) {
            breath += '10';
        } else {
            breath += '01';
        }
    }
    
    return breath;
}
```

## 🎯 Cara Kerja

1. **Inisialisasi**: Fungsi membuat variabel `breath` sebagai string kosong
2. **Iterasi**: Loop dari `i = 0` hingga `i = n` (inklusif)
3. **Pengecekan**: Untuk setiap `i`:
   - Jika `i` **genap** (i % 2 === 0) → tambahkan '**10**'
   - Jika `i` **ganjil** (i % 2 !== 0) → tambahkan '**01**'
4. **Return**: Mengembalikan string hasil gabungan

## 📊 Tabel Pola Karakter

| Indeks (i) | Kondisi | Karakter Ditambah | Keterangan |
|------------|---------|-------------------|------------|
| 0 | Genap | '10' | i % 2 === 0 |
| 1 | Ganjil | '01' | i % 2 !== 0 |
| 2 | Genap | '10' | i % 2 === 0 |
| 3 | Ganjil | '01' | i % 2 !== 0 |
| 4 | Genap | '10' | i % 2 === 0 |

## 🚀 Contoh Penggunaan & Output

### Contoh 1: Input kecil
```javascript
console.log(binaryBreath(2));
// Output: "101001"
```

**Penjelasan step-by-step:**
- i=0 (genap) → tambah '10' → "10"
- i=1 (ganjil) → tambah '01' → "1001"  
- i=2 (genap) → tambah '10' → "101001"

### Contoh 2: Input sedang
```javascript
console.log(binaryBreath(4));
// Output: "1010011010"
```

**Penjelasan step-by-step:**
- i=0 (genap) → "10"
- i=1 (ganjil) → "1001"
- i=2 (genap) → "100110"
- i=3 (ganjil) → "10011001"
- i=4 (genap) → "1010011010"

### Contoh 3: Input minimal
```javascript
console.log(binaryBreath(0));
// Output: "10"
```

### Contoh 4: Input negatif
```javascript
console.log(binaryBreath(-1));
// Output: ""
```
*Karena loop tidak akan berjalan jika n < 0*

## 📈 Analisis Panjang Output

| Input (n) | Jumlah Iterasi | Panjang Output | Formula |
|-----------|----------------|----------------|---------|
| 0 | 1 | 2 | (n+1) × 2 |
| 1 | 2 | 4 | (n+1) × 2 |
| 2 | 3 | 6 | (n+1) × 2 |
| 3 | 4 | 8 | (n+1) × 2 |
| 4 | 5 | 10 | (n+1) × 2 |

## ⚠️ Catatan Penting

- Fungsi ini akan melakukan `n+1` iterasi (dari 0 hingga n)
- Setiap iterasi menambahkan 2 karakter, sehingga panjang output = `(n+1) × 2`
- Jika `n` adalah bilangan negatif, fungsi akan mengembalikan string kosong
- Pola yang dihasilkan selalu dimulai dengan '10' (karena i=0 adalah genap)

## 🎨 Use Case

Fungsi ini bisa digunakan untuk:
- Membuat pola biner untuk visualisasi
- Simulasi napas digital atau pola hidup-mati
- Generator pola untuk game atau animasi
- Membuat sequence testing untuk aplikasi
