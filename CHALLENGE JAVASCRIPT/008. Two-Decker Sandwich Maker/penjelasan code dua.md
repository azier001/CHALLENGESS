# 🥪 Fungsi `makeSandwich` - Panduan Pemula

## 🎯 Apa itu Fungsi `makeSandwich`?

Fungsi `makeSandwich` adalah sebuah program sederhana yang **membuat sandwich virtual** dengan aturan tertentu. Seperti di kehidupan nyata, kita perlu memilih bahan yang tepat untuk membuat sandwich yang enak!

---

## 📝 Kode Lengkap

```javascript
function makeSandwich(topBread, filling, bottomBread) {
  const validBreads = ["white", "wheat"];
  const validFillings = ["cheese", "ham", "lettuce"];
  
  if (!validBreads.includes(topBread) || !validBreads.includes(bottomBread)) {
    return "Invalid bread type!";
  }
  
  if (!validFillings.includes(filling)) {
    return "Invalid filling!";
  }
  
  if (topBread !== bottomBread) {
    return "Mismatched bread types!";
  }
  
  return `Delicious ${filling} sandwich on ${topBread} bread!`;
}
```

## 🔧 Struktur Fungsi

### 🔍 Parameter (Input):
- **`topBread`** → Roti bagian atas
- **`filling`** → Isi sandwich 
- **`bottomBread`** → Roti bagian bawah

---

## 🛡️ Sistem Validasi (Pengecekan)

Fungsi ini memiliki **3 sistem pengecekan** untuk memastikan sandwich dibuat dengan benar:

### ✅ **Pengecekan 1: Jenis Roti Valid**
```javascript
const validBreads = ["white", "wheat"];
if (!validBreads.includes(topBread) || !validBreads.includes(bottomBread)) {
    return "Invalid bread type!";
}
```
- **Yang diizinkan:** `"white"` atau `"wheat"`
- **Jika salah:** Muncul pesan *"Invalid bread type!"*

### ✅ **Pengecekan 2: Isi Valid**
```javascript
const validFillings = ["cheese", "ham", "lettuce"];
if (!validFillings.includes(filling)) {
    return "Invalid filling!";
}
```
- **Yang diizinkan:** `"cheese"`, `"ham"`, atau `"lettuce"`
- **Jika salah:** Muncul pesan *"Invalid filling!"*

### ✅ **Pengecekan 3: Roti Harus Same-Same**
```javascript
if (topBread !== bottomBread) {
    return "Mismatched bread types!";
}
```
- **Aturan:** Roti atas dan bawah harus jenis yang sama
- **Jika beda:** Muncul pesan *"Mismatched bread types!"*

---

## 🎉 Hasil Akhir

Jika semua pengecekan **LOLOS**, fungsi akan mengembalikan:
```javascript
return `Delicious ${filling} sandwich on ${topBread} bread!`;
```

**Contoh output:** *"Delicious cheese sandwich on white bread!"*

---

## 🧪 Contoh Penggunaan

### ✅ **Berhasil:**
```javascript
makeSandwich("white", "cheese", "white")
// Output: "Delicious cheese sandwich on white bread!"

makeSandwich("wheat", "ham", "wheat")
// Output: "Delicious ham sandwich on wheat bread!"
```

### ❌ **Gagal - Roti tidak valid:**
```javascript
makeSandwich("sourdough", "cheese", "sourdough")
// Output: "Invalid bread type!"
```

### ❌ **Gagal - Isi tidak valid:**
```javascript
makeSandwich("white", "pizza", "white")
// Output: "Invalid filling!"
```

### ❌ **Gagal - Roti tidak matching:**
```javascript
makeSandwich("white", "cheese", "wheat")
// Output: "Mismatched bread types!"
```

---

## 🔍 Konsep Programming yang Dipelajari

| Konsep | Penjelasan |
|--------|------------|
| **Function** | Blok kode yang dapat digunakan berulang kali |
| **Parameters** | Input yang diterima fungsi |
| **Array** | Kumpulan data (seperti `validBreads`) |
| **Conditional (if)** | Pengecekan kondisi |
| **String Validation** | Memastikan input sesuai kriteria |
| **Return Statement** | Mengembalikan hasil dari fungsi |
| **Template Literals** | Menggabungkan string dengan variabel (`${}`) |

---

## 💡 Tips untuk Pemula

1. **Baca kode dari atas ke bawah** - seperti membaca cerita
2. **Pahami setiap pengecekan** - mengapa diperlukan?
3. **Coba ubah nilai input** - lihat hasilnya berubah
4. **Perhatikan urutan pengecekan** - yang pertama akan dieksekusi duluan

---

## 🚀 Tantangan Selanjutnya

Setelah memahami fungsi ini, coba:
- Tambahkan jenis roti baru
- Tambahkan isi sandwich baru  
- Buat fungsi serupa untuk makanan lain
- Tambahkan pengecekan untuk jumlah isi

**Selamat belajar coding! 🎯**
