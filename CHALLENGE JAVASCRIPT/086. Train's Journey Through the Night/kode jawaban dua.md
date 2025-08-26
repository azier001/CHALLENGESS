# 🚂 Dokumentasi Fungsi trainJourney

## 📝 Deskripsi

Fungsi `trainJourney` adalah fungsi JavaScript yang mengubah sebuah string dengan cara yang unik dan menyenangkan! Fungsi ini melakukan tiga langkah transformasi:

1. **Membalik urutan kata-kata** dalam string
2. **Mengkapitalisasi setiap karakter ke-3** (dimulai dari indeks 0)
3. **Menambahkan " choo choo!"** di akhir string

Fungsi ini cocok digunakan untuk membuat efek teks yang lucu atau sebagai latihan manipulasi string.

## 🔧 Parameter

| Parameter | Tipe   | Wajib | Deskripsi |
|-----------|--------|-------|-----------|
| `string`  | String | Ya    | Teks yang akan diproses dan ditransformasi |

## 💻 Kode Fungsi

```javascript
function trainJourney(string) {
    // Langkah 1: Membalik urutan kata-kata dalam string
    const reversedWords = string.split(' ').reverse().join(' ');
    
    // Langkah 2: Mengkapitalisasi setiap karakter ke-3 
    // (dimulai dari indeks 0, jadi posisi 0, 3, 6, 9, ...)
    let result = '';
    
    for (let i = 0; i < reversedWords.length; i++) {
        if (i % 3 === 0) {
            // Jika indeks habis dibagi 3, ubah menjadi huruf kapital
            result += reversedWords[i].toUpperCase();
        } else {
            // Jika tidak, tetap gunakan karakter asli
            result += reversedWords[i];
        }
    }
    
    // Langkah 3: Menambahkan " choo choo!" di akhir hasil
    return result + " choo choo!";
}
```

## 🎯 Cara Kerja Detail

### Langkah 1: Membalik Urutan Kata
- String dipecah menjadi array kata-kata menggunakan `split(' ')`
- Array dibalik menggunakan `reverse()`
- Array digabung kembali menjadi string menggunakan `join(' ')`

### Langkah 2: Kapitalisasi Setiap Karakter ke-3
- Fungsi melakukan loop melalui setiap karakter
- Karakter pada posisi 0, 3, 6, 9, dst. diubah menjadi huruf kapital
- Karakter lainnya tetap tidak berubah

### Langkah 3: Menambahkan Suara Kereta
- String " choo choo!" ditambahkan di akhir hasil

## 📊 Tabel Contoh Kapitalisasi

| Indeks | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|--------|---|---|---|---|---|---|---|---|---|---|
| Aksi   | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ |

*✅ = Dikapitalisasi, ❌ = Tetap sama*

## 🚀 Contoh Penggunaan

```javascript
// Contoh 1: Kalimat sederhana
console.log(trainJourney("hello world"));
// Output: "WOrld HeLlo choo choo!"

// Contoh 2: Kalimat lebih panjang
console.log(trainJourney("i love programming"));
// Output: "ProGramMing Love I choo choo!"

// Contoh 3: Satu kata
console.log(trainJourney("javascript"));
// Output: "JavAscRipt choo choo!"
```

## 📈 Contoh Output Detail

### Input: `"hello world"`

1. **Setelah langkah 1** (balik kata): `"world hello"`
2. **Setelah langkah 2** (kapitalisasi): `"WOrld HeLlo"`
   - Posisi 0: `w` → `W`
   - Posisi 3: `l` → `L`  
   - Posisi 6: `h` → `H`
   - Posisi 9: `l` → `L`
3. **Setelah langkah 3** (tambah suara): `"WOrld HeLlo choo choo!"`

### Input: `"belajar coding"`

1. **Setelah langkah 1**: `"coding belajar"`
2. **Setelah langkah 2**: `"CodIng BeLajar"`
3. **Setelah langkah 3**: `"CodIng BeLajar choo choo!"`

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** - huruf kapital dan kecil diperlakukan berbeda
- Spasi dihitung sebagai karakter dalam proses kapitalisasi
- Jika input kosong, output akan menjadi `" choo choo!"`
- Fungsi tidak melakukan validasi input, pastikan parameter berupa string

## 🎨 Kustomisasi

Anda bisa memodifikasi fungsi ini dengan:
- Mengganti `" choo choo!"` dengan suara lain
- Mengubah pola kapitalisasi (misalnya setiap 2 atau 4 karakter)
- Menambahkan validasi input untuk memastikan parameter berupa string

---

*Selamat bermain dengan fungsi trainJourney! 🚂💨*
