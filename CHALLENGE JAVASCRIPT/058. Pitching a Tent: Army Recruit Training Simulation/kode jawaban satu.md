# 🏕️ Dokumentasi Fungsi `pitchTent`

## 📝 Deskripsi Fungsi

Fungsi `pitchTent` adalah simulasi untuk mendirikan tenda dengan sistem kesabaran dan percobaan. Fungsi ini akan memproses langkah-langkah mendirikan tenda dengan cara menghapus langkah mudah secara dinamis dan mengurangi kesabaran ketika menemui langkah yang sulit.

## 🎯 Cara Kerja

1. **Sistem percobaan**: Fungsi akan mencoba hingga jumlah `attempts` yang ditentukan
2. **Hapus langkah mudah**: Setiap langkah yang mengandung kata "easy" akan dihapus dari array
3. **Proses langkah sulit**: Setiap langkah yang mengandung "difficult" akan mengurangi kesabaran
4. **Reset per percobaan**: Setiap percobaan baru akan menggunakan kesabaran penuh
5. **Hasil akhir**: Berhasil jika kesabaran masih tersisa setelah semua langkah, gagal jika semua percobaan habis

## 📊 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `steps` | Array | Daftar langkah-langkah untuk mendirikan tenda (akan dimodifikasi) |
| `patience` | Number | Jumlah kesabaran awal (berapa kali bisa menghadapi langkah sulit) |
| `attempts` | Number | Jumlah percobaan yang tersedia |

## 🔄 Return Value

| Kondisi | Return Value |
|---------|--------------|
| Berhasil (kesabaran > 0 setelah semua langkah) | `"Tent pitched successfully!"` |
| Gagal (semua percobaan habis) | `"Failed to pitch the tent!"` |

## 💻 Kode Fungsi

```javascript
function pitchTent(steps, patience, attempts) {
    // Lakukan percobaan sebanyak jumlah attempts
    for (let attempt = 0; attempt < attempts; attempt++) {
        
        // Proses setiap langkah dalam array steps
        for (let i = 0; i < steps.length; i++) {
            const step = steps[i];
            
            // Jika langkah mengandung "difficult", kurangi kesabaran
            if (step.includes("difficult")) {
                patience--;
                
                // Jika kesabaran habis, hentikan percobaan ini
                if (patience === 0) {
                    break;
                }
            } 
            // Jika langkah mengandung "easy", hapus dari array
            else if (step.includes("easy")) {
                steps = steps.slice(0, i).concat(steps.slice(i + 1));
                i--; // Mundur satu index karena array berubah
                continue;
            } 
            // Langkah lainnya, lanjutkan tanpa efek
            else {
                continue;
            }
        }
        
        // Jika kesabaran masih ada, berhasil!
        if (patience > 0) {
            return "Tent pitched successfully!";
        }
    }
    
    // Jika semua percobaan gagal
    return "Failed to pitch the tent!";
}
```

## 📋 Contoh Penggunaan

### Contoh 1: Berhasil dengan Langkah Mudah Dihapus
```javascript
const steps1 = [
    "prepare ground",
    "easy setup base", 
    "difficult insert poles",
    "attach fabric",
    "easy stake corners"
];

const result1 = pitchTent(steps1, 3, 2);
console.log(result1); 
// Output: "Tent pitched successfully!"
```

**Penjelasan**: 
- Percobaan 1: "easy setup base" dan "easy stake corners" dihapus
- Array menjadi: ["prepare ground", "difficult insert poles", "attach fabric"]
- "difficult insert poles" mengurangi kesabaran menjadi 2
- Kesabaran masih > 0 setelah semua langkah = berhasil!

### Contoh 2: Gagal Setelah Semua Percobaan
```javascript
const steps2 = [
    "difficult prepare ground",
    "difficult insert poles", 
    "difficult attach fabric",
    "difficult secure tent"
];

const result2 = pitchTent(steps2, 2, 2);
console.log(result2);
// Output: "Failed to pitch the tent!"
```

**Penjelasan**:
- Percobaan 1: 4 langkah sulit, kesabaran habis di langkah ke-2
- Percobaan 2: Kesabaran reset ke 2, tapi masih 4 langkah sulit
- Kesabaran habis lagi di langkah ke-2
- Semua percobaan habis = gagal!

### Contoh 3: Sukses Setelah Menghapus Semua Langkah Mudah
```javascript
const steps3 = [
    "easy prepare tools",
    "easy read manual",
    "normal setup", 
    "easy final check"
];

const result3 = pitchTent(steps3, 1, 1);
console.log(result3);
// Output: "Tent pitched successfully!"
```

**Penjelasan**:
- Semua langkah "easy" dihapus secara dinamis
- Array menjadi: ["normal setup"]
- Langkah "normal setup" tidak mengandung "difficult", jadi kesabaran tetap 1
- Kesabaran > 0 setelah semua langkah = berhasil!

### Contoh 4: Demonstrasi Modifikasi Array
```javascript
const originalSteps = [
    "easy step 1",
    "difficult step 2", 
    "easy step 3",
    "normal step 4"
];

console.log("Before:", originalSteps);
const result4 = pitchTent(originalSteps, 2, 1);
console.log("After:", originalSteps);
console.log("Result:", result4);

// Output:
// Before: ["easy step 1", "difficult step 2", "easy step 3", "normal step 4"]
// After: ["difficult step 2", "normal step 4"]  
// Result: "Tent pitched successfully!"
```

## 🧠 Tips Penggunaan

- **Kesabaran cukup**: Pastikan nilai `patience` lebih besar dari jumlah langkah "difficult"
- **Percobaan multiple**: Gunakan lebih dari 1 percobaan untuk situasi yang tidak pasti
- **Langkah mudah**: Akan dihapus permanen dari array asli
- **Array termodifikasi**: Fungsi ini mengubah array `steps` yang diberikan

## ⚠️ Catatan Penting

- **Side Effect**: Fungsi ini memodifikasi array `steps` yang diberikan sebagai parameter
- **Kesabaran reset**: Setiap percobaan baru dimulai dengan kesabaran penuh
- **Penghapusan dinamis**: Langkah "easy" dihapus saat ditemukan, bukan di awal
- **Index management**: Penggunaan `i--` diperlukan karena array berubah saat iterasi
- **Deteksi string**: Menggunakan `includes()` untuk mendeteksi kata "easy" dan "difficult"

## 🔍 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Ini | Versi Sebelumnya |
|-------|-----------|------------------|
| **Modifikasi Array** | Mengubah array asli | Membuat array terfilter |
| **Timing Penghapusan** | Saat ditemukan | Di awal proses |
| **Reset Kesabaran** | Setiap percobaan | Setelah kesabaran habis |
| **Side Effect** | Ya (array berubah) | Tidak |
