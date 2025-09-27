# 📮 Dokumentasi Fungsi `findReversePostcard`

## 📝 Deskripsi

Fungsi `findReversePostcard` adalah sebuah fungsi JavaScript yang digunakan untuk mencari pesan tertentu dalam array kartu pos (postcards) dengan cara membalik urutan array terlebih dahulu, kemudian mencari posisi/indeks dari pesan yang dicari.

Fungsi ini sangat berguna ketika Anda ingin mencari pesan dari urutan terbalik (dari yang terakhir ke yang pertama) dan mendapatkan posisi pesan tersebut dalam array yang sudah dibalik.

## ⚙️ Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|--------|-----------|
| `postcards` | Array | ✅ | Array yang berisi daftar kartu pos atau pesan-pesan |
| `message` | Any | ✅ | Pesan atau nilai yang ingin dicari dalam array |

## 📋 Return Value

- **Tipe**: `number`
- **Nilai**: 
  - Mengembalikan indeks (posisi) dari pesan yang ditemukan dalam array yang sudah dibalik
  - Mengembalikan `-1` jika pesan tidak ditemukan

## 💻 Kode Fungsi

```javascript
function findReversePostcard(postcards, message) {
    // Langkah 1: Membalik urutan array postcards
    const reversedPostcards = postcards.reverse();
    
    // Langkah 2 & 3: Mencari pesan yang ditentukan dan mengembalikan indeksnya
    const index = reversedPostcards.indexOf(message);
    
    // Langkah 4: Mengembalikan indeks jika ditemukan, atau -1 jika tidak ditemukan
    return index;
}
```

## 🎯 Cara Penggunaan

### Contoh 1: Pesan Ditemukan

```javascript
const postcards = ["Halo", "Selamat Pagi", "Apa Kabar", "Sampai Jumpa"];
const result = findReversePostcard(postcards, "Apa Kabar");

console.log(result); 
// Output: 1
```

**Penjelasan**: 
- Array awal: `["Halo", "Selamat Pagi", "Apa Kabar", "Sampai Jumpa"]`
- Array setelah dibalik: `["Sampai Jumpa", "Apa Kabar", "Selamat Pagi", "Halo"]`
- "Apa Kabar" berada di indeks 1 pada array yang sudah dibalik

### Contoh 2: Pesan Tidak Ditemukan

```javascript
const postcards = ["Halo", "Selamat Pagi", "Apa Kabar"];
const result = findReversePostcard(postcards, "Terima Kasih");

console.log(result);
// Output: -1
```

**Penjelasan**: 
- Pesan "Terima Kasih" tidak ada dalam array, sehingga fungsi mengembalikan -1

### Contoh 3: Dengan Data Numerik

```javascript
const numbers = [10, 20, 30, 40, 50];
const result = findReversePostcard(numbers, 30);

console.log(result);
// Output: 2
```

**Penjelasan**:
- Array awal: `[10, 20, 30, 40, 50]`
- Array setelah dibalik: `[50, 40, 30, 20, 10]`
- Angka 30 berada di indeks 2 pada array yang sudah dibalik

## 🔍 Tabel Contoh Output

| Array Awal | Pesan Dicari | Array Setelah Dibalik | Hasil Indeks |
|------------|--------------|----------------------|--------------|
| `["A", "B", "C", "D"]` | "C" | `["D", "C", "B", "A"]` | 1 |
| `["A", "B", "C", "D"]` | "A" | `["D", "C", "B", "A"]` | 3 |
| `["A", "B", "C", "D"]` | "Z" | `["D", "C", "B", "A"]` | -1 |
| `[1, 2, 3, 4, 5]` | 4 | `[5, 4, 3, 2, 1]` | 1 |

## ⚠️ Catatan Penting

1. **Modifikasi Array Original**: Fungsi ini akan **mengubah array asli** karena menggunakan method `reverse()`. Jika Anda tidak ingin array asli berubah, buat salinan array terlebih dahulu.

2. **Saran Perbaikan**: Untuk menghindari modifikasi array asli, gunakan kode berikut:
   ```javascript
   const reversedPostcards = [...postcards].reverse();
   ```

3. **Tipe Data**: Fungsi ini dapat bekerja dengan berbagai tipe data (string, number, boolean, dll.)

4. **Case Sensitive**: Untuk string, pencarian bersifat case-sensitive ("Halo" ≠ "halo")

## 🚀 Tips Penggunaan

- Gunakan fungsi ini ketika Anda perlu mencari elemen dari urutan terbalik
- Cocok untuk implementasi fitur "pencarian dari yang terbaru"
- Berguna untuk log atau riwayat data yang perlu dicari dari entri terbaru
