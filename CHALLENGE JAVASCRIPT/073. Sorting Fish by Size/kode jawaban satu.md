# 🐟 Dokumentasi Fungsi `sortFishBySize`

## 📋 Deskripsi

Fungsi `sortFishBySize` adalah sebuah fungsi JavaScript yang digunakan untuk mengurutkan daftar ikan berdasarkan ukuran dari yang terkecil hingga yang terbesar. Fungsi ini menggunakan sistem scoring internal untuk menentukan ukuran relatif setiap jenis ikan.

## 🔧 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `fishList` | Array | Ya | Array berisi nama-nama ikan dalam bentuk string yang akan diurutkan |

## 🐠 Tabel Ukuran Ikan

Fungsi ini menggunakan sistem scoring berikut untuk menentukan ukuran ikan:

| Nama Ikan | Score | Ukuran Relatif |
|-----------|-------|----------------|
| Sardine | 1 | Terkecil |
| Trout | 2 | Kecil |
| Salmon | 3 | Sedang |
| Tuna | 4 | Terbesar |

## 💻 Kode Fungsi

```javascript
function sortFishBySize(fishList) {
  // Objek yang berisi mapping nama ikan dengan ukuran relatifnya
  const fishSizes = {
    "Sardine": 1,   // Sardine adalah ikan terkecil
    "Trout": 2,     // Trout berukuran kecil
    "Salmon": 3,    // Salmon berukuran sedang
    "Tuna": 4       // Tuna adalah ikan terbesar
  };
  
  // Mengurutkan array fishList berdasarkan ukuran ikan
  // Menggunakan method sort() dengan callback function untuk membandingkan
  return fishList.sort((a, b) => fishSizes[a] - fishSizes[b]);
}
```

## ⚡ Cara Penggunaan

```javascript
// Contoh penggunaan fungsi
const daftarIkan = ["Tuna", "Sardine", "Salmon", "Trout"];
const ikanTerurut = sortFishBySize(daftarIkan);
console.log(ikanTerurut);
```

## 📤 Contoh Output

### Input:
```javascript
["Tuna", "Sardine", "Salmon", "Trout"]
```

### Output:
```javascript
["Sardine", "Trout", "Salmon", "Tuna"]
```

### Contoh Lainnya:

**Input:** `["Salmon", "Sardine", "Tuna"]`  
**Output:** `["Sardine", "Salmon", "Tuna"]`

**Input:** `["Trout", "Trout", "Sardine"]`  
**Output:** `["Sardine", "Trout", "Trout"]`

## ⚠️ Catatan Penting

1. **Case Sensitive**: Nama ikan harus ditulis dengan huruf kapital yang tepat (contoh: "Sardine", bukan "sardine")
2. **Ikan yang Tidak Dikenal**: Jika ada nama ikan yang tidak ada dalam objek `fishSizes`, akan menghasilkan `undefined` dan mungkin menyebabkan error
3. **Mutasi Array**: Fungsi ini akan mengubah array asli. Jika Anda ingin mempertahankan array asli, buat salinan terlebih dahulu:

```javascript
const ikanAsli = ["Tuna", "Sardine"];
const ikanTerurut = sortFishBySize([...ikanAsli]); // Menggunakan spread operator
```

## 🎯 Use Case

Fungsi ini berguna untuk:
- Aplikasi perikanan yang perlu mengurutkan hasil tangkapan
- Game fishing yang perlu sorting berdasarkan ukuran ikan
- Aplikasi edukasi tentang jenis-jenis ikan
- Sistem inventory toko ikan

## 🔄 Return Value

**Tipe:** `Array`  
**Deskripsi:** Array yang berisi nama-nama ikan yang sudah diurutkan dari ukuran terkecil ke terbesar

---

*Dibuat untuk memudahkan pemahaman fungsi sorting ikan berdasarkan ukuran* 🐟✨
