# 🧺 Dokumentasi Fungsi `arrangePicnic`

## 📋 Deskripsi

Fungsi `arrangePicnic` adalah fungsi yang digunakan untuk mengatur dan mengecek tumpang tindih (overlap) item-item piknik setelah dilakukan transformasi geometris. Fungsi ini menerima daftar bentuk geometris (lingkaran dan bentuk lainnya) dan menerapkan transformasi seperti rotasi atau scaling, kemudian mengecek apakah ada item yang bertumpuk satu sama lain.

## 🎯 Tujuan Fungsi

- Melakukan transformasi geometris (rotasi atau scaling) pada berbagai bentuk
- Menerapkan transformasi pada dimensi atau koordinat item
- Mendeteksi apakah ada item yang saling tumpang tindih setelah transformasi

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `items` | `Array<String>` | Array berisi string yang merepresentasikan bentuk geometris dengan formatnya masing-masing |
| `transformation` | `String` | String yang berisi jenis transformasi dan nilainya, dipisahkan koma (contoh: `"scale,2"` atau `"rotate,90"`) |

### Format String Items

| Bentuk | Format | Contoh |
|--------|--------|--------|
| **Lingkaran** | `"circle,radius"` | `"circle,5"` |
| **Bentuk Lain** | `"shape,dimensi1,dimensi2,..."` | `"rectangle,4,6"` |

### Jenis Transformasi

| Transformasi | Format | Deskripsi | Contoh |
|--------------|--------|-----------|--------|
| **Rotate** | `"rotate,derajat"` | Memutar bentuk dengan sudut tertentu (dalam derajat) | `"rotate,90"` |
| **Scale** | `"scale,faktor"` | Memperbesar/memperkecil ukuran dengan faktor pengali | `"scale,2"` (2x lipat) |

## 📤 Output

Fungsi mengembalikan array berisi nilai boolean:
- `true` = Item tersebut **bertumpuk** dengan item lain yang ada setelahnya dalam array
- `false` = Item tersebut **tidak bertumpuk** dengan item lain yang ada setelahnya

**Contoh Output:**
```javascript
[true, false, false]
// Item ke-0 bertumpuk dengan item lain
// Item ke-1 tidak bertumpuk
// Item ke-2 tidak bertumpuk
```

## 💻 Source Code

```javascript
function arrangePicnic(items, transformation) {
  // Parse (mengurai) string transformasi menjadi tipe dan nilai
  const [transformationType, transformationValue] = transformation.split(',');
  
  // Fungsi helper untuk mengecek apakah dua item saling bertumpuk
  function checkOverlap(item1, item2) {
    // Implementasi logika pengecekan overlap berdasarkan bentuk dan dimensi item
    // Return true jika item bertumpuk, false jika tidak
    // Dapat menggunakan formula geometri atau library untuk menghitung overlap
    // Untuk kesederhanaan, asumsikan item overlap jika dimensi mereka berpotongan
    
    const [shape1, ...dimensions1] = item1.split(',');
    const [shape2, ...dimensions2] = item2.split(',');
    
    // Cek overlap untuk dua lingkaran
    if (shape1 === 'circle' && shape2 === 'circle') {
      const [radius1] = dimensions1.map(Number);
      const [radius2] = dimensions2.map(Number);
      
      // Asumsi lingkaran berada di titik pusat yang sama (origin)
      return radius1 + radius2 > 0;
    }
    
    // Tambahkan kondisi untuk kombinasi bentuk lainnya
    // ...
    
    // Default: tidak ada overlap
    return false;
  }
  
  // Terapkan transformasi pada setiap item
  const transformedItems = items.map(item => {
    // Parse bentuk dan dimensi item
    const [shape, ...dimensions] = item.split(',');
    
    // Terapkan transformasi berdasarkan tipe transformasi
    if (transformationType === 'rotate') {
      const angle = parseInt(transformationValue);
      
      // Lakukan logika rotasi berdasarkan sudut
      // Update koordinat atau dimensi item sesuai kebutuhan
      // ...
      
    } else if (transformationType === 'scale') {
      const factor = parseInt(transformationValue);
      
      // Lakukan logika scaling berdasarkan faktor
      // Kalikan dimensi item dengan faktor pengali
      // ...
    }
    
    // Return item yang sudah ditransformasi
    return `${shape},${dimensions.join(',')}`;
  });
  
  // Cek overlap antara item-item yang sudah ditransformasi
  const overlaps = transformedItems.map((item, index) => {
    // Loop melalui item-item setelah item saat ini
    for (let i = index + 1; i < transformedItems.length; i++) {
      if (checkOverlap(item, transformedItems[i])) {
        return true; // Overlap ditemukan
      }
    }
    return false; // Tidak ada overlap
  });
  
  return overlaps;
}
```

## 🔧 Cara Kerja

### 1️⃣ **Parsing Transformasi**
Fungsi memisahkan string transformasi menjadi:
- `transformationType`: Jenis transformasi (rotate/scale)
- `transformationValue`: Nilai transformasi (sudut derajat atau faktor pengali)

### 2️⃣ **Fungsi Helper: checkOverlap**
Fungsi internal yang mengecek apakah dua item bertumpuk:
- Memparse bentuk dan dimensi dari kedua item
- **Untuk dua lingkaran**: Mengecek apakah jumlah radius > 0 (asumsi di titik pusat yang sama)
- **Untuk bentuk lain**: Dapat ditambahkan logika sesuai kebutuhan
- Return `true` jika bertumpuk, `false` jika tidak

### 3️⃣ **Transformasi Item**
Menerapkan transformasi pada setiap item:
- **Rotate**: Memutar item berdasarkan sudut (dalam derajat)
- **Scale**: Mengalikan dimensi dengan faktor pengali

**Catatan:** Implementasi transformasi masih berupa placeholder (perlu diimplementasikan lengkap)

### 4️⃣ **Deteksi Overlap**
Untuk setiap item, mengecek apakah item tersebut bertumpuk dengan item-item setelahnya dalam array:
- Loop dimulai dari `index + 1` (hanya cek item setelahnya, bukan sebelumnya)
- Jika ada overlap dengan salah satu item, return `true`
- Jika tidak ada overlap sama sekali, return `false`

## 📚 Contoh Penggunaan

### Contoh 1: Scale Dua Lingkaran

```javascript
const items = [
    "circle,5",  // Lingkaran radius 5
    "circle,3"   // Lingkaran radius 3
];

const result = arrangePicnic(items, "scale,2");
console.log(result);
// Output: [true, false]
```

**Penjelasan:**
- Item ke-0 (circle,5) dicek dengan item ke-1 → Overlap ditemukan → `true`
- Item ke-1 (circle,3) tidak ada item setelahnya → `false`
- Kedua lingkaran overlap karena berada di titik pusat yang sama

### Contoh 2: Rotate Tiga Lingkaran

```javascript
const items = [
    "circle,4",
    "circle,2",
    "circle,6"
];

const result = arrangePicnic(items, "rotate,45");
console.log(result);
// Output: [true, true, false]
```

**Penjelasan:**
- Item ke-0 overlap dengan item ke-1 atau ke-2 → `true`
- Item ke-1 overlap dengan item ke-2 → `true`
- Item ke-2 tidak ada item setelahnya → `false`

### Contoh 3: Scale Satu Lingkaran

```javascript
const items = [
    "circle,10"  // Hanya 1 lingkaran
];

const result = arrangePicnic(items, "scale,3");
console.log(result);
// Output: [false]
```

**Penjelasan:**
- Hanya ada 1 item, tidak ada item lain untuk dicek
- Hasil: tidak ada overlap → `false`

## ⚠️ Catatan Penting

1. **Implementasi Tidak Lengkap**: 
   - Logika transformasi (rotate dan scale) masih berupa placeholder (`// ...`)
   - Perlu implementasi lengkap untuk mengubah dimensi atau koordinat item
   - Fungsi `checkOverlap` hanya menghandle dua lingkaran

2. **Asumsi Posisi**: 
   - Fungsi `checkOverlap` untuk lingkaran mengasumsikan semua lingkaran berada di titik pusat (origin) yang sama
   - Dengan asumsi ini, dua lingkaran dengan radius > 0 akan **selalu bertumpuk**

3. **Arah Pengecekan**: 
   - Fungsi hanya mengecek overlap dengan item **setelahnya** dalam array (index + 1)
   - Tidak mengecek overlap dengan item sebelumnya (untuk menghindari duplikasi pengecekan)

4. **Type Conversion**: 
   - `parseInt()` digunakan untuk mengkonversi string ke integer
   - Pastikan nilai transformasi adalah angka valid

5. **Ekstensibilitas**: 
   - Fungsi dapat diperluas untuk menangani bentuk lain (segitiga, persegi panjang, dll)
   - Perlu menambahkan kondisi di `checkOverlap` untuk kombinasi bentuk yang berbeda

## 🎨 Alur Logika

```
Input: items array & transformation string
    ↓
1. Parse transformation → [type, value]
    ↓
2. Transform setiap item
   - Parse shape & dimensions
   - Terapkan rotate/scale
   - Return transformed item
    ↓
3. Untuk setiap transformed item:
   - Cek overlap dengan item setelahnya
   - Jika ada overlap → true
   - Jika tidak ada → false
    ↓
Output: Array of boolean [true/false]
```

## 🔨 Pengembangan Lebih Lanjut

Untuk membuat fungsi ini lebih lengkap, perlu ditambahkan:

### 1. Implementasi Transformasi Scale
```javascript
if (transformationType === 'scale') {
    const factor = parseInt(transformationValue);
    const scaledDimensions = dimensions.map(d => Number(d) * factor);
    return `${shape},${scaledDimensions.join(',')}`;
}
```

### 2. Implementasi Transformasi Rotate
Perlu logika khusus tergantung bentuk (misalnya rotasi persegi panjang menukar width-height untuk 90°/270°)

### 3. Overlap Check untuk Bentuk Lain
Tambahkan kondisi untuk rectangle-rectangle, circle-rectangle, triangle-triangle, dll.

### 4. Sistem Koordinat
Tambahkan koordinat (x, y) untuk setiap item agar overlap check lebih akurat

---

**📝 Dibuat untuk pembelajaran pemrograman JavaScript**
