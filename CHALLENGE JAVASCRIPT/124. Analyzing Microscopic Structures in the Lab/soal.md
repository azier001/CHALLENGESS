# 🔬 Analyzing Microscopic Structures in the Lab

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Anda adalah seorang ilmuwan di laboratorium yang memeriksa struktur mikroskopis. Tugas Anda adalah mengembangkan sebuah program yang membantu dalam menganalisis data laboratorium dengan mencari struktur tertentu dan memberikan laporan analisis yang detail.

---

## 🎯 Tujuan

Buat sebuah function bernama **`analyzeMicrostructures`** yang mencari melalui array struktur mikroskopis untuk menemukan struktur target tertentu dan mengembalikan laporan analisis yang terformat.

---

## 📥 Parameter Function

Function ini menerima dua parameter:

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `structures` | `array` | Array berisi string di mana setiap string merepresentasikan struktur mikroskopis |
| `target` | `string` | Struktur spesifik yang Anda cari dalam array |

---

## 📤 Output yang Diharapkan

Function harus mengembalikan sebuah **string** dengan salah satu format berikut:

### ✅ Ketika Target Ditemukan

```
Structure '[target]' found at position [position]. Total structures examined: [total].
```

### ❌ Ketika Target Tidak Ditemukan

```
Structure '[target]' not found. Total structures examined: [total].
```

---

## 📌 Catatan Penting

> **Pengindeksan Posisi:** Posisi harus dilaporkan sebagai `index + 1` agar lebih ramah pengguna.
> 
> - Elemen pertama berada di **posisi 1** (bukan 0)
> - Elemen kedua berada di **posisi 2** (bukan 1)
> - Dan seterusnya...

---

## 💡 Contoh Penggunaan

### Contoh 1: Target Ditemukan

**Input:**
```javascript
structures = ["cell", "bacteria", "virus", "protein"]
target = "virus"
```

**Output:**
```
Structure 'virus' found at position 3. Total structures examined: 4.
```

### Contoh 2: Target Tidak Ditemukan

**Input:**
```javascript
structures = ["cell", "bacteria", "virus", "protein"]
target = "enzyme"
```

**Output:**
```
Structure 'enzyme' not found. Total structures examined: 4.
```

---

## 🔧 Petunjuk Implementasi

- Gunakan method pencarian array untuk menemukan struktur target
- Ingat untuk mengkonversi index array ke posisi yang ramah pengguna (tambahkan 1)
- Tangani kasus berhasil dan gagal dengan tepat
- Pastikan output string sesuai dengan format yang ditentukan

---

## ✨ Poin Penting

Challenge ini membantu Anda berlatih:

- 🔍 Mencari data dalam array
- 📊 Analisis dan pelaporan data
- 🎨 Format dan interpolasi string
- 🧮 Manipulasi dan konversi index

---

**Selamat mengerjakan! 🚀**
