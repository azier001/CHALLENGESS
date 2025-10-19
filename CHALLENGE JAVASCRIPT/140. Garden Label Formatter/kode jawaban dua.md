# 🌱 Dokumentasi Fungsi `createGardenLabel`

## 📋 Deskripsi

Fungsi `createGardenLabel` digunakan untuk membuat label teks yang menampilkan informasi tanaman di kebun. Fungsi ini akan menghasilkan string yang berisi nama tanaman, umur tanaman, dan status pembungaan dalam format yang rapi dan mudah dibaca.

Fungsi ini sangat berguna untuk:
- Membuat label identifikasi tanaman
- Mencatat informasi tanaman dalam sistem kebun
- Menampilkan data tanaman di aplikasi atau website

---

## 📝 Parameter

Fungsi ini menerima 3 parameter:

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `plantName` | String | Nama tanaman yang akan dibuat labelnya | `"Mawar"`, `"Melati"` |
| `plantAge` | Number | Umur tanaman dalam satuan tahun | `2`, `5`, `10` |
| `isFlowering` | Boolean | Status apakah tanaman sedang berbunga atau tidak | `true`, `false` |

---

## 💻 Kode Fungsi

```javascript
function createGardenLabel(plantName, plantAge, isFlowering) {
  // Mengembalikan string label yang berisi informasi tanaman
  // Menggunakan template literal untuk format yang rapi
  // Operator ternary untuk mengubah boolean menjadi 'yes' atau 'no'
  return `Plant: ${plantName}, Age: ${plantAge} years, Flowering: ${isFlowering ? 'yes' : 'no'}`;
}
```

---

## 🎯 Cara Kerja

1. Fungsi menerima 3 informasi: nama tanaman, umur, dan status berbunga
2. Menggunakan **template literal** (backtick `` ` ``) untuk membuat string
3. Menggunakan **operator ternary** (`? :`) untuk mengubah nilai boolean `isFlowering`:
   - Jika `true` → ditampilkan sebagai `'yes'`
   - Jika `false` → ditampilkan sebagai `'no'`
4. Mengembalikan string yang sudah diformat

---

## 📊 Contoh Penggunaan

### Contoh 1: Tanaman yang Sedang Berbunga
```javascript
const label1 = createGardenLabel("Mawar", 2, true);
console.log(label1);
```

**Output:**
```
Plant: Mawar, Age: 2 years, Flowering: yes
```

### Contoh 2: Tanaman yang Tidak Berbunga
```javascript
const label2 = createGardenLabel("Kaktus", 5, false);
console.log(label2);
```

**Output:**
```
Plant: Kaktus, Age: 5 years, Flowering: no
```

### Contoh 3: Tanaman Muda
```javascript
const label3 = createGardenLabel("Melati", 1, false);
console.log(label3);
```

**Output:**
```
Plant: Melati, Age: 1 years, Flowering: no
```

### Contoh 4: Penggunaan Langsung
```javascript
console.log(createGardenLabel("Anggrek", 3, true));
```

**Output:**
```
Plant: Anggrek, Age: 3 years, Flowering: yes
```

---

## 🔍 Penjelasan Detail untuk Pemula

### Apa itu Template Literal?
Template literal adalah cara modern untuk membuat string di JavaScript menggunakan backtick (`` ` ``). Kita bisa memasukkan variabel langsung ke dalam string dengan `${variabel}`.

**Contoh:**
```javascript
const nama = "Bunga";
const pesan = `Halo, saya ${nama}`; // Output: "Halo, saya Bunga"
```

### Apa itu Operator Ternary?
Operator ternary adalah cara singkat untuk menulis kondisi if-else dalam satu baris.

**Format:** `kondisi ? nilaiJikaBenar : nilaiJikaSalah`

**Contoh:**
```javascript
const umur = 20;
const status = umur >= 18 ? "Dewasa" : "Anak-anak";
// Jika umur >= 18, maka "Dewasa", jika tidak maka "Anak-anak"
```

---

## ✅ Kesimpulan

Fungsi `createGardenLabel` adalah fungsi sederhana namun praktis untuk membuat label informasi tanaman. Dengan 3 parameter saja, kita bisa menghasilkan deskripsi tanaman yang lengkap dan terformat dengan baik. Fungsi ini mendemonstrasikan penggunaan template literal dan operator ternary, dua fitur penting dalam JavaScript modern.
