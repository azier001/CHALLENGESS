# 🦗 Entomologist's Specimen Sorter

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Sebagai seorang entomologist yang bekerja di museum sejarah alam bergengsi, Anda ditugaskan untuk mengorganisir dan menganalisis koleksi spesimen serangga. Keahlian Anda dibutuhkan untuk membuat sistem sorting yang efisien yang akan membantu para peneliti mengakses spesimen dengan cepat berdasarkan ukurannya.

---

## 🎯 Tujuan

Buat sebuah function bernama `sortInsectSpecimens` yang memproses data spesimen sesuai dengan protokol museum tertentu.

### Function Signature
```javascript
function sortInsectSpecimens(specimens) {
    // Implementasi Anda di sini
}
```

---

## 📝 Requirements

Function Anda harus melakukan operasi berikut secara berurutan:

### Step 1: Protokol Penyesuaian Ukuran
- **Increment ukuran** dari setiap **spesimen ketiga** dalam array sebesar `1`
- Ini memperhitungkan variasi pengukuran akibat metode preservasi

### Step 2: Organisasi Spesimen
- **Sort array** dalam **urutan ascending** berdasarkan ukuran spesimen
- Spesimen yang lebih kecil harus muncul pertama dalam koleksi

### Step 3: Return Hasil
- **Return array yang sudah di-sort** dengan semua penyesuaian yang telah diterapkan

---

## 🔧 Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `specimens` | `Array<number>` | Sebuah array berisi angka yang mewakili ukuran spesimen serangga dalam milimeter |

---

## 📤 Return Value

| Type | Deskripsi |
|------|-----------|
| `Array<number>` | Array yang sudah di-sort berisi angka yang mewakili ukuran spesimen yang telah disesuaikan dan diorganisir |

---

## 💡 Contoh Penggunaan

```javascript
// Contoh input
const specimens = [5, 8, 3, 12, 7, 15, 2, 9];

// Function call
const sortedSpecimens = sortInsectSpecimens(specimens);

// Proses yang diharapkan:
// 1. Sesuaikan setiap spesimen ke-3: [5, 8, 4, 12, 7, 16, 2, 9]
//    (posisi 2, 5 di-increment: 3→4, 15→16)
// 2. Sort ascending: [2, 4, 5, 7, 8, 9, 12, 16]
```

---

## 🔍 Catatan Implementasi Penting

- **Array indexing**: Ingat bahwa indeks array dimulai dari 0
- **Identifikasi spesimen ketiga**: Elemen pada indeks 2, 5, 8, 11, dst.
- **Metode sorting**: Gunakan algoritma sorting yang sesuai untuk data numerik
- **Integritas data**: Pastikan tipe data asli tetap terjaga

---

## 🏛️ Konteks Museum

Sistem sorting ini membantu kurator museum untuk:
- **Mengorganisir spesimen** berdasarkan ukuran untuk kemudahan pengambilan
- **Memperhitungkan efek preservasi** pada pengukuran spesimen  
- **Memfasilitasi penelitian** dengan menyediakan urutan data yang konsisten
- **Mempertahankan standar koleksi** di berbagai jenis spesimen

---

*Selamat coding, fellow entomologist! 🐛*
