# 🏆 Dokumentasi Fungsi `formatPlacards`

## 📋 Deskripsi

Fungsi `formatPlacards` adalah sebuah utility function yang digunakan untuk mengubah array nama-nama peserta menjadi format placard (papan nama) yang seragam. Fungsi ini akan mengkonversi setiap nama menjadi format "Competitor: NAMA" dengan semua huruf nama diubah menjadi huruf kapital (uppercase).

## 🔧 Sintaks

```javascript
formatPlacards(names)
```

## 📥 Parameter

| Parameter | Tipe    | Wajib | Deskripsi                                    |
|-----------|---------|-------|----------------------------------------------|
| `names`   | Array   | ✅    | Array berisi nama-nama peserta (string)     |

### Detail Parameter:

- **`names`**: Sebuah array yang berisi string nama-nama peserta yang akan diformat menjadi placard

## 📤 Return Value

- **Tipe**: `Array`
- **Deskripsi**: Array baru yang berisi string dengan format "Competitor: NAMA_KAPITAL"

## 💻 Kode Fungsi

```javascript
function formatPlacards(names) {
  // Menggunakan map untuk mengubah setiap nama dalam array
  return names.map(name => {
    // Mengubah nama menjadi huruf kapital dan menambahkan prefix "Competitor: "
    return `Competitor: ${name.toUpperCase()}`;
  });
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Array dengan beberapa nama

```javascript
const peserta = ["Alice", "Bob", "Charlie"];
const hasilPlacard = formatPlacards(peserta);

console.log(hasilPlacard);
```

**Output:**
```javascript
["Competitor: ALICE", "Competitor: BOB", "Competitor: CHARLIE"]
```

### Contoh 2: Array dengan nama campuran huruf besar-kecil

```javascript
const namaPeserta = ["john doe", "JANE SMITH", "pEtEr PaRkEr"];
const placardFormat = formatPlacards(namaPeserta);

console.log(placardFormat);
```

**Output:**
```javascript
["Competitor: JOHN DOE", "Competitor: JANE SMITH", "Competitor: PETER PARKER"]
```

### Contoh 3: Array kosong

```javascript
const namaKosong = [];
const hasil = formatPlacards(namaKosong);

console.log(hasil);
```

**Output:**
```javascript
[]
```

## ✨ Fitur Utama

- 🔄 **Transformasi Array**: Mengubah setiap elemen dalam array
- 🔤 **Konversi Uppercase**: Semua nama diubah menjadi huruf kapital
- 🏷️ **Format Konsisten**: Menambahkan prefix "Competitor: " pada setiap nama
- ⚡ **Non-destructive**: Tidak mengubah array asli, melainkan mengembalikan array baru

## 🎯 Kegunaan

Fungsi ini sangat berguna untuk:

- **Event Olahraga**: Membuat placard nama peserta untuk kompetisi
- **Konferensi**: Format name tag yang seragam untuk peserta
- **Kompetisi**: Standardisasi tampilan nama peserta
- **Sistem Pendaftaran**: Format display nama yang konsisten

## ⚠️ Catatan Penting

- Fungsi ini mengharapkan parameter berupa array yang berisi string
- Jika ada elemen array yang bukan string, method `toUpperCase()` mungkin akan error
- Array asli tidak akan dimodifikasi (immutable operation)

## 🔍 Cara Kerja

1. Fungsi menerima array `names` sebagai parameter
2. Menggunakan method `map()` untuk iterasi setiap elemen
3. Untuk setiap nama, fungsi akan:
   - Mengubah nama menjadi huruf kapital dengan `toUpperCase()`
   - Menambahkan prefix "Competitor: " di depan nama
   - Menggabungkan keduanya menggunakan template literal
4. Mengembalikan array baru dengan format yang sudah diubah
