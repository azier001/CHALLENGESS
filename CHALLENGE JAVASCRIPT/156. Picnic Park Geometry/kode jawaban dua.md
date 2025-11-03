# 🧺 Dokumentasi Fungsi `arrangePicnic`

## 📋 Deskripsi

Fungsi `arrangePicnic` adalah fungsi yang digunakan untuk mengatur dan mengecek tumpang tindih (overlap) item-item piknik setelah dilakukan transformasi geometris. Fungsi ini menerima daftar bentuk geometris (segitiga, lingkaran, persegi panjang) dan menerapkan transformasi seperti scaling atau rotasi, kemudian mengecek apakah ada item yang bertumpuk satu sama lain.

## 🎯 Tujuan Fungsi

- Melakukan transformasi geometris pada berbagai bentuk
- Menghitung bounding box (area pembatas) untuk setiap bentuk
- Mendeteksi apakah ada item yang saling tumpang tindih

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `items` | `Array<String>` | Array berisi string yang merepresentasikan bentuk geometris dengan formatnya masing-masing |
| `transformation` | `String` | String yang berisi jenis transformasi dan nilainya, dipisahkan koma (contoh: `"scale,2"` atau `"rotate,90"`) |

### Format String Items

| Bentuk | Format | Contoh |
|--------|--------|--------|
| **Segitiga** | `"triangle,sisi_a,sisi_b,sisi_c"` | `"triangle,3,4,5"` |
| **Lingkaran** | `"circle,radius"` | `"circle,5"` |
| **Persegi Panjang** | `"rectangle,lebar,tinggi"` | `"rectangle,4,6"` |

### Jenis Transformasi

| Transformasi | Format | Deskripsi | Contoh |
|--------------|--------|-----------|--------|
| **Scale** | `"scale,nilai"` | Memperbesar/memperkecil ukuran dengan faktor pengali | `"scale,2"` (2x lipat) |
| **Rotate** | `"rotate,derajat"` | Memutar bentuk (khusus persegi panjang, 90° atau 270° menukar dimensi) | `"rotate,90"` |

## 📤 Output

Fungsi mengembalikan array berisi nilai boolean:
- `true` = Item tersebut **bertumpuk** dengan item lain
- `false` = Item tersebut **tidak bertumpuk** dengan item lain

**Contoh Output:**
```javascript
[true, true, false]
// Item ke-0 bertumpuk, Item ke-1 bertumpuk, Item ke-2 tidak bertumpuk
```

## 💻 Source Code

```javascript
function arrangePicnic(items, transformation) {
    // Parse (mengurai) string transformasi
    const [transType, transValue] = transformation.split(',');
    const value = parseFloat(transValue);
    
    // Parse dan transformasi setiap item
    const transformedItems = items.map(item => {
        const parts = item.split(',');
        const shape = parts[0];
        
        let bounds = {};
        
        if (shape === 'triangle') {
            // Ambil panjang ketiga sisi segitiga
            let [a, b, c] = [
                parseFloat(parts[1]), 
                parseFloat(parts[2]), 
                parseFloat(parts[3])
            ];
            
            // Terapkan transformasi pada sisi-sisi segitiga
            if (transType === 'scale') {
                a *= value;
                b *= value;
                c *= value;
            }
            
            // Hitung bounding box menggunakan rumus Heron untuk luas
            const s = (a + b + c) / 2; // Semi-perimeter
            const area = Math.sqrt(s * (s - a) * (s - b) * (s - c)); // Luas
            const height = (2 * area) / a; // Tinggi dengan 'a' sebagai alas
            
            bounds = { 
                width: a, 
                height: height, 
                type: 'triangle' 
            };
            
        } else if (shape === 'circle') {
            // Ambil radius lingkaran
            let radius = parseFloat(parts[1]);
            
            // Terapkan transformasi scale pada radius
            if (transType === 'scale') {
                radius *= value;
            }
            
            bounds = { 
                width: radius * 2, 
                height: radius * 2, 
                radius: radius, 
                type: 'circle' 
            };
            
        } else if (shape === 'rectangle') {
            // Ambil lebar dan tinggi persegi panjang
            let width = parseFloat(parts[1]);
            let height = parseFloat(parts[2]);
            
            if (transType === 'scale') {
                // Scale: perbesar/perkecil dimensi
                width *= value;
                height *= value;
            } else if (transType === 'rotate') {
                // Rotate: untuk rotasi 90° atau 270°, tukar dimensi
                if (value === 90 || value === 270) {
                    [width, height] = [height, width];
                }
            }
            
            bounds = { 
                width: width, 
                height: height, 
                type: 'rectangle' 
            };
        }
        
        return bounds;
    });
    
    // Cek apakah ada item yang tumpang tindih
    const result = items.map((_, i) => {
        for (let j = 0; j < transformedItems.length; j++) {
            if (i !== j) {
                // Pengecekan overlap sederhana: jika kedua item memiliki area,
                // maka mereka akan tumpang tindih
                // Asumsi: semua item ditempatkan di titik awal (0,0)
                const item1 = transformedItems[i];
                const item2 = transformedItems[j];
                
                // Cek apakah bounding box bertumpuk
                // Karena semua item mulai di (0,0), dua item dengan area
                // akan otomatis tumpang tindih
                if (item1.width > 0 && item1.height > 0 && 
                    item2.width > 0 && item2.height > 0) {
                    return true;
                }
            }
        }
        return false;
    });
    
    return result;
}
```

## 🔧 Cara Kerja

### 1️⃣ **Parsing Transformasi**
Fungsi memisahkan string transformasi menjadi tipe (scale/rotate) dan nilai numerik.

### 2️⃣ **Transformasi Setiap Item**
Untuk setiap bentuk:
- **Segitiga**: Menghitung bounding box menggunakan rumus Heron untuk mendapatkan luas, lalu tinggi
- **Lingkaran**: Diameter = 2 × radius
- **Persegi Panjang**: Menerapkan scale atau menukar dimensi saat rotasi 90°/270°

### 3️⃣ **Deteksi Overlap**
Mengecek setiap item dengan item lainnya. Karena semua item dianggap dimulai dari titik (0,0), maka jika dua item memiliki ukuran (width > 0 dan height > 0), mereka akan bertumpuk.

## 📚 Contoh Penggunaan

### Contoh 1: Scale Lingkaran dan Persegi Panjang

```javascript
const items = [
    "circle,5",      // Lingkaran radius 5
    "rectangle,4,6"  // Persegi panjang 4×6
];

const result = arrangePicnic(items, "scale,2");
console.log(result);
// Output: [true, true]
// Kedua item bertumpuk karena berada di posisi (0,0)
```

**Penjelasan:**
- Lingkaran: radius 5 → setelah scale 2× → radius 10 (diameter 20)
- Persegi panjang: 4×6 → setelah scale 2× → 8×12
- Karena keduanya berada di (0,0), mereka bertumpuk

### Contoh 2: Rotate Persegi Panjang

```javascript
const items = [
    "rectangle,10,5"  // Persegi panjang 10×5
];

const result = arrangePicnic(items, "rotate,90");
console.log(result);
// Output: [false]
// Hanya 1 item, tidak ada yang bertumpuk
```

**Penjelasan:**
- Persegi panjang 10×5 dirotasi 90° → menjadi 5×10
- Hanya ada 1 item, jadi tidak ada overlap

### Contoh 3: Segitiga dengan Scale

```javascript
const items = [
    "triangle,3,4,5",  // Segitiga siku-siku 3-4-5
    "circle,2"         // Lingkaran radius 2
];

const result = arrangePicnic(items, "scale,1.5");
console.log(result);
// Output: [true, true]
```

**Penjelasan:**
- Segitiga 3-4-5 → setelah scale 1.5× → 4.5-6-7.5
- Lingkaran radius 2 → setelah scale 1.5× → radius 3
- Kedua item bertumpuk di (0,0)

## ⚠️ Catatan Penting

1. **Asumsi Posisi**: Fungsi ini mengasumsikan semua item ditempatkan di koordinat (0,0), sehingga **semua item dengan ukuran > 0 akan selalu bertumpuk** satu sama lain.

2. **Rotasi**: Transformasi rotasi hanya mempengaruhi persegi panjang dengan menukar dimensi untuk rotasi 90° dan 270°. Rotasi 0°, 180°, 360° tidak mengubah dimensi.

3. **Formula Segitiga**: Menggunakan rumus Heron untuk menghitung luas segitiga dari panjang ketiga sisinya, lalu menghitung tinggi dengan asumsi sisi pertama sebagai alas.

4. **Validasi**: Fungsi tidak melakukan validasi input (misalnya cek apakah ketiga sisi bisa membentuk segitiga, atau nilai radius negatif).

## 🎓 Konsep Matematika

### Rumus Heron (untuk Segitiga)
```
s = (a + b + c) / 2
Luas = √[s(s-a)(s-b)(s-c)]
Tinggi = (2 × Luas) / alas
```

Dimana:
- `s` = semi-perimeter (setengah keliling)
- `a, b, c` = panjang sisi-sisi segitiga

---

**📝 Dibuat untuk pembelajaran pemrograman JavaScript**
