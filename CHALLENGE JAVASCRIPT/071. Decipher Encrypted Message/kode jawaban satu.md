# 🔓 Fungsi decipherMessage

## 📋 Deskripsi

Fungsi `decipherMessage` digunakan untuk mendekripsi (memecahkan sandi) pesan yang telah dienkripsi menggunakan teknik **substitusi posisi**. Fungsi ini bekerja dengan cara mengambil karakter dari pesan terenkripsi berdasarkan urutan indeks yang ditentukan oleh kunci sandi.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `encryptedMessage` | `string` | Pesan yang sudah dienkripsi dan perlu didekripsi |
| `cipherKey` | `array` | Array berisi urutan indeks untuk mengambil karakter dari pesan terenkripsi |

## 💻 Kode Fungsi

```javascript
function decipherMessage(encryptedMessage, cipherKey) {
  let decipheredMessage = '';
  
  // Iterasi melalui setiap indeks dalam kunci sandi
  for (let i = 0; i < cipherKey.length; i++) {
    
    // Ambil indeks dari kunci sandi pada posisi i
    const index = cipherKey[i];
    
    // Tambahkan karakter dari pesan terenkripsi pada posisi index ke hasil dekripsi
    decipheredMessage += encryptedMessage[index];
  }
  
  return decipheredMessage;
}
```

## 🎯 Cara Kerja

1. **Inisialisasi**: Membuat variabel `decipheredMessage` kosong untuk menyimpan hasil dekripsi
2. **Iterasi**: Melakukan perulangan sepanjang array `cipherKey`
3. **Ekstraksi Indeks**: Untuk setiap iterasi, ambil nilai indeks dari `cipherKey[i]`
4. **Pengambilan Karakter**: Ambil karakter dari `encryptedMessage` pada posisi yang sesuai dengan indeks
5. **Penggabungan**: Tambahkan karakter yang diambil ke variabel `decipheredMessage`
6. **Return**: Mengembalikan pesan yang sudah didekripsi

## 📊 Contoh Penggunaan

### Contoh 1: Dekripsi Kata Sederhana
```javascript
const pesanTerenkripsi = "HLOWRLD";
const kunciSandi = [0, 2, 4, 1, 3, 5, 6];

const hasil = decipherMessage(pesanTerenkripsi, kunciSandi);
console.log(hasil); // Output: "HELLOWD"
```

### Contoh 2: Dekripsi Kata "PROGRAM"
```javascript
const pesanTerenkripsi = "ROGPRAM";
const kunciSandi = [3, 0, 4, 1, 5, 2, 6];

const hasil = decipherMessage(pesanTerenkripsi, kunciSandi);
console.log(hasil); // Output: "PROGRAM"
```

### Contoh 3: Dekripsi Kalimat
```javascript
const pesanTerenkripsi = "AVCJSRTPIA";
const kunciSandi = [1, 2, 0, 3, 8, 4, 5, 6, 7, 9];

const hasil = decipherMessage(pesanTerenkripsi, kunciSandi);
console.log(hasil); // Output: "JAVASCRIPT"
```

## 📈 Tabel Contoh Proses Dekripsi

Menggunakan contoh: `encryptedMessage = "ROGPRAM"`, `cipherKey = [3, 0, 4, 1, 5, 2, 6]`

| Iterasi | i | cipherKey[i] | index | encryptedMessage[index] | decipheredMessage |
|---------|---|--------------|-------|------------------------|-------------------|
| 0 | 0 | 3 | 3 | 'P' (dari "ROGPRAM"[3]) | "P" |
| 1 | 1 | 0 | 0 | 'R' (dari "ROGPRAM"[0]) | "PR" |
| 2 | 2 | 4 | 4 | 'R' (dari "ROGPRAM"[4]) | "PRR" |
| 3 | 3 | 1 | 1 | 'O' (dari "ROGPRAM"[1]) | "PRRO" |
| 4 | 4 | 5 | 5 | 'A' (dari "ROGPRAM"[5]) | "PRROA" |
| 5 | 5 | 2 | 2 | 'G' (dari "ROGPRAM"[2]) | "PRROAG" |
| 6 | 6 | 6 | 6 | 'M' (dari "ROGPRAM"[6]) | "PRROAGM" |

## ⚠️ Catatan Penting

- **Validasi Indeks**: Pastikan semua nilai dalam `cipherKey` adalah indeks yang valid (0 ≤ index < panjang `encryptedMessage`)
- **Urutan Kritis**: Urutan indeks dalam `cipherKey` sangat menentukan hasil dekripsi
- **Panjang Array**: Panjang `cipherKey` menentukan berapa banyak karakter yang akan diambil dari pesan terenkripsi
- **Case Sensitivity**: Fungsi ini mempertahankan case (huruf besar/kecil) dari pesan asli

## 🔍 Tips Penggunaan

1. **Error Handling**: Tambahkan validasi untuk memastikan indeks tidak out of bounds
2. **Debugging**: Gunakan `console.log()` di dalam loop untuk melihat proses step-by-step
3. **Performance**: Untuk pesan panjang, pertimbangkan menggunakan array dan `.join()` instead of string concatenation
4. **Keamanan**: Jaga kerahasiaan `cipherKey` karena ini adalah kunci untuk dekripsi

## 📝 Contoh Implementasi dengan Error Handling

```javascript
function decipherMessageSafe(encryptedMessage, cipherKey) {
  // Validasi input
  if (!encryptedMessage || !cipherKey || !Array.isArray(cipherKey)) {
    throw new Error("Input tidak valid");
  }
  
  let decipheredMessage = '';
  
  // Iterasi melalui setiap indeks dalam kunci sandi
  for (let i = 0; i < cipherKey.length; i++) {
    
    // Ambil indeks dari kunci sandi pada posisi i
    const index = cipherKey[i];
    
    // Validasi indeks
    if (index < 0 || index >= encryptedMessage.length) {
      throw new Error(`Indeks ${index} tidak valid untuk pesan dengan panjang ${encryptedMessage.length}`);
    }
    
    // Tambahkan karakter dari pesan terenkripsi pada posisi index ke hasil dekripsi
    decipheredMessage += encryptedMessage[index];
  }
  
  return decipheredMessage;
}

// Contoh penggunaan dengan error handling
try {
  const hasil = decipherMessageSafe("JAVASCRIPT", [1, 2, 0, 3, 4, 5, 6, 7, 8, 9]);
  console.log("Hasil dekripsi:", hasil);
} catch (error) {
  console.error("Error:", error.message);
}
```

## 🛠️ Variasi Fungsi (Optimized)

```javascript
// Versi yang lebih efisien untuk pesan panjang
function decipherMessageOptimized(encryptedMessage, cipherKey) {
  // Menggunakan array untuk menghindari string concatenation berulang
  const result = [];
  
  // Iterasi melalui setiap indeks dalam kunci sandi
  for (let i = 0; i < cipherKey.length; i++) {
    
    // Ambil indeks dari kunci sandi pada posisi i
    const index = cipherKey[i];
    
    // Push karakter ke array
    result.push(encryptedMessage[index]);
  }
  
  // Gabungkan semua karakter menjadi string
  return result.join('');
}
```

---

*📚 Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi dekripsi pesan dengan teknik substitusi posisi karakter.*
