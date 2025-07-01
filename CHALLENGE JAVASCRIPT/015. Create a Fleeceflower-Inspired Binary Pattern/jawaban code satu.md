# 🌸 Dokumentasi Fungsi createFleeceflowerPattern (Versi Lengkap dengan Error Handling)

## 📌 Deskripsi

Fungsi `createFleeceflowerPattern` membuat pola bunga fleece berbentuk simetris berbasis angka biner (1 dan 0) yang disusun secara zig-zag. Fungsi ini menampilkan pola dalam bentuk teks multiline dan hanya menerima input bilangan ganjil ≥ 3. Jika input tidak valid, fungsi akan menghasilkan error.

---

## 🔧 Deklarasi Fungsi

```javascript
function createFleeceflowerPattern(size)
```

---

## 🧩 Kode Lengkap

```javascript
function createFleeceflowerPattern(size) {
    // Validate input
    if (size < 3 || size % 2 === 0) {
        throw new Error("Size must be an odd integer of at least 3");
    }
    
    let pattern = "";
    const center = Math.floor(size / 2);
    
    for (let i = 0; i < size; i++) {
        let row = "";
        
        // Calculate distance from center row
        const distanceFromCenter = Math.abs(i - center);
        
        // Calculate number of elements in this row
        const elementsInRow = size - 2 * distanceFromCenter;
        
        // Calculate leading spaces
        const leadingSpaces = distanceFromCenter;
        
        // Add leading spaces
        row += " ".repeat(leadingSpaces);
        
        // Add the binary pattern for this row
        for (let j = 0; j < elementsInRow; j++) {
            // Alternate between 1 and 0
            if (j % 2 === 0) {
                row += "1";
            } else {
                row += "0";
            }
        }
        
        // Add trailing spaces to match the width
        row += " ".repeat(leadingSpaces);
        
        // Add row to pattern
        pattern += row;
        
        // Add newline except for the last row
        if (i < size - 1) {
            pattern += "\n";
        }
    }
    
    return pattern;
}
```

---

## 🧾 Parameter

| Parameter | Tipe   | Deskripsi                               |
| --------- | ------ | --------------------------------------- |
| size      | Number | Ukuran pola (harus bilangan ganjil ≥ 3) |

---

## ⚠️ Validasi & Error Handling

Jika `size` kurang dari 3 atau merupakan bilangan genap, fungsi akan menghasilkan error.

### Contoh:

```javascript
createFleeceflowerPattern(4);
```

🛑 Akan menghasilkan:

```
Error: Size must be an odd integer of at least 3
```

---

## 🔄 Cara Kerja

1. Validasi input.
2. Hitung jarak setiap baris dari tengah.
3. Hitung jumlah angka `1` dan `0` yang akan ditampilkan berdasarkan jarak tersebut.
4. Tambahkan spasi di depan dan belakang untuk membentuk simetri.
5. Gabungkan semua baris menjadi satu string pola multiline.

---

## 📤 Nilai Kembali

* **Tipe:** `String`
* **Deskripsi:** String pola bunga fleece yang terdiri dari angka `1` dan `0` berbentuk simetris.

---

## 💡 Contoh Penggunaan

```javascript
console.log(createFleeceflowerPattern(5));
```

### ✅ Output

```
  1  
 101
10101
 101
  1  
```

---

## 🧪 Contoh Tambahan

```javascript
console.log(createFleeceflowerPattern(7));
```

### Output:

```
   1   
  101  
 10101
1010101
 10101
  101  
   1   
```

---

## 📎 Catatan

* Fungsi ini membantu memahami konsep simetri dan manipulasi string dalam JavaScript.
* Dapat dikembangkan lebih lanjut dengan karakter berbeda atau pola warna.

---

Selamat berkreasi dengan pola! 🎨
