# 👤 Dokumentasi Fungsi `sketchInmateProfile`

## 📋 Deskripsi

Fungsi `sketchInmateProfile` adalah sebuah fungsi JavaScript yang digunakan untuk membuat sketsa profil karakter menggunakan ASCII art. Fungsi ini dapat menghasilkan profil yang menghadap ke kiri atau ke kanan berdasarkan parameter yang diberikan.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `features` | Array | Array yang berisi karakter-karakter ASCII untuk membentuk profil wajah |
| `facingLeft` | Boolean | Menentukan arah hadap profil (`true` = kiri, `false` = kanan) |

## 🎨 Karakter ASCII yang Umum Digunakan

| Karakter | Fungsi |
|----------|--------|
| `(` `)` | Bentuk wajah/kepala |
| `>` `<` | Hidung (arah menghadap) |
| `^` `v` | Mata atau bagian atas/bawah |
| `-` `_` | Garis horizontal |
| `\|` `/` | Garis vertikal atau diagonal |

## 💻 Kode Fungsi

```javascript
function sketchInmateProfile(features, facingLeft) {
    let result;
    
    if (facingLeft) {
        // Membalik urutan array features untuk profil menghadap kiri
        result = features.slice().reverse().join('');
        
        // Mengganti karakter '>' dengan '<' untuk profil menghadap kiri
        result = result.replace(/>/g, '<');
    } else {
        // Untuk profil menghadap kanan, langsung gabungkan features
        result = features.join('');
    }
    
    return result;
}
```

## 📝 Cara Kerja

1. **Profil Menghadap Kiri (`facingLeft = true`)**:
   - Array `features` dibalik urutannya menggunakan `slice().reverse()`
   - Semua karakter `>` diganti dengan `<` untuk menyesuaikan arah hidung
   - Hasil digabungkan menjadi string

2. **Profil Menghadap Kanan (`facingLeft = false`)**:
   - Array `features` langsung digabungkan tanpa dibalik
   - Tidak ada penggantian karakter

## 🔍 Contoh Penggunaan

### Contoh 1: Profil Menghadap Kanan
```javascript
const features = ['(', '^', '>', '_', ')'];
const result = sketchInmateProfile(features, false);
console.log(result);
```

**Output:**
```
(^>_)
```

### Contoh 2: Profil Menghadap Kiri
```javascript
const features = ['(', '^', '>', '_', ')'];
const result = sketchInmateProfile(features, true);
console.log(result);
```

**Output:**
```
)_<^(
```

### Contoh 3: Profil Lebih Kompleks
```javascript
const complexFeatures = ['(', ':', '>', '-', ')'];

// Menghadap kanan
console.log(sketchInmateProfile(complexFeatures, false)); // (:>-)

// Menghadap kiri  
console.log(sketchInmateProfile(complexFeatures, true));  // )-<:(
```

## 📊 Perbandingan Output

| Input Features | Menghadap Kanan | Menghadap Kiri |
|----------------|-----------------|----------------|
| `['(', '^', '>', '_', ')']` | `(^>_)` | `)_<^(` |
| `['(', ':', '>', '-', ')']` | `(:>-)` | `)-<:(` |
| `['[', 'o', '>', '~', ']']` | `[o>~]` | `]~<o[` |

## 🎯 Kegunaan

Fungsi ini berguna untuk:
- Membuat ASCII art profil karakter
- Sistem visualisasi sederhana dalam game text-based
- Membuat representasi karakter dalam aplikasi konsol
- Pembelajaran konsep manipulasi string dan array

## 🚀 Tips Penggunaan

1. **Konsistensi Karakter**: Pastikan karakter yang digunakan cocok untuk membentuk profil
2. **Urutan Features**: Susun array features sesuai dengan struktur wajah yang diinginkan
3. **Testing**: Coba kedua arah (kiri dan kanan) untuk memastikan hasil sesuai ekspektasi
4. **Kreativitas**: Eksplorasi berbagai kombinasi karakter ASCII untuk hasil yang unik

## ⚠️ Catatan Penting

- Fungsi ini hanya mengganti karakter `>` dengan `<`, karakter lain tidak berubah
- Hasil akan berbeda tergantung urutan elemen dalam array `features`
- Fungsi menggunakan `slice()` untuk membuat copy array sehingga array asli tidak berubah
