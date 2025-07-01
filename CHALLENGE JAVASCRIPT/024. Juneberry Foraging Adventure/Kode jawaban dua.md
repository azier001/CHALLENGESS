# 🍇 Dokumentasi Fungsi Petualangan Juneberry

## 📖 Penjelasan Singkat

Fungsi `countJuneberries` adalah sebuah simulasi petualangan mencari buah Juneberry. Bayangkan kamu adalah Charlie yang sedang berjalan-jalan di sepanjang deretan semak untuk mengumpulkan buah, tapi tas kamu punya batas maksimal!

---

## 🎯 Cara Menggunakan Fungsi

```javascript
countJuneberries(deretanSemak, maksimalBuah)
```

### Parameter (Input yang Dibutuhkan)

| Nama Parameter | Tipe Data | Penjelasan |
|----------------|-----------|------------|
| `bushRow` | `string` (teks) | Deretan semak yang diwakili oleh huruf-huruf. Huruf `'J'` = buah Juneberry, huruf lain = daun atau ranting |  
| `maxBerries` | `number` (angka) | Jumlah maksimal buah yang bisa dibawa (kapasitas tas) |

### Output (Hasil yang Dikembalikan)

Fungsi ini akan mengembalikan **teks** berupa pesan status yang memberitahu:
- Berapa buah yang ditemukan
- Apakah tas sudah penuh atau masih bisa mencari lagi

---

## 💻 Kode Lengkap

```javascript
function countJuneberries(bushRow, maxBerries) {
    let juneberryCount = 0;
    
    for (let i = 0; i < bushRow.length; i++) {
        if (bushRow[i] === 'J') {
            juneberryCount++;
            
            // Check if we've reached our carrying capacity
            if (juneberryCount === maxBerries) {
                return `Found ${juneberryCount} Juneberries. Basket full!`;
            }
        }
    }
    
    // If we've gone through the entire row without reaching maxBerries
    return `Found ${juneberryCount} Juneberries. Keep foraging!`;
}
```

---

## 🔍 Penjelasan Cara Kerja Step by Step

### Langkah 1: Persiapan
```javascript
let juneberryCount = 0;
```
- Membuat variabel `juneberryCount` untuk menghitung buah yang ditemukan
- Dimulai dari 0 (belum ada buah)

### Langkah 2: Menjelajahi Setiap Semak
```javascript
for (let i = 0; i < bushRow.length; i++) {
```
- Loop (perulangan) untuk memeriksa setiap huruf dalam `bushRow`
- Seperti berjalan dari semak pertama sampai semak terakhir

### Langkah 3: Cek Apakah Ada Buah
```javascript
if (bushRow[i] === 'J') {
    juneberryCount++;
```
- Jika huruf yang diperiksa adalah `'J'`, berarti ketemu buah!
- Tambahkan 1 ke penghitung buah

### Langkah 4: Cek Apakah Tas Sudah Penuh
```javascript
if (juneberryCount === maxBerries) {
    return `Found ${juneberryCount} Juneberries. Basket full!`;
}
```
- Jika buah yang dikumpulkan sudah sama dengan batas maksimal
- Langsung berhenti dan bilang "Tas penuh!"

### Langkah 5: Hasil Akhir
```javascript
return `Found ${juneberryCount} Juneberries. Keep foraging!`;
```
- Jika sudah selesai memeriksa semua semak tapi tas belum penuh
- Bilang "Masih bisa cari lagi!"

---

## 🎮 Contoh Penggunaan

### Contoh 1: Tas Penuh
```javascript
countJuneberries("JlJbJrJaJn", 3);
// Hasil: "Found 3 Juneberries. Basket full!"
```

**Penjelasan:**
- Ada 5 buah `'J'` dalam string "JlJbJrJaJn"
- Tapi tas hanya muat 3 buah
- Jadi berhenti setelah mengumpulkan 3 buah pertama

### Contoh 2: Masih Bisa Cari Lagi
```javascript
countJuneberries("JlbJrJan", 5);
// Hasil: "Found 3 Juneberries. Keep foraging!"
```

**Penjelasan:**
- Ada 3 buah `'J'` dalam string "JlbJrJan"
- Tas bisa muat 5 buah
- Jadi masih bisa mencari 2 buah lagi

### Contoh 3: Tidak Ada Buah
```javascript
countJuneberries("", 5);
// Hasil: "Found 0 Juneberries. Keep foraging!"
```

**Penjelasan:**
- String kosong berarti tidak ada semak untuk diperiksa
- Tidak ketemu buah sama sekali
- Harus cari tempat lain

---

## 📝 Catatan Penting

### ⚠️ Yang Perlu Diingat:
- **Case Sensitive**: Hanya huruf `'J'` besar yang dihitung sebagai buah, bukan `'j'` kecil
- **Berhenti Otomatis**: Fungsi akan berhenti begitu tas penuh, tidak akan melanjutkan memeriksa semak berikutnya
- **String Kosong**: Jika tidak ada semak (`""`), hasilnya pasti 0 buah

### 🎯 Tujuan Pembelajaran:
Fungsi ini membantu belajar konsep:
- **Loop/Perulangan**: Bagaimana memeriksa setiap elemen dalam string
- **Conditional**: Bagaimana membuat keputusan berdasarkan kondisi
- **String Processing**: Bagaimana bekerja dengan teks
- **Early Return**: Bagaimana menghentikan fungsi di tengah jalan

---

## 🏆 Tips untuk Pemula

1. **Coba Ubah Parameter**: Eksperimen dengan string dan angka yang berbeda
2. **Trace Manual**: Ikuti langkah demi langkah apa yang dilakukan fungsi
3. **Debug dengan Console**: Gunakan `console.log()` untuk melihat nilai variabel
4. **Variasi String**: Coba dengan huruf J di posisi berbeda

Selamat belajar coding! 🚀
