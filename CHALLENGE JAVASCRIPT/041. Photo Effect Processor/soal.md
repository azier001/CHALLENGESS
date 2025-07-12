# 📸 Photo Effect Processor

## 🎯 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function pemrosesan foto yang powerful untuk menerapkan berbagai efek pada array data gambar dengan level intensitas yang dapat disesuaikan.

---

## 📋 Requirements

### Spesifikasi Function

```javascript
function processPhoto(photoData, effectType, intensity)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `photoData` | `Array<number>` | Array berisi integer yang merepresentasikan data foto |
| `effectType` | `string` | Jenis efek yang akan diterapkan pada foto |
| `intensity` | `number` | Level intensitas untuk efek tertentu |

### Return Value

- **Type:** `Array<number>`
- **Deskripsi:** Array data foto yang telah dimodifikasi setelah menerapkan efek yang ditentukan

---

## ⚡ Jenis-jenis Effect

### 🔄 Reverse Effect
- **Trigger:** `effectType === "Reverse"`
- **Aksi:** Membalik urutan elemen dalam array `photoData`
- **Intensity:** Tidak digunakan untuk efek ini

### 🔊 Amplify Effect
- **Trigger:** `effectType === "Amplify"`
- **Aksi:** Mengalikan setiap elemen dalam `photoData` dengan nilai `intensity`
- **Intensity:** Nilai pengali yang diterapkan pada setiap elemen

### 🚫 Default Behavior
- **Trigger:** Nilai `effectType` lainnya
- **Aksi:** Mengembalikan array `photoData` asli tanpa perubahan
- **Intensity:** Tidak digunakan untuk efek ini

---

## 💡 Panduan Implementasi

### Poin Penting yang Perlu Diingat

- ✅ Handle tiga jenis efek utama: `"Reverse"`, `"Amplify"`, dan default
- ✅ Gunakan parameter `intensity` hanya untuk efek "Amplify"
- ✅ Return array asli untuk jenis efek yang tidak dikenali
- ✅ Pastikan function mengembalikan array berisi angka

### Expected Behavior

```javascript
// Contoh pola penggunaan
processPhoto([1, 2, 3, 4], "Reverse", 0);     // Harus membalik array
processPhoto([2, 4, 6], "Amplify", 3);        // Harus mengalikan dengan 3
processPhoto([1, 2, 3], "Unknown", 5);        // Harus return array asli
```

---

## 🎨 Ringkasan Visual

```
Input: photoData[] + effectType + intensity
         ↓
    ┌─────────────────────────────────────┐
    │        processPhoto()               │
    │                                     │
    │  ┌─────────────┐  ┌─────────────┐   │
    │  │  "Reverse"  │  │  "Amplify"  │   │
    │  │     ↓       │  │     ↓       │   │
    │  │  Membalik   │  │  Mengalikan │   │
    │  │   Urutan    │  │  dengan     │   │
    │  │             │  │  Intensity  │   │
    │  └─────────────┘  └─────────────┘   │
    │         ↓               ↓           │
    │  ┌─────────────────────────────────┐ │
    │  │        Array Termodifikasi     │ │
    │  └─────────────────────────────────┘ │
    └─────────────────────────────────────┘
         ↓
    Output: photoData[] yang telah dimodifikasi
```

---

## 🏆 Kriteria Keberhasilan

Implementasi Anda harus berhasil:

1. **Memproses Reverse Effect** - Membalik urutan elemen array dengan benar
2. **Memproses Amplify Effect** - Mengalikan setiap elemen dengan intensity dengan tepat
3. **Handle Unknown Effects** - Mengembalikan array asli untuk efek yang tidak dikenali
4. **Maintain Data Types** - Memastikan output tetap berupa array berisi angka

---

*Semoga berhasil dengan implementasi Anda! 🚀*
