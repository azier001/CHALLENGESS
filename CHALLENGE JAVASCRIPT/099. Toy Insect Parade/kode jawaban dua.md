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
    
    // Inisialisasi array parade dengan elemen "Start"
    let parade = ["Start"];
    
    // Loop melalui setiap serangga dalam array
    for (let insect of insects) {
        // Ulangi serangga sesuai jumlah repeatCount
        for (let i = 0; i < repeatCount; i++) {
            parade.push(insect);
        }
    }
    
    // Tambahkan "Finish" di akhir parade
    parade.push("Finish");
    
    // Gabungkan semua elemen array menjadi string dengan pemisah " -> "
    return parade.join(" -> ");
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

## 🔄 Cara Kerja

1. **Validasi Input**: Fungsi pertama-tama memeriksa apakah array `insects` kosong atau `repeatCount` kurang dari atau sama dengan 0
2. **Inisialisasi Parade**: Jika input valid, membuat array `parade` yang dimulai dengan string "Start"
3. **Iterasi Serangga**: Menggunakan loop `for...of` untuk iterasi setiap serangga dalam array input
4. **Pengulangan**: Untuk setiap serangga, menggunakan loop `for` untuk menambahkan serangga tersebut sebanyak `repeatCount` kali
5. **Finalisasi**: Menambahkan "Finish" di akhir array parade
6. **Pengembalian**: Menggabungkan semua elemen array dengan pemisah " -> " menggunakan method `join()`

## 📊 Kompleksitas

- **Time Complexity**: O(n × m) dimana n adalah jumlah serangga dan m adalah repeatCount
- **Space Complexity**: O(n × m) untuk menyimpan hasil parade

## ⚠️ Catatan Penting

- Fungsi ini akan mengembalikan "No parade today!" jika array serangga kosong atau repeatCount ≤ 0
- Serangga akan muncul berurutan sesuai urutan dalam array input
- Setiap jenis serangga akan diulang secara berturut-turut sebelum beralih ke serangga berikutnya
- Output berupa string dengan format yang mudah dibaca dan konsisten
