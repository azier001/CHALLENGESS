# 🏖️ Dokumentasi Fungsi `connectBeachFlags`

## 📋 Deskripsi

Fungsi `connectBeachFlags` adalah utility sederhana yang berfungsi untuk menggabungkan beberapa bendera pantai (flags) menjadi satu string dengan pemisah ganda strip (`--`). Fungsi ini sangat berguna ketika Anda ingin membuat representasi visual dari barisan bendera pantai atau menggabungkan beberapa flag menjadi satu identifier yang mudah dibaca.

## 🔧 Sintaks

```javascript
connectBeachFlags(flags)
```

## 📝 Parameter

| Parameter | Type    | Required | Deskripsi                                                    |
|-----------|---------|----------|--------------------------------------------------------------|
| `flags`   | Array   | ✅ Ya    | Array yang berisi string-string bendera yang akan digabung  |

### Detail Parameter:
- **flags**: Harus berupa array yang berisi elemen-elemen string. Setiap elemen array akan dianggap sebagai satu bendera yang akan dihubungkan dengan bendera lainnya menggunakan pemisah `--`.

## 🏁 Return Value

Fungsi ini mengembalikan **string** yang merupakan hasil penggabungan semua elemen dalam array `flags` dengan pemisah `--` di antara setiap elemen.

## 💻 Source Code

```javascript
function connectBeachFlags(flags) {
  // Menggabungkan semua elemen array dengan pemisah "--"
  return flags.join("--");
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Bendera Warna Dasar
```javascript
const colorFlags = ["merah", "biru", "kuning"];
const result = connectBeachFlags(colorFlags);
console.log(result);
```

**Output:**
```
merah--biru--kuning
```

### Contoh 2: Bendera Status Pantai
```javascript
const statusFlags = ["aman", "berenang", "diizinkan"];
const beachStatus = connectBeachFlags(statusFlags);
console.log(beachStatus);
```

**Output:**
```
aman--berenang--diizinkan
```

### Contoh 3: Satu Bendera Saja
```javascript
const singleFlag = ["bahaya"];
const warning = connectBeachFlags(singleFlag);
console.log(warning);
```

**Output:**
```
bahaya
```

### Contoh 4: Array Kosong
```javascript
const emptyFlags = [];
const result = connectBeachFlags(emptyFlags);
console.log(result);
```

**Output:**
```

```

## 🎨 Contoh Penggunaan dalam Konteks Nyata

### Sistem Peringatan Pantai
```javascript
// Membuat sistem peringatan pantai
function createBeachWarning(conditions) {
  const warningFlags = [];
  
  if (conditions.highWaves) warningFlags.push("GELOMBANG-TINGGI");
  if (conditions.strongCurrent) warningFlags.push("ARUS-KUAT");
  if (conditions.jellyfish) warningFlags.push("UBUR-UBUR");
  
  return connectBeachFlags(warningFlags);
}

// Penggunaan
const beachCondition = {
  highWaves: true,
  strongCurrent: false,
  jellyfish: true
};

const warning = createBeachWarning(beachCondition);
console.log(`Peringatan Pantai: ${warning}`);
```

**Output:**
```
Peringatan Pantai: GELOMBANG-TINGGI--UBUR-UBUR
```

## ⚠️ Catatan Penting

- Fungsi ini menggunakan method `join()` dari JavaScript Array
- Pemisah yang digunakan adalah `--` (double dash/ganda strip)
- Jika array kosong, akan mengembalikan string kosong
- Fungsi tidak melakukan validasi input, pastikan parameter adalah array yang valid

## 🔍 Tips Penggunaan

1. **Validasi Input**: Selalu pastikan parameter yang dikirim adalah array
2. **Konsistensi Naming**: Gunakan penamaan yang konsisten untuk flag (misalnya semua huruf kapital atau semua huruf kecil)
3. **Handling Edge Cases**: Pertimbangkan untuk menambahkan pengecekan array kosong jika diperlukan

## 📚 Method Terkait

- `Array.prototype.join()` - Method dasar yang digunakan dalam fungsi ini
- `String.prototype.split()` - Kebalikan dari join, untuk memisahkan string kembali menjadi array
