# 📰 adjustPrintingPlates

## 📝 Deskripsi Fungsi

Fungsi `adjustPrintingPlates` adalah fungsi yang digunakan untuk menyesuaikan halaman-halaman majalah berdasarkan aturan tertentu. Fungsi ini akan memproses setiap halaman majalah dan menerapkan penyesuaian yang berbeda tergantung pada kondisi konten yang ada di halaman tersebut.

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `magazineSections` | Array of Arrays | Array yang berisi halaman-halaman majalah, dimana setiap halaman adalah array berisi kata-kata (string) |

## ⚙️ Aturan Pemrosesan

Fungsi ini menerapkan aturan berikut secara berurutan:

| No | Kondisi | Aksi |
|----|---------|------|
| 1️⃣ | Halaman mengandung kata "advertisement" | 🚫 **Lewati halaman** (tidak dimasukkan ke hasil) |
| 2️⃣ | Ada kata yang lebih dari 10 karakter | 🔄 **Balik urutan seluruh halaman** |
| 3️⃣ | Halaman memiliki tepat 5 elemen | 🔄 **Balik urutan 3 elemen tengah** (indeks 1, 2, 3) |
| 4️⃣ | Tidak memenuhi kondisi di atas | ✅ **Biarkan halaman apa adanya** |

## 📤 Output

Fungsi mengembalikan array baru yang berisi halaman-halaman yang telah disesuaikan sesuai dengan aturan di atas.

## 💻 Kode Fungsi

```javascript
function adjustPrintingPlates(magazineSections) {
  let adjustedSections = [];
  
  // Iterasi setiap halaman dalam majalah
  for (let page of magazineSections) {
    
    // Cek apakah halaman mengandung "advertisement" - lewati jika ditemukan
    if (page.includes("advertisement")) {
      continue; // Lewati halaman ini sepenuhnya
    }
    
    // Cek apakah ada kata yang lebih dari 10 karakter menggunakan method some()
    if (page.some(word => word.length > 10)) {
      adjustedSections.push(page.reverse()); // Balik urutan seluruh halaman
      continue;
    }
    
    // Cek apakah halaman memiliki tepat 5 elemen - balik 3 elemen tengah
    if (page.length === 5) {
      // Ambil 3 elemen tengah (indeks 1, 2, 3) dan balik urutannya
      let middleThree = page.slice(1, 4).reverse();
      // Gabungkan elemen pertama + 3 elemen tengah yang sudah dibalik + elemen terakhir
      adjustedSections.push([page[0], ...middleThree, page[4]]);
      continue;
    }
    
    // Tidak memenuhi kondisi di atas - biarkan halaman apa adanya
    adjustedSections.push(page);
  }
  
  return adjustedSections;
}
```

## 🔍 Contoh Penggunaan

### Input:
```javascript
const magazineSections = [
  ["artikel", "berita", "advertisement", "foto"],     // Halaman 1
  ["judul", "konten", "gambar"],                      // Halaman 2  
  ["kata", "kalimatpanjangbanget", "teks"],           // Halaman 3
  ["satu", "dua", "tiga", "empat", "lima"],          // Halaman 4
  ["pendek", "kata", "lagi"]                          // Halaman 5
];

const hasil = adjustPrintingPlates(magazineSections);
console.log(hasil);
```

### Output:
```javascript
[
  // Halaman 1: DILEWATI karena mengandung "advertisement"
  
  ["judul", "konten", "gambar"],                      // Halaman 2: tidak ada perubahan
  
  ["teks", "kalimatpanjangbanget", "kata"],           // Halaman 3: dibalik karena ada kata > 10 karakter
  
  ["satu", "empat", "tiga", "dua", "lima"],          // Halaman 4: 3 elemen tengah dibalik
  
  ["pendek", "kata", "lagi"]                          // Halaman 5: tidak ada perubahan
]
```

## 📋 Penjelasan Contoh

1. **Halaman 1** `["artikel", "berita", "advertisement", "foto"]`
   - ❌ Dilewati karena mengandung kata "advertisement"

2. **Halaman 2** `["judul", "konten", "gambar"]`
   - ✅ Tidak memenuhi kondisi khusus, dibiarkan apa adanya

3. **Halaman 3** `["kata", "kalimatpanjangbanget", "teks"]`
   - 🔄 Dibalik seluruhnya karena "kalimatpanjangbanget" lebih dari 10 karakter
   - Hasil: `["teks", "kalimatpanjangbanget", "kata"]`

4. **Halaman 4** `["satu", "dua", "tiga", "empat", "lima"]`
   - 🔄 Memiliki tepat 5 elemen, sehingga 3 elemen tengah (indeks 1,2,3) dibalik
   - Elemen tengah: `["dua", "tiga", "empat"]` → `["empat", "tiga", "dua"]`
   - Hasil: `["satu", "empat", "tiga", "dua", "lima"]`

5. **Halaman 5** `["pendek", "kata", "lagi"]`
   - ✅ Tidak memenuhi kondisi khusus, dibiarkan apa adanya

## 🛠️ Method JavaScript yang Digunakan

| Method | Fungsi | Contoh |
|--------|--------|---------|
| `includes()` | Mengecek apakah array mengandung elemen tertentu | `page.includes("advertisement")` |
| `some()` | Mengecek apakah ada elemen yang memenuhi kondisi | `page.some(word => word.length > 10)` |
| `reverse()` | Membalik urutan elemen dalam array | `page.reverse()` |
| `slice()` | Mengambil sebagian elemen array | `page.slice(1, 4)` |
| `spread operator (...)` | Menyebarkan elemen array | `[page[0], ...middleThree, page[4]]` |

## ⚠️ Catatan Penting

- **Perubahan Array Original**: Method `reverse()` mengubah array asli. Dalam kode ini, hal ini tidak masalah karena kita tetap mendapat hasil yang diinginkan
- **Efisiensi Kode**: Versi ini lebih ringkas menggunakan method built-in JavaScript seperti `includes()` dan `some()`
- **Urutan Pemeriksaan**: Kondisi dicek secara berurutan dari atas ke bawah, kondisi yang terpenuhi pertama kali akan dijalankan
- **Spread Operator**: Digunakan untuk menggabungkan array dengan cara yang lebih elegan

## 🔄 Perbandingan dengan Versi Loop Manual

Versi ini lebih modern dan ringkas dibandingkan menggunakan loop manual:
- `page.includes("advertisement")` lebih simple dari loop untuk mencari kata
- `page.some(word => word.length > 10)` lebih readable dari loop manual
- Menggunakan spread operator untuk penggabungan array yang lebih clean
