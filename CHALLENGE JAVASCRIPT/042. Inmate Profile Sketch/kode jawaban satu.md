# 👤 Dokumentasi Fungsi `sketchInmateProfile`

## 📋 Deskripsi

Fungsi `sketchInmateProfile` adalah sebuah fungsi JavaScript yang digunakan untuk membuat sketsa profil karakter menggunakan ASCII art. Fungsi ini dapat menghasilkan profil yang menghadap ke kiri atau ke kanan berdasarkan parameter yang diberikan dengan cara membalik urutan karakter dan menukar arah panah/bracket.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `features` | Array | Array yang berisi karakter-karakter ASCII untuk membentuk profil wajah |
| `facingLeft` | Boolean | Menentukan arah hadap profil (`true` = kiri, `false` = kanan) |

## 🎨 Karakter ASCII yang Umum Digunakan

| Karakter | Fungsi | Berubah Saat Menghadap Kiri |
|----------|--------|-----------------------------|
| `<` `>` | Hidung/arah hadap | Ya, saling bertukar |
| `(` `)` | Bentuk wajah/kepala | Tidak |
| `[` `]` | Bracket wajah | Tidak |
| `^` `v` | Mata atau bagian atas/bawah | Tidak |
| `-` `_` | Garis horizontal | Tidak |
| `\|` `/` | Garis vertikal atau diagonal | Tidak |

## 💻 Kode Fungsi

```javascript
function sketchInmateProfile(features, facingLeft) {
    if (facingLeft) {
        // Membalik urutan array features untuk profil menghadap kiri
        features = features.reverse();
    }
    
    // Menggabungkan semua karakter dalam array menjadi string
    let sketch = features.join('');
    
    if (facingLeft) {
        // Menukar karakter '<' dan '>' untuk menyesuaikan arah hadap
        sketch = sketch.replace(/</g, '>');  // Ganti '<' dengan '>'
        sketch = sketch.replace(/>/g, '<');  // Ganti '>' dengan '<'
    }
    
    return sketch;
}
```

## 📝 Cara Kerja

1. **Profil Menghadap Kiri (`facingLeft = true`)**:
   - Array `features` dibalik urutannya menggunakan `reverse()`
   - Semua karakter digabungkan menjadi string
   - Karakter `<` dan `>` saling bertukar posisi untuk menyesuaikan arah hadap

2. **Profil Menghadap Kanan (`facingLeft = false`)**:
   - Array `features` tetap dalam urutan asli
   - Karakter langsung digabungkan tanpa penggantian

## 🔍 Contoh Penggunaan

### Contoh 1: Profil Dasar
```javascript
const features = ['(', '^', '>', '_', ')'];

// Menghadap kanan (default)
console.log(sketchInmateProfile(features, false));

// Menghadap kiri
console.log(sketchInmateProfile(features, true));
```

**Output:**
```
Menghadap kanan: (^>_)
Menghadap kiri:  )_<^(
```

### Contoh 2: Profil dengan Bracket
```javascript
const features = ['[', 'o', '<', '~', ']'];

// Menghadap kanan
console.log(sketchInmateProfile(features, false));

// Menghadap kiri
console.log(sketchInmateProfile(features, true));
```

**Output:**
```
Menghadap kanan: [o<~]
Menghadap kiri:  ]~>o[
```

### Contoh 3: Profil Kompleks dengan Berbagai Karakter
```javascript
const complexFeatures = ['(', ':', '>', '-', '<', ')'];

// Menghadap kanan
console.log(sketchInmateProfile(complexFeatures, false));

// Menghadap kiri
console.log(sketchInmateProfile(complexFeatures, true));
```

**Output:**
```
Menghadap kanan: (:>-<)
Menghadap kiri:  (>-<:)
```

## 📊 Perbandingan Output

| Input Features | Menghadap Kanan | Menghadap Kiri |
|----------------|-----------------|----------------|
| `['(', '^', '>', '_', ')']` | `(^>_)` | `)_<^(` |
| `['[', 'o', '<', '~', ']']` | `[o<~]` | `]~>o[` |
| `['(', ':', '>', '-', '<', ')']` | `(:>-<)` | `(>-<:)` |
| `['{', '*', '>', '=', '}']` | `{*>=}` | `}=<*{` |

## 🎯 Kegunaan

Fungsi ini berguna untuk:
- Membuat ASCII art profil karakter dalam game
- Sistem visualisasi sederhana dalam aplikasi konsol
- Representasi karakter dalam chat bot atau aplikasi text-based
- Pembelajaran konsep manipulasi string dan array
- Membuat emoticon atau avatar sederhana

## 🚀 Tips Penggunaan

1. **Urutan Features**: Susun array features dari kiri ke kanan untuk profil menghadap kanan
2. **Karakter Panah**: Gunakan `<` dan `>` untuk hidung agar bisa bertukar arah
3. **Simetri**: Pertimbangkan bagaimana karakter akan terlihat setelah dibalik
4. **Testing**: Selalu test kedua arah untuk memastikan hasil sesuai ekspektasi
5. **Kreativitas**: Eksplorasi berbagai kombinasi karakter ASCII

## ⚠️ Catatan Penting

- **Mutasi Array**: Fungsi ini mengubah array `features` asli karena menggunakan `reverse()` tanpa `slice()`
- **Penggantian Karakter**: Hanya karakter `<` dan `>` yang bertukar posisi saat menghadap kiri
- **Urutan Operasi**: Pembalikan array dilakukan sebelum penggabungan string
- **Case Sensitive**: Penggantian karakter hanya berlaku untuk `<` dan `>`, bukan untuk karakter lain

## 🔧 Alternatif Implementasi (Tanpa Mutasi)

Jika ingin menghindari mutasi array asli:

```javascript
function sketchInmateProfile(features, facingLeft) {
    let workingFeatures = facingLeft ? features.slice().reverse() : features;
    let sketch = workingFeatures.join('');
    
    if (facingLeft) {
        sketch = sketch.replace(/</g, '>');
        sketch = sketch.replace(/>/g, '<');
    }
    
    return sketch;
}
```
