# 📚 Dokumentasi Fungsi `groupAnagramTitles`

## 📖 Deskripsi

Fungsi `groupAnagramTitles` adalah fungsi yang digunakan untuk mengelompokkan judul-judul buku yang merupakan anagram satu sama lain. 

**Apa itu Anagram?** 
Anagram adalah kata atau frasa yang dibentuk dengan menyusun ulang huruf-huruf dari kata atau frasa lain. Contohnya: "listen" dan "silent" adalah anagram karena menggunakan huruf yang sama.

Fungsi ini akan menganalisis setiap judul buku dan mengelompokkannya berdasarkan huruf-huruf yang digunakan (mengabaikan spasi dan perbedaan huruf besar/kecil).

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `bookTitles` | Array of Strings | Array yang berisi daftar judul-judul buku yang akan dikelompokkan |

---

## 📤 Return Value

Fungsi ini mengembalikan **Array of Arrays** (array 2 dimensi), di mana:
- Setiap sub-array berisi judul-judul buku yang merupakan anagram satu sama lain
- Judul-judul yang tidak memiliki anagram akan berada di sub-array tersendiri

---

## 💻 Kode Fungsi

```javascript
function groupAnagramTitles(bookTitles) {
    // Membuat Map untuk menyimpan grup anagram
    const groups = new Map();
    
    for (const title of bookTitles) {
        // Membuat signature dengan mengurutkan huruf-huruf
        // (mengabaikan huruf besar/kecil dan spasi)
        const signature = title
            .toLowerCase()              // Ubah ke huruf kecil
            .replace(/\s/g, '')         // Hapus semua spasi
            .split('')                  // Pisahkan menjadi array karakter
            .sort()                     // Urutkan karakter secara alfabetis
            .join('');                  // Gabungkan kembali menjadi string
        
        // Jika signature belum ada di Map, buat array baru
        if (!groups.has(signature)) {
            groups.set(signature, []);
        }
        
        // Tambahkan judul ke grup yang sesuai
        groups.get(signature).push(title);
    }
    
    // Kembalikan semua grup sebagai array
    return Array.from(groups.values());
}
```

---

## 🎯 Cara Kerja

1. **Inisialisasi Map**: Membuat struktur data Map untuk menyimpan grup-grup anagram
2. **Iterasi Judul**: Memproses setiap judul buku satu per satu
3. **Buat Signature**: Untuk setiap judul, buat "signature" unik dengan:
   - Mengubah semua huruf ke huruf kecil
   - Menghapus semua spasi
   - Mengurutkan huruf-huruf secara alfabetis
4. **Kelompokkan**: Judul-judul dengan signature yang sama dikelompokkan bersama
5. **Return Hasil**: Mengembalikan array berisi semua grup anagram

---

## 📝 Contoh Penggunaan

### Input:
```javascript
const bookTitles = [
    "The Eyes",
    "They See",
    "Listen",
    "Silent",
    "A Gentleman",
    "Elegant Man"
];

const result = groupAnagramTitles(bookTitles);
console.log(result);
```

### Output:
```javascript
[
    ["The Eyes", "They See"],
    ["Listen", "Silent"],
    ["A Gentleman", "Elegant Man"]
]
```

### 📊 Tabel Penjelasan Hasil

| Grup | Judul-judul | Signature | Penjelasan |
|------|-------------|-----------|------------|
| 1 | "The Eyes", "They See" | `eeeehsty` | Kedua judul menggunakan huruf yang sama |
| 2 | "Listen", "Silent" | `eilnst` | Anagram klasik - huruf yang sama, urutan berbeda |
| 3 | "A Gentleman", "Elegant Man" | `aaeegelmnnnt` | Termasuk spasi, tapi signature mengabaikan spasi |

---

## 🌟 Contoh Tambahan

### Contoh 1: Judul Tanpa Anagram
```javascript
const titles = ["Book One", "Book Two", "Book Three"];
const result = groupAnagramTitles(titles);
console.log(result);

// Output:
// [
//     ["Book One"],
//     ["Book Two"],
//     ["Book Three"]
// ]
```

### Contoh 2: Banyak Anagram dalam Satu Grup
```javascript
const titles = ["tea", "eat", "ate", "bat", "tab"];
const result = groupAnagramTitles(titles);
console.log(result);

// Output:
// [
//     ["tea", "eat", "ate"],
//     ["bat", "tab"]
// ]
```

---

## ⚡ Kompleksitas

- **Time Complexity**: O(n × m log m)
  - n = jumlah judul buku
  - m = panjang rata-rata judul (untuk sorting)
  
- **Space Complexity**: O(n × m)
  - Menyimpan semua judul dan signature-nya

---

## 💡 Tips Penggunaan

- Fungsi ini **case-insensitive**, jadi "ABC" dan "abc" dianggap sama
- **Spasi diabaikan**, sehingga "the eyes" dan "theeyes" dianggap identik
- Cocok untuk menganalisis judul buku, kata-kata puzzle, atau permainan kata
- Gunakan untuk mendeteksi duplikasi judul dengan penyusunan huruf yang berbeda

---

## ⚠️ Catatan Penting

- Fungsi ini hanya memperhitungkan huruf alphabet
- Karakter spesial dan angka tetap diperhitungkan dalam signature
- Urutan grup dalam hasil akhir bergantung pada urutan kemunculan pertama di input
