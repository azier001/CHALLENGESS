# 🔢 Binary Breath Challenge

> **Tingkat Kesulitan:** Easy | **Topik:** Loops & Conditionals

Buat pola binary yang bernapas dengan mengganti '10' dan '01' berdasarkan iterasi genap/ganjil.

---

## 🎯 Tugas

Buat sebuah function `binaryBreath(n)` yang membangun string binary dengan melakukan loop dari 0 hingga n (inclusive). Bayangkan seperti pola pernapasan digital yang berganti antara dua urutan binary.

### Aturan Pola
- **Index genap** (0, 2, 4, ...) → tambahkan `'10'`
- **Index ganjil** (1, 3, 5, ...) → tambahkan `'01'`

### Proses Step-by-Step
1. Inisialisasi variable string kosong `breath`
2. Buat loop yang beriterasi dari `i = 0` sampai `i = n` (inclusive)
3. Untuk setiap iterasi, cek apakah `i` genap atau ganjil
4. Tambahkan pola binary yang sesuai ke string `breath`
5. Return string `breath` yang lengkap

---

## 📊 Visualisasi Pola

Mari kita trace bagaimana pola terbentuk step by step:

```
n=0: 
├─ i=0 (genap) → tambah "10" → hasil: "10"

n=1: 
├─ i=0 (genap) → tambah "10" → saat ini: "10"
└─ i=1 (ganjil) → tambah "01" → hasil: "1001"

n=2: 
├─ i=0 (genap) → tambah "10" → saat ini: "10"
├─ i=1 (ganjil) → tambah "01" → saat ini: "1001"  
└─ i=2 (genap) → tambah "10" → hasil: "100110"

n=3:
├─ i=0 (genap) → tambah "10" → saat ini: "10"
├─ i=1 (ganjil) → tambah "01" → saat ini: "1001"
├─ i=2 (genap) → tambah "10" → saat ini: "100110"
└─ i=3 (ganjil) → tambah "01" → hasil: "10011001"
```

---

## 🧪 Test Cases

```javascript
binaryBreath(0)  // → "10"           (1 iterasi: genap)
binaryBreath(1)  // → "1001"         (2 iterasi: genap + ganjil)  
binaryBreath(2)  // → "100110"       (3 iterasi: genap + ganjil + genap)
binaryBreath(3)  // → "10011001"     (4 iterasi: siklus lengkap)
binaryBreath(4)  // → "1001100110"   (5 iterasi: siklus + genap)
```

### Panjang Pola yang Diharapkan
- Setiap iterasi menambahkan tepat 2 karakter ('10' atau '01')
- Untuk input `n`, hasilnya akan memiliki `(n + 1) × 2` karakter
- Contoh: `n=3` → `(3+1) × 2 = 8` karakter → "10011001" ✓

---

## 💡 Poin Penting

- **Kondisi Loop**: Gunakan `i <= n` untuk menyertakan nilai akhir n dalam loop
- **Cek Genap/Ganjil**: Gunakan operator modulo `i % 2 === 0` untuk genap, `i % 2 !== 0` untuk ganjil
- **Membangun String**: Gunakan operator `+=` untuk concatenation string: `breath += "10"`
- **Logika Pola**: Pergantian '10' dan '01' menciptakan urutan binary yang berirama

### Memahami Logiknya
- **Mengapa '10' untuk genap?** Index genap (0, 2, 4...) merepresentasikan fase "menghirup"
- **Mengapa '01' untuk ganjil?** Index ganjil (1, 3, 5...) merepresentasikan fase "menghembuskan"
- Hasilnya menciptakan pola binary seperti bernapas yang berganti secara konsisten

---

> **Siap untuk coding?** Ingat: angka genap dapat '10', angka ganjil dapat '01'! 💻
