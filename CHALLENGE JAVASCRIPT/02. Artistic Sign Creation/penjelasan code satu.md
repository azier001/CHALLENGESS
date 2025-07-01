# 🎨 Penjelasan Fungsi `createArtisticSign`

Fungsi ini membuat "papan tanda artistik" dengan memisahkan karakter dekorasi menjadi dua kategori: **vine** (`&`) dan **knot** (`*`), kemudian menyusunnya dalam format yang indah.

---

## 📋 **Struktur Fungsi**

```javascript
function createArtisticSign(text, decorations)
```

### 🔧 **Parameter**
| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `text` | String | Teks utama yang akan dihias |
| `decorations` | String | String berisi karakter dekorasi (`&` dan `*`) |

---

## 🔍 **Analisis Kode Baris per Baris**

### 1️⃣ **Deklarasi Fungsi**
```javascript
function createArtisticSign(text, decorations) {
```
> **Fungsi:** Mendefinisikan fungsi dengan 2 parameter input

### 2️⃣ **Inisialisasi Variabel Penampung**
```javascript
let vines = ''; // untuk menyimpan karakter '&'
let knots = ''; // untuk menyimpan karakter '*'
```
> **Fungsi:** 
> - `vines` → Menampung semua karakter **vine** (`&`)
> - `knots` → Menampung semua karakter **knot** (`*`)

### 3️⃣ **Loop Iterasi**
```javascript
for (let i = 0; i < decorations.length; i++) {
```
> **Fungsi:** Melakukan perulangan untuk setiap karakter dalam string `decorations`

### 4️⃣ **Pemisahan Karakter Vine**
```javascript
if (decorations[i] === '&') {
    vines += '&'; // tambahkan ke vine decorations
}
```
> **Fungsi:** 
> - Mengecek apakah karakter saat ini adalah `&`
> - Jika ya, tambahkan ke variabel `vines`

### 5️⃣ **Pemisahan Karakter Knot**
```javascript
else if (decorations[i] === '*') {
    knots += '*'; // tambahkan ke knot decorations
}
```
> **Fungsi:** 
> - Mengecek apakah karakter saat ini adalah `*`
> - Jika ya, tambahkan ke variabel `knots`

### 6️⃣ **Penggabungan dan Return**
```javascript
return vines + text + knots;
```
> **Fungsi:** Menggabungkan dalam urutan: **vine + teks + knot**

---

## 🎯 **Contoh Penggunaan**

### Input & Output
```javascript
// Contoh 1
createArtisticSign("HELLO", "&*&**&")
// Output: "&&&HELLO**"

// Contoh 2  
createArtisticSign("WORLD", "***&&&**")
// Output: "&&&WORLD*****"

// Contoh 3
createArtisticSign("JS", "&*&*&*")
// Output: "&&&JS***"
```

### 📊 **Breakdown Proses**
| Input | Vine (`&`) | Text | Knot (`*`) | Final Result |
|-------|------------|------|------------|--------------|
| `"&*&**&"` | `"&&&"` | `"HELLO"` | `"**"` | `"&&&HELLO**"` |
| `"***&&&**"` | `"&&&"` | `"WORLD"` | `"*****"` | `"&&&WORLD*****"` |

---

## 💡 **Konsep Utama**

### 🔄 **Alur Kerja**
1. **Pisahkan** karakter dekorasi berdasarkan tipe
2. **Kumpulkan** semua vine (`&`) di awal
3. **Tempatkan** teks di tengah
4. **Tambahkan** semua knot (`*`) di akhir

### 🎨 **Format Output**
```
[VINE DECORATIONS] + [TEXT] + [KNOT DECORATIONS]
```

---

## ⚡ **Keunggulan Fungsi**

- ✅ **Fleksibel** - Dapat menangani berbagai kombinasi dekorasi
- ✅ **Terstruktur** - Output selalu konsisten (vine-text-knot)
- ✅ **Sederhana** - Logic yang mudah dipahami
- ✅ **Reusable** - Dapat digunakan berulang kali

