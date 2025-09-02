# 🪁 Fungsi `countPeacefulKites`

## 📝 Deskripsi

Fungsi `countPeacefulKites` adalah sebuah fungsi JavaScript yang digunakan untuk menghitung jumlah layang-layang dengan warna damai (peaceful kites) dalam sebuah deskripsi pemandangan. Fungsi ini akan mencari dan menghitung kata kunci tertentu yang mengandung kombinasi warna damai dengan kata "kite".

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
    const lowerDescription = sceneDescription.toLowerCase();
    
    // Mendefinisikan warna-warna damai
    const peacefulColors = ['red', 'blue', 'green', 'yellow', 'purple'];
    
    let totalCount = 0;
    
    // Melakukan iterasi melalui warna-warna damai dan menghitung kemunculannya
    for (const color of peacefulColors) {
        const pattern = `${color} kite`;
        const matches = lowerDescription.split(pattern).length - 1;
        totalCount += matches;
    }
    
    return totalCount;
}
```

## 🔍 Cara Kerja

1. **Normalisasi Teks**: Fungsi mengubah seluruh teks deskripsi menjadi huruf kecil untuk memastikan pencarian tidak sensitif terhadap huruf besar/kecil
2. **Definisi Warna**: Menyimpan array warna-warna damai yang akan dicari
3. **Pencarian Pattern**: Untuk setiap warna, mencari pola `[warna] kite` dalam teks
4. **Penghitungan**: Menggunakan metode `split()` untuk menghitung berapa kali pola tersebut muncul
5. **Akumulasi**: Menjumlahkan semua hasil pencarian dari setiap warna

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

## ⚠️ Catatan Penting

- Fungsi ini hanya menghitung layang-layang dengan pola tepat `[warna] kite` (dengan spasi di antaranya)
- Pencarian bersifat **case-insensitive** (tidak sensitif huruf besar/kecil)
- Jika ada variasi penulisan seperti `red-kite` atau `redkite`, tidak akan terhitung
- Warna yang tidak termasuk dalam daftar warna damai tidak akan dihitung

## 🎯 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `number` | Jumlah total layang-layang berwarna damai yang ditemukan dalam deskripsi |

## 🚀 Pengembangan Lebih Lanjut

Fungsi ini dapat dikembangkan dengan:
- Menambahkan lebih banyak warna damai
- Mendukung variasi penulisan (dengan tanda hubung, tanpa spasi, dll.)
- Menambahkan dukungan untuk bahasa lain
- Mengembalikan detail warna apa saja yang ditemukan
