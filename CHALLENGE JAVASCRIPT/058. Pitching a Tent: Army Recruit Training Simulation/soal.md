# 🏕️ Pitching a Tent: Simulasi Pelatihan Rekrut Militer

## 📋 Gambaran Challenge
**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan upaya seorang rekrut militer untuk mendirikan tenda selama pelatihan dasar. Rekrut harus menavigasi berbagai langkah sambil mengelola kesabaran dan percobaan yang terbatas.

---

## 🎯 Tujuan

Implementasikan function bernama `pitchTent` yang memproses serangkaian langkah mendirikan tenda sambil menangani skenario yang berbeda berdasarkan kesabaran rekrut dan attempts yang tersedia.

---

## 📝 Spesifikasi Function

### Function Signature
```javascript
function pitchTent(steps, patience, attempts)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `steps` | `Array<string>` | Array string yang merepresentasikan langkah-langkah mendirikan tenda |
| `patience` | `Number` | Integer yang merepresentasikan tingkat kesabaran awal rekrut |
| `attempts` | `Number` | Integer yang merepresentasikan jumlah percobaan yang diizinkan |

### Return Value
- **Type:** `String`
- **Sukses:** `"Tent pitched successfully!"`
- **Gagal:** `"Failed to pitch the tent!"`

---

## ⚙️ Logic Implementasi

Function harus mengimplementasikan perilaku berikut:

### 🔄 Pemrosesan Step
1. **Iterasi** melalui setiap step dalam array `steps`
2. **Analisis** setiap step untuk keyword spesifik:
   - 🔴 **"difficult"** → Kurangi `patience` sebesar 1
   - 🟢 **"easy"** → Skip step tersebut (gunakan array slicing)
   - ⚪ **Tidak ada** → Lanjutkan ke step berikutnya (gunakan statement `continue`)

### 🛑 Kondisi Terminasi
- **Hentikan langsung** jika:
  - `patience` mencapai `0`, ATAU
  - Semua `attempts` habis
- Gunakan statement `break` untuk keluar dari loop

### ✅ Kriteria Sukses
- Return pesan sukses jika **semua steps selesai** sebelum kehabisan patience atau attempts
- Jika tidak, return pesan gagal

---

## 🚀 Perilaku yang Diharapkan

```javascript
// Contoh skenario penggunaan:

// Skenario 1: Penyelesaian sukses
pitchTent(["setup ground", "easy assembly", "difficult knots"], 2, 3)
// Expected: "Tent pitched successfully!"

// Skenario 2: Patience habis
pitchTent(["difficult start", "difficult middle", "difficult end"], 1, 5)
// Expected: "Failed to pitch the tent!"
```

---

## 💡 Konsep Programming Utama

- **Array iteration** dan processing
- **String manipulation** dan deteksi keyword
- **Conditional logic** dengan multiple branches
- **Loop control** menggunakan `break` dan `continue`
- **Array slicing** untuk skipping step
- **State management** (tracking patience dan attempts)

---

## 🎖️ Catatan Pelatihan

> Simulasi ini mencerminkan skenario pelatihan militer nyata dimana rekrut harus:
> - Mengikuti prosedur yang tepat di bawah tekanan
> - Mengelola resource terbatas (waktu, kesabaran, attempts)
> - Beradaptasi dengan tingkat kesulitan yang bervariasi
> - Menyelesaikan tugas dengan sukses meskipun ada rintangan

**Semoga berhasil, rekrut! 🫡**
