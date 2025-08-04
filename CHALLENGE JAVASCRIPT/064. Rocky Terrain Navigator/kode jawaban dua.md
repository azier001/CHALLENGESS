# 🏔️ Rocky Terrain Navigator

Fungsi untuk mensimulasikan navigasi karakter melalui medan berbatu yang penuh dengan rintangan.

## 📋 Deskripsi

`rockyTerrainNavigator` adalah fungsi yang mensimulasikan pergerakan karakter di medan berbatu. Karakter akan bergerak maju selangkah demi selangkah, namun jika bertemu dengan rintangan ("Obstacle"), karakter akan tersandung dan mundur dua langkah sebagai penalti.

## 🔧 Parameter

| Parameter | Tipe   | Deskripsi |
|-----------|--------|-----------|
| `terrain` | Array  | Array yang berisi elemen-elemen medan. Bisa berupa string "Obstacle" untuk rintangan atau elemen lain untuk jalur aman |
| `steps`   | Number | Jumlah langkah yang akan dicoba oleh karakter |

## 🎮 Karakter Medan

| Karakter    | Deskripsi |
|-------------|-----------|
| `"Obstacle"` | Rintangan yang menyebabkan karakter tersandung dan mundur 2 langkah |
| Lainnya     | Jalur aman yang bisa dilalui tanpa penalti |

## 💻 Kode Fungsi

```javascript
function rockyTerrainNavigator(terrain, steps) {
    // Inisialisasi posisi awal karakter di indeks 0
    let position = 0;
    
    // Lakukan pergerakan sebanyak langkah yang ditentukan
    for (let i = 0; i < steps; i++) {
        // Coba bergerak maju satu langkah
        if (position < terrain.length - 1) {
            position++;
        }
        
        // Periksa apakah posisi saat ini adalah rintangan
        if (terrain[position] === "Obstacle") {
            // Tersandung: mundur dua langkah (batalkan gerakan + penalti)
            position = Math.max(0, position - 2);
        }
    }
    
    // Kembalikan posisi akhir karakter
    return position;
}
```

## 📖 Cara Kerja

1. **Inisialisasi**: Karakter dimulai dari posisi 0 (awal array)
2. **Pergerakan**: Setiap langkah, karakter mencoba bergerak maju satu posisi
3. **Pemeriksaan Rintangan**: Jika posisi baru mengandung "Obstacle":
   - Karakter tersandung
   - Mundur 2 langkah dari posisi saat ini
   - Posisi tidak boleh kurang dari 0 (menggunakan `Math.max(0, position - 2)`)
4. **Batas Medan**: Karakter tidak bisa bergerak melampaui panjang array terrain

## 🎯 Contoh Penggunaan

### Contoh 1: Medan dengan Beberapa Rintangan
```javascript
const terrain1 = ["Safe", "Safe", "Obstacle", "Safe", "Safe"];
const result1 = rockyTerrainNavigator(terrain1, 5);
console.log(result1); // Output: 2

// Penjelasan langkah demi langkah:
// Langkah 1: posisi 0 → 1 (Safe)
// Langkah 2: posisi 1 → 2 (Obstacle) → mundur ke posisi 0
// Langkah 3: posisi 0 → 1 (Safe)  
// Langkah 4: posisi 1 → 2 (Obstacle) → mundur ke posisi 0
// Langkah 5: posisi 0 → 1 (Safe)
// Posisi akhir: 1
```

### Contoh 2: Medan Tanpa Rintangan
```javascript
const terrain2 = ["Safe", "Safe", "Safe", "Safe"];
const result2 = rockyTerrainNavigator(terrain2, 3);
console.log(result2); // Output: 3

// Penjelasan:
// Langkah 1: posisi 0 → 1
// Langkah 2: posisi 1 → 2  
// Langkah 3: posisi 2 → 3
// Posisi akhir: 3
```

### Contoh 3: Rintangan di Awal
```javascript
const terrain3 = ["Safe", "Obstacle", "Safe", "Safe"];
const result3 = rockyTerrainNavigator(terrain3, 4);
console.log(result3); // Output: 1

// Penjelasan:
// Langkah 1: posisi 0 → 1 (Obstacle) → mundur ke posisi 0 (Math.max(0, 1-2))
// Langkah 2: posisi 0 → 1 (Obstacle) → mundur ke posisi 0
// Langkah 3: posisi 0 → 1 (Obstacle) → mundur ke posisi 0
// Langkah 4: posisi 0 → 1 (Obstacle) → mundur ke posisi 0
// Posisi akhir: 0
```

## ⚠️ Catatan Penting

- Posisi karakter tidak akan pernah kurang dari 0
- Karakter tidak bisa bergerak melampaui panjang array terrain
- Setiap kali bertemu rintangan, karakter akan mundur 2 langkah (tidak hanya 1)
- Fungsi mengembalikan posisi akhir dalam bentuk indeks array (dimulai dari 0)

## 🎯 Kegunaan

Fungsi ini cocok untuk:
- Game navigasi sederhana
- Simulasi pergerakan dengan penalti
- Pembelajaran algoritma dasar
- Contoh implementasi logika kondisional dalam programming
