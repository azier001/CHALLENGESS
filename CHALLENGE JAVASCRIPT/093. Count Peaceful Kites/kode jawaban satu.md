# 🪁 Fungsi `countPeacefulKites`

## 📝 Deskripsi

Fungsi `countPeacefulKites` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung jumlah layang-layang dengan warna damai (peaceful kites) dalam sebuah deskripsi pemandangan. Fungsi ini menggunakan Regular Expression (RegEx) untuk mencari dan menghitung kata kunci tertentu yang mengandung kombinasi warna damai dengan kata "kite".

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `sceneDescription` | `string` | Deskripsi pemandangan yang akan dicari layang-layang berwarna damainya |

## 🎨 Warna Damai yang Dikenali

Fungsi ini mengenali 5 warna damai berikut:

| No | Warna | Bahasa Inggris |
|----|-------|----------------|
| 1 | 🔴 Merah | `red` |
| 2 | 🔵 Biru | `blue` |
| 3 | 🟢 Hijau | `green` |
| 4 | 🟡 Kuning | `yellow` |
| 5 | 🟣 Ungu | `purple` |

## 💻 Kode Fungsi

```javascript
function countPeacefulKites(sceneDescription) {
  // Mengubah teks menjadi huruf kecil untuk pencocokan yang tidak sensitif huruf besar/kecil
  const lowercaseDescription = sceneDescription.toLowerCase();
  
  // Mendefinisikan array warna-warna damai yang akan dicari
  const peacefulColors = ['red', 'blue', 'green', 'yellow', 'purple'];
  
  // Inisialisasi variabel penghitung layang-layang damai
  let peacefulKiteCount = 0;
  
  // Melakukan iterasi untuk setiap warna damai
  for (const color of peacefulColors) {
    // Membuat pola Regular Expression untuk mencari "[warna] kite" secara global
    const regex = new RegExp(`${color} kite`, 'g');
    
    // Mencari semua kemunculan pola dalam teks menggunakan match()
    const matches = lowercaseDescription.match(regex);
    
    // Jika ada kecocokan ditemukan, tambahkan jumlahnya ke penghitung total
    if (matches) {
      peacefulKiteCount += matches.length;
    }
  }
  
  // Mengembalikan total jumlah layang-layang damai yang ditemukan
  return peacefulKiteCount;
}
```

## 🔍 Cara Kerja

1. **Normalisasi Teks**: Fungsi mengubah seluruh teks deskripsi menjadi huruf kecil untuk memastikan pencarian tidak sensitif terhadap huruf besar/kecil
2. **Definisi Warna**: Menyimpan array warna-warna damai yang akan dicari
3. **Inisialisasi Counter**: Membuat variabel penghitung yang dimulai dari 0
4. **Iterasi Warna**: Melakukan perulangan untuk setiap warna dalam array
5. **Pembuatan RegEx**: Membuat pola Regular Expression `[warna] kite` dengan flag global (`g`)
6. **Pencarian Pattern**: Menggunakan metode `match()` untuk mencari semua kemunculan pola
7. **Penghitungan**: Jika ada kecocokan, menambahkan jumlahnya ke counter total
8. **Return Result**: Mengembalikan total jumlah layang-layang damai

## 📊 Contoh Penggunaan dan Output

### Contoh 1: Deskripsi Sederhana
```javascript
const description1 = "I see a red kite flying in the sky with a blue kite nearby.";
const result1 = countPeacefulKites(description1);
console.log(result1); // Output: 2
```

### Contoh 2: Deskripsi dengan Banyak Layang-layang
```javascript
const description2 = "The festival has a red kite, two blue kite, a green kite, and a yellow kite dancing in the wind.";
const result2 = countPeacefulKites(description2);
console.log(result2); // Output: 5
```

### Contoh 3: Deskripsi Tanpa Layang-layang Damai
```javascript
const description3 = "There are black kites and white kites in the stormy sky.";
const result3 = countPeacefulKites(description3);
console.log(result3); // Output: 0
```

### Contoh 4: Deskripsi dengan Huruf Besar/Kecil Campuran
```javascript
const description4 = "RED KITE and Blue Kite are flying with a GREEN kite.";
const result4 = countPeacefulKites(description4);
console.log(result4); // Output: 3
```

### Contoh 5: Deskripsi dengan Kemunculan Berulang
```javascript
const description5 = "A red kite follows another red kite while a purple kite dances above.";
const result5 = countPeacefulKites(description5);
console.log(result5); // Output: 3 (2 red kite + 1 purple kite)
```

## 🛠️ Keunggulan Pendekatan RegEx

- **Pencarian Global**: Flag `g` memastikan semua kemunculan pola ditemukan, bukan hanya yang pertama
- **Akurasi Tinggi**: Metode `match()` memberikan hasil yang lebih akurat dibandingkan `split()`
- **Fleksibilitas**: Regular Expression mudah dimodifikasi untuk pola pencarian yang lebih kompleks
- **Performa**: RegEx umumnya lebih efisien untuk pencarian pola yang kompleks

## ⚠️ Catatan Penting

- Fungsi ini hanya menghitung layang-layang dengan pola tepat `[warna] kite` (dengan spasi di antaranya)
- Pencarian bersifat **case-insensitive** (tidak sensitif huruf besar/kecil)
- Jika ada variasi penulisan seperti `red-kite` atau `redkite`, tidak akan terhitung
- Warna yang tidak termasuk dalam daftar warna damai tidak akan dihitung
- Menggunakan flag global (`g`) untuk mencari semua kemunculan dalam teks

## 🎯 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `number` | Jumlah total layang-layang berwarna damai yang ditemukan dalam deskripsi |

## 🔧 Teknologi yang Digunakan

- **Regular Expression (RegEx)**: Untuk pencarian pola yang efisien
- **String Methods**: `toLowerCase()` untuk normalisasi teks
- **Array Methods**: `match()` untuk mengekstrak semua kecocokan

## 🚀 Pengembangan Lebih Lanjut

Fungsi ini dapat dikembangkan dengan:
- Menambahkan lebih banyak warna damai
- Mendukung variasi penulisan (dengan tanda hubung, tanpa spasi, dll.)
- Menambahkan dukungan untuk bahasa lain
- Mengembalikan detail warna apa saja yang ditemukan
- Menggunakan pola RegEx yang lebih kompleks untuk variasi kata
