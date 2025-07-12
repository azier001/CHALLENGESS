# 📸 Dokumentasi Fungsi processPhoto

## 🎯 Deskripsi Fungsi

Fungsi `processPhoto` adalah utilitas untuk memproses data foto dengan berbagai efek visual. Fungsi ini dapat membalik urutan data foto (reverse) atau memperkuat intensitas nilai-nilai dalam data foto (amplify).

## 📋 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|-------|
| `photoData` | Array | Array yang berisi data foto (bisa berupa pixel values, RGB values, dll) | ✅ |
| `effectType` | String | Jenis efek yang ingin diterapkan (`"Reverse"` atau `"Amplify"`) | ✅ |
| `intensity` | Number | Nilai pengali untuk efek amplify (hanya digunakan jika effectType = "Amplify") | ⚠️ |

## 🎨 Jenis Efek yang Tersedia

| Efek | Deskripsi | Contoh Penggunaan |
|------|-----------|-------------------|
| `"Reverse"` | Membalik urutan elemen dalam array | Membuat efek mirror/cermin |
| `"Amplify"` | Mengalikan setiap elemen dengan nilai intensity | Memperkuat brightness/kontras |
| Lainnya | Mengembalikan data asli tanpa perubahan | Untuk efek yang belum didefinisikan |

## 💻 Kode Fungsi

```javascript
function processPhoto(photoData, effectType, intensity) {
    
    if (effectType === "Reverse") {
        return photoData.slice().reverse();
        
    } else if (effectType === "Amplify") {
        return photoData.map(element => element * intensity);
        
    } else {
        return photoData;
    }
}
```

## 📝 Contoh Penggunaan

### 1. Efek Reverse (Membalik Data)

```javascript
const originalData = [10, 20, 30, 40, 50];
const reversedPhoto = processPhoto(originalData, "Reverse", 0);

console.log("Data asli:", originalData);
console.log("Data setelah reverse:", reversedPhoto);
```

**Output:**
```
Data asli: [10, 20, 30, 40, 50]
Data setelah reverse: [50, 40, 30, 20, 10]
```

### 2. Efek Amplify (Memperkuat Intensitas)

```javascript
const originalData = [1, 2, 3, 4, 5];
const amplifiedPhoto = processPhoto(originalData, "Amplify", 2.5);

console.log("Data asli:", originalData);
console.log("Data setelah amplify:", amplifiedPhoto);
```

**Output:**
```
Data asli: [1, 2, 3, 4, 5]
Data setelah amplify: [2.5, 5, 7.5, 10, 12.5]
```

### 3. Efek Tidak Dikenal

```javascript
const originalData = [100, 200, 300];
const unchangedPhoto = processPhoto(originalData, "Blur", 1.5);

console.log("Data asli:", originalData);
console.log("Data tidak berubah:", unchangedPhoto);
```

**Output:**
```
Data asli: [100, 200, 300]
Data tidak berubah: [100, 200, 300]
```

## ⚠️ Catatan Penting

- **Reverse Effect**: Menggunakan `slice()` untuk membuat copy array baru sebelum di-reverse, sehingga array asli tidak berubah
- **Amplify Effect**: Parameter `intensity` hanya digunakan untuk efek "Amplify". Untuk efek lain, parameter ini diabaikan
- **Default Behavior**: Jika `effectType` tidak dikenali, fungsi akan mengembalikan data asli tanpa perubahan
- **Data Safety**: Fungsi ini tidak memodifikasi array asli, melainkan mengembalikan array baru

## 🔧 Tips Penggunaan

1. **Untuk efek Reverse**: Nilai `intensity` tidak berpengaruh, bisa diisi angka berapa saja
2. **Untuk efek Amplify**: Gunakan nilai `intensity` sesuai kebutuhan:
   - `< 1`: Mengurangi intensitas
   - `= 1`: Tidak ada perubahan
   - `> 1`: Meningkatkan intensitas
3. **Validasi Data**: Pastikan `photoData` adalah array yang valid sebelum memanggil fungsi

## 🎭 Contoh Penggunaan dalam Konteks Nyata

```javascript
// Simulasi data RGB pixel
const pixelData = [128, 64, 192, 255, 0, 128];

// Membuat efek mirror
const mirrorEffect = processPhoto(pixelData, "Reverse");

// Membuat efek brightness
const brighterPhoto = processPhoto(pixelData, "Amplify", 1.2);

// Efek yang belum tersedia
const originalPhoto = processPhoto(pixelData, "Sepia", 0.8);
```

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi processPhoto dengan mudah dan praktis.*
