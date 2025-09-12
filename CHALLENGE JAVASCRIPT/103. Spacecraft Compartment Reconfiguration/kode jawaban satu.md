# 🚀 Dokumentasi Fungsi `reconfigureSpacecraft`

## 📝 Deskripsi

Fungsi `reconfigureSpacecraft` digunakan untuk mengatur ulang konfigurasi pesawat ruang angkasa dengan menambahkan spacer (pemisah) di antara setiap kompartemen. Fungsi ini berguna untuk memberikan jarak atau ruang tambahan antar kompartemen dalam desain pesawat ruang angkasa.

## 🔧 Sintaks

```javascript
reconfigureSpacecraft(compartmentSizes, spacerSize)
```

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `compartmentSizes` | Array | Array yang berisi ukuran-ukuran kompartemen pesawat ruang angkasa |
| `spacerSize` | Number | Ukuran spacer (pemisah) yang akan disisipkan di antara kompartemen |

## ↩️ Return Value

- **Tipe**: Array
- **Deskripsi**: Array baru yang berisi ukuran kompartemen asli dengan spacer yang disisipkan di antaranya

## 💻 Kode Fungsi

```javascript
function reconfigureSpacecraft(compartmentSizes, spacerSize) {
  // Array untuk menyimpan ukuran kompartemen yang sudah dikonfigurasi ulang
  const reconfiguredSizes = [];
  
  // Iterasi melalui setiap ukuran kompartemen
  for (let i = 0; i < compartmentSizes.length; i++) {
    // Tambahkan ukuran kompartemen ke array hasil
    reconfiguredSizes.push(compartmentSizes[i]);
    
    // Tambahkan spacer jika bukan elemen terakhir
    if (i !== compartmentSizes.length - 1) {
      reconfiguredSizes.push(spacerSize);
    }
  }
  
  // Kembalikan array yang sudah dikonfigurasi ulang
  return reconfiguredSizes;
}
```

## 📊 Cara Kerja

1. **Inisialisasi**: Fungsi membuat array kosong `reconfiguredSizes` untuk menyimpan hasil
2. **Iterasi**: Fungsi melakukan loop melalui setiap elemen dalam `compartmentSizes`
3. **Penambahan Kompartemen**: Setiap ukuran kompartemen ditambahkan ke array hasil
4. **Penambahan Spacer**: Spacer ditambahkan setelah setiap kompartemen, kecuali setelah kompartemen terakhir
5. **Return**: Mengembalikan array baru dengan konfigurasi yang sudah diperbarui

## 🔍 Contoh Penggunaan

### Contoh 1: Konfigurasi Dasar
```javascript
const compartments = [10, 20, 15];
const spacer = 5;
const result = reconfigureSpacecraft(compartments, spacer);
console.log(result);
```

**Output:**
```javascript
[10, 5, 20, 5, 15]
```

### Contoh 2: Satu Kompartemen
```javascript
const compartments = [25];
const spacer = 3;
const result = reconfigureSpacecraft(compartments, spacer);
console.log(result);
```

**Output:**
```javascript
[25]
```

### Contoh 3: Banyak Kompartemen
```javascript
const compartments = [8, 12, 6, 14, 10];
const spacer = 2;
const result = reconfigureSpacecraft(compartments, spacer);
console.log(result);
```

**Output:**
```javascript
[8, 2, 12, 2, 6, 2, 14, 2, 10]
```

## 📈 Tabel Contoh Transformasi

| Input Compartments | Spacer Size | Output Result |
|-------------------|-------------|---------------|
| `[10, 20, 15]` | `5` | `[10, 5, 20, 5, 15]` |
| `[25]` | `3` | `[25]` |
| `[5, 10]` | `2` | `[5, 2, 10]` |
| `[1, 2, 3, 4]` | `1` | `[1, 1, 2, 1, 3, 1, 4]` |

## ⚠️ Catatan Penting

- Fungsi ini tidak mengubah array asli (`compartmentSizes`), melainkan membuat array baru
- Spacer tidak akan ditambahkan setelah kompartemen terakhir
- Jika hanya ada satu kompartemen, tidak akan ada spacer yang ditambahkan
- Parameter `compartmentSizes` harus berupa array, dan `spacerSize` harus berupa number

## 🎯 Use Case

Fungsi ini berguna untuk:
- Merancang layout pesawat ruang angkasa dengan jarak antar kompartemen
- Menambahkan buffer zone atau safety space antar modul
- Perencanaan distribusi ruang dalam sistem modular
- Simulasi konfigurasi struktur dengan pemisah

---

*Dokumentasi ini dibuat untuk membantu pemahaman fungsi `reconfigureSpacecraft` dalam konteks pengembangan sistem pesawat ruang angkasa.* ✨
