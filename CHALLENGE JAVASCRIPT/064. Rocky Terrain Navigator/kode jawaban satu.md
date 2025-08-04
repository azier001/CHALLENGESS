# 🏔️ Rocky Terrain Navigator

Fungsi untuk mensimulasikan navigasi karakter melalui medan berbatu dengan jalur aman dan rintangan.

## 📋 Deskripsi

`rockyTerrainNavigator` adalah fungsi yang mensimulasikan pergerakan karakter di medan berbatu. Karakter akan memeriksa medan di depannya sebelum bergerak. Jika ada jalur aman ("Path"), karakter akan maju. Jika ada rintangan ("Obstacle"), karakter akan mundur satu langkah (jika memungkinkan).

## 🔧 Parameter

| Parameter | Tipe   | Deskripsi |
|-----------|--------|-----------|
| `terrain` | Array  | Array yang berisi elemen-elemen medan berupa string "Path" untuk jalur aman atau "Obstacle" untuk rintangan |
| `steps`   | Number | Jumlah langkah yang akan dicoba oleh karakter |

## 🎮 Karakter Medan

| Karakter    | Deskripsi | Aksi Karakter |
|-------------|-----------|---------------|
| `"Path"`    | Jalur aman yang bisa dilalui | Karakter bergerak maju 1 langkah |
| `"Obstacle"` | Rintangan yang menghalangi jalan | Karakter mundur 1 langkah (jika posisi > 0) |
| Lainnya     | Medan tidak dikenal | Karakter tetap di tempat |

## 💻 Kode Fungsi

```javascript
function rockyTerrainNavigator(terrain, steps) {
    // Inisialisasi posisi awal karakter di indeks 0
    let position = 0;
    
    // Lakukan pergerakan sebanyak langkah yang ditentukan
    for (let i = 0; i < steps; i++) {
        // Periksa apakah masih ada medan di depan untuk diperiksa
        if (position < terrain.length - 1) {
            // Periksa medan di posisi selanjutnya
            if (terrain[position + 1] === "Path") {
                // Jika jalur aman, maju satu langkah
                position++;
            } else if (terrain[position + 1] === "Obstacle") {
                // Jika ada rintangan, mundur satu langkah (jika memungkinkan)
                if (position > 0) {
                    position--;
                }
            }
            // Jika bukan "Path" atau "Obstacle", karakter tetap di tempat
        }
        // Jika sudah di ujung medan, karakter tidak bergerak
    }
    
    // Kembalikan posisi akhir karakter
    return position;
}
```

## 📖 Cara Kerja

1. **Inisialisasi**: Karakter dimulai dari posisi 0 (awal array)
2. **Pemeriksaan Medan**: Setiap langkah, karakter memeriksa medan di posisi selanjutnya (position + 1)
3. **Keputusan Pergerakan**:
   - Jika medan selanjutnya adalah "Path" → maju 1 langkah
   - Jika medan selanjutnya adalah "Obstacle" → mundur 1 langkah (jika posisi > 0)
   - Jika medan lainnya → tetap di tempat
4. **Batas Medan**: Jika sudah di ujung medan (position >= terrain.length - 1), karakter tidak bergerak
5. **Batas Mundur**: Karakter tidak bisa mundur jika sudah di posisi 0

## 🎯 Contoh Penggunaan

### Contoh 1: Medan dengan Jalur Aman dan Rintangan
```javascript
const terrain1 = ["Start", "Path", "Path", "Obstacle", "Path"];
const result1 = rockyTerrainNavigator(terrain1, 5);
console.log(result1); // Output: 1

// Penjelasan langkah demi langkah:
// Posisi awal: 0 (Start)
// Langkah 1: Cek posisi 1 → "Path" → maju ke posisi 1
// Langkah 2: Cek posisi 2 → "Path" → maju ke posisi 2  
// Langkah 3: Cek posisi 3 → "Obstacle" → mundur ke posisi 1
// Langkah 4: Cek posisi 2 → "Path" → maju ke posisi 2
// Langkah 5: Cek posisi 3 → "Obstacle" → mundur ke posisi 1
// Posisi akhir: 1
```

### Contoh 2: Medan Hanya Jalur Aman
```javascript
const terrain2 = ["Start", "Path", "Path", "Path"];
const result2 = rockyTerrainNavigator(terrain2, 3);
console.log(result2); // Output: 3

// Penjelasan:
// Langkah 1: Cek posisi 1 → "Path" → maju ke posisi 1
// Langkah 2: Cek posisi 2 → "Path" → maju ke posisi 2
// Langkah 3: Cek posisi 3 → "Path" → maju ke posisi 3
// Posisi akhir: 3
```

### Contoh 3: Rintangan di Awal
```javascript
const terrain3 = ["Start", "Obstacle", "Path", "Path"];
const result3 = rockyTerrainNavigator(terrain3, 4);
console.log(result3); // Output: 0

// Penjelasan:
// Langkah 1: Cek posisi 1 → "Obstacle" → mundur, tapi sudah di posisi 0 → tetap 0
// Langkah 2: Cek posisi 1 → "Obstacle" → mundur, tapi sudah di posisi 0 → tetap 0
// Langkah 3: Cek posisi 1 → "Obstacle" → mundur, tapi sudah di posisi 0 → tetap 0
// Langkah 4: Cek posisi 1 → "Obstacle" → mundur, tapi sudah di posisi 0 → tetap 0
// Posisi akhir: 0
```

### Contoh 4: Medan dengan Elemen Tidak Dikenal
```javascript
const terrain4 = ["Start", "Unknown", "Path", "Path"];
const result4 = rockyTerrainNavigator(terrain4, 3);
console.log(result4); // Output: 0

// Penjelasan:
// Langkah 1: Cek posisi 1 → "Unknown" → tetap di posisi 0
// Langkah 2: Cek posisi 1 → "Unknown" → tetap di posisi 0
// Langkah 3: Cek posisi 1 → "Unknown" → tetap di posisi 0
// Posisi akhir: 0
```

## ⚠️ Catatan Penting

- Karakter **memeriksa medan di depan** sebelum memutuskan gerakan
- Posisi karakter tidak akan pernah kurang dari 0
- Karakter tidak bergerak jika sudah mencapai ujung medan (posisi terakhir)
- Hanya elemen "Path" yang membuat karakter maju
- Hanya elemen "Obstacle" yang membuat karakter mundur
- Elemen lain selain "Path" dan "Obstacle" membuat karakter tetap di tempat
- Fungsi mengembalikan posisi akhir dalam bentuk indeks array (dimulai dari 0)

## 🎯 Kegunaan

Fungsi ini cocok untuk:
- Game navigasi dengan strategi
- Simulasi pergerakan dengan pemeriksaan medan
- Pembelajaran algoritma decision-making
- Implementasi AI sederhana untuk pathfinding
- Contoh logika kondisional bertingkat dalam programming

## 🔄 Perbedaan dengan Versi Sebelumnya

Versi ini lebih strategis karena:
- Karakter **memeriksa medan terlebih dahulu** sebelum bergerak
- Penalti rintangan lebih ringan (mundur 1 langkah vs 2 langkah)
- Karakter tidak akan "terjebak" bergerak maju ke rintangan
- Lebih realistis dalam simulasi navigasi yang hati-hati
