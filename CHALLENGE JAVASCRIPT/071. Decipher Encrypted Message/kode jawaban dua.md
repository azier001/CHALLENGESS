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
    let result = '';
    
    // Iterasi melalui setiap indeks dalam kunci sandi
    for (let i = 0; i < cipherKey.length; i++) {
        
        // Ambil karakter pada indeks yang ditentukan oleh cipherKey[i]
        result += encryptedMessage[cipherKey[i]];
    }
    
    return result;
}
```

## 🎯 Cara Kerja

1. **Inisialisasi**: Membuat variabel `result` kosong untuk menyimpan hasil dekripsi
2. **Iterasi**: Melakukan perulangan sepanjang array `cipherKey`
3. **Ekstraksi**: Untuk setiap elemen dalam `cipherKey`, ambil karakter dari `encryptedMessage` pada posisi yang sesuai
4. **Penggabungan**: Tambahkan karakter yang diambil ke variabel `result`
5. **Return**: Mengembalikan pesan yang sudah didekripsi

## 📊 Contoh Penggunaan

### Contoh 1: Dekripsi Sederhana
```javascript
const pesanTerenkripsi = "HLOWRLD";
const kunciSandi = [0, 2, 4, 1, 3, 5, 6];

const hasil = decipherMessage(pesanTerenkripsi, kunciSandi);
console.log(hasil); // Output: "HELLOWD"
```

### Contoh 2: Dekripsi Kata
```javascript
const pesanTerenkripsi = "RPAMOGMR";
const kunciSandi = [4, 0, 6, 2, 1, 7, 3, 5];

const hasil = decipherMessage(pesanTerenkripsi, kunciSandi);
console.log(hasil); // Output: "PROGRAM"
```

## 📈 Tabel Contoh Proses Dekripsi

| Iterasi | cipherKey[i] | encryptedMessage[cipherKey[i]] | result |
|---------|--------------|-------------------------------|--------|
| 0 | 4 | 'G' (dari "RPAMOGMR"[4]) | "G" |
| 1 | 0 | 'R' (dari "RPAMOGMR"[0]) | "GR" |
| 2 | 6 | 'M' (dari "RPAMOGMR"[6]) | "GRM" |
| 3 | 2 | 'A' (dari "RPAMOGMR"[2]) | "GRMA" |
| ... | ... | ... | ... |

## ⚠️ Catatan Penting

- **Indeks Array**: Pastikan indeks dalam `cipherKey` tidak melebihi panjang `encryptedMessage`
- **Urutan Penting**: Urutan indeks dalam `cipherKey` menentukan urutan karakter dalam hasil dekripsi
- **Panjang Kunci**: Panjang `cipherKey` menentukan berapa banyak karakter yang akan diambil dari pesan terenkripsi

## 🔍 Tips Penggunaan

1. **Validasi Input**: Selalu pastikan `cipherKey` berisi indeks yang valid
2. **Debugging**: Gunakan `console.log()` untuk melihat proses dekripsi step-by-step
3. **Enkripsi Balik**: Fungsi ini adalah kebalikan dari proses enkripsi dengan substitusi posisi

## 📝 Contoh Implementasi Lengkap

```javascript
// Contoh penggunaan lengkap
function contohDekripsi() {
    const pesanAsli = "JAVASCRIPT";
    const kunciEnkripsi = [9, 0, 8, 1, 7, 2, 6, 3, 5, 4];
    
    // Simulasi proses enkripsi (untuk pemahaman)
    let pesanTerenkripsi = '';
    for (let i = 0; i < pesanAsli.length; i++) {
        pesanTerenkripsi += pesanAsli[kunciEnkripsi[i]];
    }
    console.log("Pesan Terenkripsi:", pesanTerenkripsi);
    
    // Membuat kunci dekripsi (kebalikan dari kunci enkripsi)
    const kunciDekripsi = [1, 3, 5, 7, 9, 8, 6, 4, 2, 0];
    
    // Dekripsi menggunakan fungsi kita
    const hasilDekripsi = decipherMessage(pesanTerenkripsi, kunciDekripsi);
    console.log("Hasil Dekripsi:", hasilDekripsi);
}
```

---

*📚 Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi dekripsi pesan dengan teknik substitusi posisi.*
