# 🐛 Dokumentasi Fungsi `toyInsectParade`

## 📝 Deskripsi

Fungsi `toyInsectParade` adalah sebuah fungsi JavaScript yang membuat parade serangga mainan. Fungsi ini akan mengatur serangga-serangga dalam barisan dengan mengulangi setiap jenis serangga sesuai jumlah yang ditentukan, kemudian menampilkannya dalam format parade yang dimulai dengan "Start" dan diakhiri dengan "Finish".

## ⚙️ Sintaks

```javascript
toyInsectParade(insects, repeatCount)
```

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `insects` | Array | Array berisi nama-nama serangga yang akan diikutsertakan dalam parade |
| `repeatCount` | Number | Jumlah pengulangan untuk setiap serangga dalam parade |

### Detail Parameter:
- **`insects`**: Array string yang berisi jenis-jenis serangga (contoh: ["🐛", "🦋", "🐝"])
- **`repeatCount`**: Bilangan bulat positif yang menentukan berapa kali setiap serangga akan muncul berturut-turut

## 📤 Nilai Kembalian

| Kondisi | Tipe Return | Nilai |
|---------|-------------|-------|
| Parade normal | String | String yang berisi urutan parade dengan format "Start -> [serangga] -> ... -> Finish" |
| Array kosong atau repeatCount ≤ 0 | String | "No parade today!" |

## 💻 Kode Fungsi

```javascript
function toyInsectParade(insects, repeatCount) {
  // Cek apakah array serangga kosong atau jumlah pengulangan tidak valid
  if (insects.length === 0 || repeatCount <= 0) {
    return "No parade today!";
  }
  
  // Inisialisasi string parade dengan "Start"
  let parade = "Start";
  
  // Loop melalui setiap serangga dalam array
  for (let insect of insects) {
    // Ulangi serangga sesuai jumlah repeatCount
    for (let i = 0; i < repeatCount; i++) {
      parade += ` -> ${insect}`;
    }
  }
  
  // Tambahkan "Finish" di akhir parade
  parade += " -> Finish";
  
  // Kembalikan string parade yang sudah lengkap
  return parade;
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Parade Normal
```javascript
const serangga = ["🐛", "🦋", "🐝"];
const result = toyInsectParade(serangga, 2);
console.log(result);
```

**Output:**
```
Start -> 🐛 -> 🐛 -> 🦋 -> 🦋 -> 🐝 -> 🐝 -> Finish
```

### Contoh 2: Parade dengan Satu Serangga
```javascript
const serangga = ["🦗"];
const result = toyInsectParade(serangga, 3);
console.log(result);
```

**Output:**
```
Start -> 🦗 -> 🦗 -> 🦗 -> Finish
```

### Contoh 3: Array Kosong
```javascript
const serangga = [];
const result = toyInsectParade(serangga, 2);
console.log(result);
```

**Output:**
```
No parade today!
```

### Contoh 4: Repeat Count Nol atau Negatif
```javascript
const serangga = ["🐛", "🦋"];
const result = toyInsectParade(serangga, 0);
console.log(result);
```

**Output:**
```
No parade today!
```

### Contoh 5: Parade dengan Nama Serangga
```javascript
const serangga = ["kupu-kupu", "lebah", "belalang"];
const result = toyInsectParade(serangga, 1);
console.log(result);
```

**Output:**
```
Start -> kupu-kupu -> lebah -> belalang -> Finish
```

## 🔄 Cara Kerja

1. **Validasi Input**: Fungsi pertama-tama memeriksa apakah array `insects` kosong atau `repeatCount` kurang dari atau sama dengan 0
2. **Inisialisasi Parade**: Jika input valid, membuat string `parade` yang dimulai dengan "Start"
3. **Iterasi Serangga**: Menggunakan loop `for...of` untuk iterasi setiap serangga dalam array input
4. **Pengulangan**: Untuk setiap serangga, menggunakan loop `for` untuk menambahkan serangga tersebut sebanyak `repeatCount` kali dengan format ` -> ${insect}`
5. **Finalisasi**: Menambahkan " -> Finish" di akhir string parade menggunakan operator `+=`
6. **Pengembalian**: Mengembalikan string parade yang sudah lengkap

## 📊 Kompleksitas

- **Time Complexity**: O(n × m × k) dimana n adalah jumlah serangga, m adalah repeatCount, dan k adalah rata-rata panjang nama serangga (untuk operasi string concatenation)
- **Space Complexity**: O(n × m × k) untuk menyimpan hasil string parade final

## ⚠️ Catatan Penting

- Fungsi ini menggunakan **string concatenation** dengan operator `+=` untuk membangun parade
- Setiap penambahan serangga menggunakan **template literal** dengan format ` -> ${insect}`
- Fungsi akan mengembalikan "No parade today!" jika array serangga kosong atau repeatCount ≤ 0
- Serangga akan muncul berurutan sesuai urutan dalam array input
- Setiap jenis serangga akan diulang secara berturut-turut sebelum beralih ke serangga berikutnya
- Output berupa string tunggal dengan format yang mudah dibaca dan konsisten

## 🔧 Perbedaan dengan Versi Array

Versi ini menggunakan **string concatenation** langsung dibandingkan dengan pendekatan array + `join()`. Keuntungan:
- ✅ Lebih sederhana dan direct
- ✅ Tidak perlu method `join()` di akhir
- ❌ Potentially less efficient untuk data yang sangat besar (string concatenation bisa lebih lambat)

## 🚀 Tips Penggunaan

- Cocok untuk parade dengan ukuran kecil hingga menengah
- Gunakan nama serangga yang pendek untuk hasil yang lebih rapi
- Bisa menggunakan emoji serangga untuk tampilan yang lebih menarik
- RepeatCount yang terlalu besar akan menghasilkan string yang sangat panjang
