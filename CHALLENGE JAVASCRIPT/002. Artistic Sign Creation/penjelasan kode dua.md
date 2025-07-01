# 🎨 Analisis Fungsi `createArtisticSign`

## 📋 **Overview**
Fungsi ini bertujuan untuk membuat "tanda artistik" dengan menggabungkan teks dan dekorasi yang telah dimodifikasi.

---

## 🔍 **Breakdown Kode Baris per Baris**

### **Baris 1: Deklarasi Fungsi**
```javascript
function createArtisticSign(text, decorations) {
```
> 🏗️ **Fungsi**: Mendeklarasikan fungsi dengan nama `createArtisticSign`
> 
> **Parameter:**
> - `text` → Teks utama yang akan ditampilkan
> - `decorations` → String berisi karakter dekorasi

---

### **Baris 2: Variabel Vines**
```javascript
const vines = decorations.replace(/\*/g, '');
```
> 🌿 **Vines**: Membuat konstanta untuk "sulur-sulur"
> 
> **Proses:**
> - Mengambil string `decorations`
> - Menghapus **semua** karakter asterisk (`*`) menggunakan regex
> - `/\*/g` → Pattern untuk mencari `*` secara global
> - Hasil disimpan dalam `vines`

---

### **Baris 3: Variabel Knots**
```javascript
const knots = decorations.replace(/&/g, '');
```
> 🪢 **Knots**: Membuat konstanta untuk "simpul-simpul"
> 
> **Proses:**
> - Mengambil string `decorations` yang sama
> - Menghapus **semua** karakter ampersand (`&`) menggunakan regex
> - `/&/g` → Pattern untuk mencari `&` secara global
> - Hasil disimpan dalam `knots`

---

### **Baris 4: Return Statement**
```javascript
return vines + text + knots;
```
> 🔄 **Output**: Mengembalikan penggabungan string
> 
> **Urutan:** `vines` + `text` + `knots`

---

### **Baris 5: Penutup Fungsi**
```javascript
}
```
> 🏁 **End**: Menutup blok fungsi

---

## ⚠️ **Analisis Masalah**

| **Issue** | **Deskripsi** |
|-----------|---------------|
| 🐛 **Logic Bug** | Kedua variabel `vines` dan `knots` memproses string yang sama |
| 🤔 **Redundancy** | Jika `decorations` hanya berisi `*` dan `&`, hasilnya tidak konsisten |
| 📝 **Naming** | Nama variabel tidak mencerminkan fungsi sebenarnya |

---

## 🎯 **Contoh Penggunaan**

### **Input:**
```javascript
createArtisticSign("WELCOME", "*&*&*");
```

### **Proses:**
```javascript
// decorations = "*&*&*"
const vines = "*&*&*".replace(/\*/g, ''); // = "&&&"
const knots = "*&*&*".replace(/&/g, '');  // = "***"
return "&&&" + "WELCOME" + "***";
```

### **Output:**
```
&&&WELCOME***
```

---

## 💡 **Saran Perbaikan**

```javascript
function createArtisticSign(text, leftDecor, rightDecor) {
  return leftDecor + text + rightDecor;
}

// Atau dengan approach yang lebih clear:
function createArtisticSign(text, decorations) {
  const vines = decorations.match(/\*/g)?.join('') || '';
  const knots = decorations.match(/&/g)?.join('') || '';
  return vines + text + knots;
}
```

---

## 📊 **Regex Reference**

| **Pattern** | **Deskripsi** | **Contoh** |
|-------------|---------------|------------|
| `/\*/g` | Cari semua karakter `*` | `"a*b*c"` → matches: `*`, `*` |
| `/&/g` | Cari semua karakter `&` | `"a&b&c"` → matches: `&`, `&` |
| `g` flag | Global search | Cari semua, bukan hanya yang pertama |

---

*📝 **Note**: Fungsi ini memiliki konsep yang menarik tetapi implementasinya perlu diperbaiki untuk hasil yang lebih konsisten dan dapat diprediksi.*
