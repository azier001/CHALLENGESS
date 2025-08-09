# 🐚 Dokumentasi Fungsi `collectShells`

## 📝 Deskripsi

Fungsi `collectShells` adalah sebuah fungsi yang digunakan untuk mengelola koleksi kerang (shells) berdasarkan serangkaian perintah. Fungsi ini memungkinkan penambahan dan penghapusan kerang dari koleksi dengan aturan khusus untuk penghapusan.

## ⚙️ Cara Kerja

- **Menambah kerang**: Jika perintah berupa angka positif, kerang dengan tipe tersebut akan ditambahkan ke koleksi
- **Menghapus kerang**: Jika perintah berupa angka negatif, fungsi akan mencoba menghapus kerang dengan tipe yang sesuai, tetapi hanya jika kerang tersebut berada di posisi terakhir dalam koleksi

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `shells` | Array | Koleksi kerang awal yang sudah ada |
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
    // Buat salinan array shells untuk menghindari modifikasi array asli
    let result = [...shells];
    
    // Iterasi melalui setiap perintah
    for (let i = 0; i < commands.length; i++) {
        let command = commands[i];
        
        // Jika perintah negatif, coba hapus kerang
        if (command < 0) {
            let shellType = Math.abs(command); // Dapatkan tipe kerang yang akan dihapus
            
            // Hapus hanya jika kerang terakhir sesuai dengan tipe yang diminta
            if (result.length > 0 && result[result.length - 1] === shellType) {
                result.pop(); // Hapus kerang terakhir
            }
        } 
        // Jika perintah positif, tambah kerang
        else if (command > 0) {
            result.push(command); // Tambahkan kerang baru ke koleksi
        }
        // Jika command = 0, tidak melakukan apa-apa (diabaikan)
    }
    
    return result; // Kembalikan koleksi kerang yang sudah dimodifikasi
}
```

## 📖 Contoh Penggunaan

### Contoh 1: Menambah Kerang
```javascript
const shellsAwal = [1, 2, 3];
const perintah = [4, 5];
const hasil = collectShells(shellsAwal, perintah);

console.log(hasil); 
// Output: [1, 2, 3, 4, 5]
```

### Contoh 2: Menghapus Kerang (Berhasil)
```javascript
const shellsAwal = [1, 2, 3];
const perintah = [-3]; // Hapus kerang tipe 3
const hasil = collectShells(shellsAwal, perintah);

console.log(hasil);
// Output: [1, 2]
// Berhasil menghapus karena kerang tipe 3 ada di posisi terakhir
```

### Contoh 3: Menghapus Kerang (Gagal)
```javascript
const shellsAwal = [1, 2, 3];
const perintah = [-2]; // Coba hapus kerang tipe 2
const hasil = collectShells(shellsAwal, perintah);

console.log(hasil);
// Output: [1, 2, 3]
// Gagal menghapus karena kerang tipe 2 tidak di posisi terakhir
```

### Contoh 4: Kombinasi Perintah
```javascript
const shellsAwal = [1, 2];
const perintah = [3, 4, -4, 5, -2, -5];
const hasil = collectShells(shellsAwal, perintah);

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

## ⚠️ Catatan Penting

1. **Array Original Tidak Berubah**: Fungsi membuat salinan array `shells` sehingga array asli tidak termodifikasi
2. **Aturan Penghapusan Ketat**: Kerang hanya bisa dihapus jika berada di posisi terakhir dalam koleksi
3. **Penanganan Edge Case**: Fungsi akan mengabaikan perintah penghapusan jika koleksi kosong
4. **Tipe Data**: Fungsi mengharapkan array berisi angka integer

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- Simulasi permainan mengumpulkan item dengan aturan LIFO (Last In, First Out)
- Implementasi stack dengan operasi tambah/hapus bersyarat
- Manajemen inventori dengan aturan khusus penghapusan item
