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
    let hasAdvertisement = false;
    for (let word of page) {
      if (word === "advertisement") {
        hasAdvertisement = true;
        break;
      }
    }
    if (hasAdvertisement) {
      continue; // Lewati halaman ini sepenuhnya
    }
    
    // Cek apakah ada kata yang lebih dari 10 karakter
    let hasLongWord = false;
    for (let word of page) {
      if (word.length > 10) {
        hasLongWord = true;
        break;
      }
    }
    if (hasLongWord) {
      // Balik urutan seluruh halaman dan tambahkan ke hasil
      adjustedSections.push([...page].reverse());
      continue;
    }
    
    // Cek apakah halaman memiliki tepat 5 elemen - balik 3 elemen tengah
    if (page.length === 5) {
      let adjustedPage = [...page];
      // Balik urutan 3 elemen tengah (indeks 1, 2, 3)
      let middle = adjustedPage.slice(1, 4).reverse();
      adjustedPage[1] = middle[0];
      adjustedPage[2] = middle[1];
      adjustedPage[3] = middle[2];
      adjustedSections.push(adjustedPage);
      continue;
    }
    
    // Tidak memenuhi kondisi di atas - biarkan halaman apa adanya
    adjustedSections.push([...page]);
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

## ⚠️ Catatan Penting

- Fungsi ini tidak mengubah array asli (`magazineSections`), melainkan membuat array baru
- Urutan pemeriksaan kondisi sangat penting - kondisi yang dicek lebih dulu akan dijalankan terlebih dahulu
- Halaman yang mengandung "advertisement" akan benar-benar dihilangkan dari hasil akhir
