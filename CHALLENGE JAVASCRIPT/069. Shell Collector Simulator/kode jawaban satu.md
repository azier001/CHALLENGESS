# 🐚 Dokumentasi Fungsi `collectShells`

## 📝 Deskripsi

Fungsi `collectShells` adalah sebuah fungsi yang digunakan untuk mengelola koleksi kerang (shells) berdasarkan serangkaian perintah. Fungsi ini memungkinkan penambahan dan penghapusan kerang dari koleksi dengan aturan khusus untuk penghapusan. **Penting**: Fungsi ini memodifikasi array asli yang diberikan sebagai parameter.

## ⚙️ Cara Kerja

- **Menambah kerang**: Jika perintah berupa angka positif, kerang dengan tipe tersebut akan ditambahkan ke koleksi
- **Menghapus kerang**: Jika perintah berupa angka negatif, fungsi akan mencoba menghapus kerang dengan tipe yang sesuai, tetapi hanya jika kerang tersebut berada di posisi terakhir dalam koleksi

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `shells` | Array | Koleksi kerang yang akan dimodifikasi (array asli akan berubah) |
| `commands` | Array | Daftar perintah untuk menambah atau menghapus kerang |

## 🔢 Tipe Perintah

| Nilai Perintah | Aksi | Contoh |
|----------------|------|---------|
| Angka positif (> 0) | Menambah kerang dengan tipe tersebut | `5` → menambah kerang tipe 5 |
| Angka negatif (< 0) | Menghapus kerang dengan tipe `Math.abs(command)` jika berada di posisi terakhir | `-3` → menghapus kerang tipe 3 (jika ada di akhir) |
| Nol (0) | Tidak melakukan apa-apa | `0` → diabaikan |

## 💻 Kode Fungsi

```javascript
function collectShells(shells, commands) {
  // Iterasi melalui setiap perintah dalam array commands
  for (let i = 0; i < commands.length; i++) {
    const command = commands[i];
    
    // Jika perintah negatif dan kerang terakhir sesuai dengan tipe yang diminta
    if (command < 0 && shells[shells.length - 1] === -command) {
      shells.pop(); // Hapus kerang terakhir dari koleksi
      continue; // Lanjutkan ke perintah berikutnya
    }
    
    // Jika perintah positif, tambahkan kerang ke koleksi
    if (command > 0) {
      shells.push(command); // Tambahkan kerang baru ke akhir koleksi
    }
    // Jika command = 0, tidak melakukan apa-apa (diabaikan)
  }
  
  return shells; // Kembalikan koleksi kerang yang sudah dimodifikasi
}
```

## 📖 Contoh Penggunaan

### Contoh 1: Menambah Kerang
```javascript
const shellsKoleksi = [1, 2, 3];
const perintah = [4, 5];
const hasil = collectShells(shellsKoleksi, perintah);

console.log(hasil); 
// Output: [1, 2, 3, 4, 5]
console.log(shellsKoleksi);
// Output: [1, 2, 3, 4, 5] (array asli juga berubah!)
```

### Contoh 2: Menghapus Kerang (Berhasil)
```javascript
const shellsKoleksi = [1, 2, 3];
const perintah = [-3]; // Hapus kerang tipe 3
const hasil = collectShells(shellsKoleksi, perintah);

console.log(hasil);
// Output: [1, 2]
// Berhasil menghapus karena kerang tipe 3 ada di posisi terakhir
```

### Contoh 3: Menghapus Kerang (Gagal)
```javascript
const shellsKoleksi = [1, 2, 3];
const perintah = [-2]; // Coba hapus kerang tipe 2
const hasil = collectShells(shellsKoleksi, perintah);

console.log(hasil);
// Output: [1, 2, 3]
// Gagal menghapus karena kerang tipe 2 tidak di posisi terakhir
```

### Contoh 4: Kombinasi Perintah
```javascript
const shellsKoleksi = [1, 2];
const perintah = [3, 4, -4, 5, -2, -5];
const hasil = collectShells(shellsKoleksi, perintah);

console.log(hasil);
// Output: [1, 2, 3]

// Proses step by step:
// 1. [1, 2] + 3 = [1, 2, 3]
// 2. [1, 2, 3] + 4 = [1, 2, 3, 4]  
// 3. [1, 2, 3, 4] - 4 = [1, 2, 3] (berhasil, 4 di akhir)
// 4. [1, 2, 3] + 5 = [1, 2, 3, 5]
// 5. [1, 2, 3, 5] - 2 = [1, 2, 3, 5] (gagal, 2 bukan di akhir)
// 6. [1, 2, 3, 5] - 5 = [1, 2, 3] (berhasil, 5 di akhir)
```

### Contoh 5: Array Kosong
```javascript
const shellsKoleksi = [];
const perintah = [-1, 2, 3, -3];
const hasil = collectShells(shellsKoleksi, perintah);

console.log(hasil);
// Output: [2]
// Proses: [] -1 (gagal, array kosong) → [2] → [2, 3] → [2] (hapus 3)
```

## ⚠️ Catatan Penting

1. **Array Asli Berubah**: Fungsi ini **memodifikasi array asli** yang diberikan sebagai parameter `shells`
2. **Aturan Penghapusan Ketat**: Kerang hanya bisa dihapus jika berada di posisi terakhir dalam koleksi
3. **Penanganan Array Kosong**: Fungsi akan mengabaikan perintah penghapusan jika koleksi kosong
4. **Tipe Data**: Fungsi mengharapkan array berisi angka integer
5. **Continue Statement**: Menggunakan `continue` untuk melewati perintah setelah penghapusan berhasil

## 🔄 Perbedaan dengan Versi Immutable

Jika Anda ingin array asli tidak berubah, gunakan spread operator:

```javascript
// Membuat salinan array sebelum memanggil fungsi
const shellsAsli = [1, 2, 3];
const shellsSalinan = [...shellsAsli];
const hasil = collectShells(shellsSalinan, [4, -3]);

console.log(shellsAsli);    // Output: [1, 2, 3] (tidak berubah)
console.log(hasil);         // Output: [1, 2, 4]
```

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- Simulasi permainan mengumpulkan item dengan aturan LIFO (Last In, First Out)
- Implementasi stack dengan operasi tambah/hapus bersyarat  
- Manajemen inventori dengan aturan khusus penghapusan item
- Sistem undo/redo sederhana
- Algoritma parsing dengan pencocokan bracket atau tag
