# 🍒 Cherry Bookmarker

## 📝 Deskripsi Fungsi

Fungsi `cherryBookmarker` digunakan untuk menandai (bookmark) spesies cherry tertentu dalam sebuah array. Fungsi ini akan menelusuri array spesies cherry dan menambahkan label "(Bookmarked)" pada spesies yang cocok dengan bookmark yang dicari, kemudian berhenti memproses sisa array.

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `cherrySpecies` | Array | Array yang berisi daftar spesies cherry |
| `bookmarkSpecies` | String/Any | Spesies cherry yang ingin ditandai (di-bookmark) |

---

## 🔄 Return Value

**Tipe:** `Array`

Mengembalikan array baru yang berisi:
- Semua elemen sebelum bookmark
- Elemen yang di-bookmark dengan tambahan label " (Bookmarked)"
- Elemen setelah bookmark **tidak dimasukkan**

---

## 💻 Kode Fungsi

```javascript
function cherryBookmarker(cherrySpecies, bookmarkSpecies) {
  // Inisialisasi array kosong untuk menampung hasil
  const result = [];
  
  // Loop melalui setiap spesies cherry dalam array menggunakan for...of
  for (let species of cherrySpecies) {
    
    // Cek apakah spesies saat ini sama dengan spesies yang ingin di-bookmark
    if (species === bookmarkSpecies) {
      // Tambahkan spesies dengan label "(Bookmarked)"
      result.push(species + " (Bookmarked)");
      
      // Hentikan loop setelah menemukan bookmark
      break;
      
    } else {
      // Jika belum ketemu bookmark, tambahkan spesies seperti biasa
      result.push(species);
    }
  }
  
  // Kembalikan array hasil
  return result;
}
```

---

## 📊 Contoh Penggunaan

### Contoh 1: Bookmark di Tengah Array

```javascript
const species = ["Bing", "Rainier", "Montmorency", "Lambert", "Chelan"];
const result = cherryBookmarker(species, "Montmorency");

console.log(result);
// Output: ["Bing", "Rainier", "Montmorency (Bookmarked)"]
```

**Penjelasan:** Fungsi menemukan "Montmorency" di posisi ke-3, menambahkan label "(Bookmarked)", dan berhenti. Elemen setelahnya ("Lambert" dan "Chelan") tidak dimasukkan.

---

### Contoh 2: Bookmark di Awal Array

```javascript
const species = ["Bing", "Rainier", "Montmorency", "Lambert"];
const result = cherryBookmarker(species, "Bing");

console.log(result);
// Output: ["Bing (Bookmarked)"]
```

**Penjelasan:** Karena "Bing" ada di posisi pertama, fungsi langsung menambahkan label dan berhenti.

---

### Contoh 3: Bookmark Tidak Ditemukan

```javascript
const species = ["Bing", "Rainier", "Montmorency"];
const result = cherryBookmarker(species, "Sweetheart");

console.log(result);
// Output: ["Bing", "Rainier", "Montmorency"]
```

**Penjelasan:** Karena "Sweetheart" tidak ditemukan, semua elemen dikembalikan tanpa label bookmark.

---

## ⚠️ Catatan Penting

1. **Fungsi Berhenti Setelah Menemukan Match**: Setelah menemukan spesies yang cocok, fungsi akan berhenti dan tidak memproses elemen sisanya.

2. **Perbandingan Strict**: Fungsi menggunakan operator `===` untuk perbandingan, jadi tipe data harus sama persis.

3. **Case Sensitive**: Perbandingan string bersifat case-sensitive. "Bing" tidak sama dengan "bing".

4. **Hanya Match Pertama**: Jika ada duplikat dalam array, hanya kemunculan pertama yang akan di-bookmark.

5. **Menggunakan for...of Loop**: Kode ini menggunakan `for...of` loop yang lebih modern dan mudah dibaca dibanding loop tradisional dengan index.

---

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- Menandai item favorit dalam daftar
- Membuat sistem highlight pada data
- Memfilter data sampai titik tertentu
- Menampilkan data partial dengan penanda khusus

---

## 📚 Tabel Perbandingan Output

| Input Array | Bookmark | Output Array | Jumlah Elemen |
|-------------|----------|--------------|---------------|
| `["A", "B", "C", "D"]` | `"B"` | `["A", "B (Bookmarked)"]` | 2 |
| `["A", "B", "C", "D"]` | `"D"` | `["A", "B", "C", "D (Bookmarked)"]` | 4 |
| `["A", "B", "C", "D"]` | `"A"` | `["A (Bookmarked)"]` | 1 |
| `["A", "B", "C", "D"]` | `"Z"` | `["A", "B", "C", "D"]` | 4 |

---

## 🔧 Kemungkinan Modifikasi

Jika Anda ingin fungsi tetap memasukkan semua elemen, Anda bisa menghapus statement `break`:

```javascript
function cherryBookmarkerAll(cherrySpecies, bookmarkSpecies) {
  const result = [];
  
  for (let species of cherrySpecies) {
    if (species === bookmarkSpecies) {
      result.push(species + " (Bookmarked)");
    } else {
      result.push(species);
    }
  }
  
  return result;
}
```

---

## 🆚 Perbedaan dengan Versi Lain

Kode ini menggunakan **for...of loop** yang memiliki kelebihan:
- ✅ Sintaks lebih sederhana dan mudah dibaca
- ✅ Tidak perlu mengakses index secara manual
- ✅ Langsung mendapat nilai elemen, bukan index
- ✅ Lebih modern dan idiomatik dalam JavaScript

Bandingkan dengan versi tradisional menggunakan for loop dengan index:
```javascript
// Versi tradisional
for (let i = 0; i < cherrySpecies.length; i++) {
  if (cherrySpecies[i] === bookmarkSpecies) {
    // ...
  }
}

// Versi for...of (lebih simpel)
for (let species of cherrySpecies) {
  if (species === bookmarkSpecies) {
    // ...
  }
}
```

---

**Dibuat dengan ❤️ untuk dokumentasi yang lebih baik**
