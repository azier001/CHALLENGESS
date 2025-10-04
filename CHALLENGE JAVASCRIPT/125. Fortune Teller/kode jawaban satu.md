# 🔮 Fortune Teller Function

## 📋 Deskripsi

Fungsi `fortuneTeller` adalah sebuah fungsi yang memprediksi "keberuntungan" berdasarkan perhitungan matematis dari array angka. Fungsi ini bekerja dengan cara:
- Menambahkan angka **genap** ke total sum
- Mengurangi angka **ganjil** dari total sum
- Membandingkan hasil akhir dengan target yang ditentukan

Jika hasil perhitungan sama dengan target, maka Anda **"Lucky!"** (beruntung), jika tidak maka **"Unlucky!"** (tidak beruntung).

---

## 📝 Sintaks

```javascript
fortuneTeller(numbers, target)
```

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `numbers` | Array | Array berisi angka-angka yang akan dihitung. Bisa berisi angka genap atau ganjil |
| `target` | Number | Angka target yang ingin dicapai dari hasil perhitungan |

---

## 📤 Return Value

| Tipe | Nilai | Kondisi |
|------|-------|---------|
| String | `"Lucky!"` | Jika hasil perhitungan sama dengan target |
| String | `"Unlucky!"` | Jika hasil perhitungan tidak sama dengan target |

---

## 🎯 Cara Kerja

1. **Inisialisasi**: Variabel `sum` dimulai dari 0
2. **Looping**: Fungsi melakukan perulangan untuk setiap angka dalam array
3. **Pengecekan**:
   - Jika angka **genap** (habis dibagi 2): **tambahkan** ke sum
   - Jika angka **ganjil** (tidak habis dibagi 2): **kurangi** dari sum
4. **Perbandingan**: Hasil akhir dibandingkan dengan target menggunakan if-else
5. **Output**: Return "Lucky!" atau "Unlucky!"

---

## 💻 Kode Lengkap

```javascript
function fortuneTeller(numbers, target) {
  // Inisialisasi variabel sum dengan nilai 0
  let sum = 0;
  
  // Looping setiap angka dalam array numbers
  for (let i = 0; i < numbers.length; i++) {
    
    // Cek apakah angka genap atau ganjil
    if (numbers[i] % 2 === 0) {
      // Jika genap, tambahkan ke sum
      sum += numbers[i];
      
    } else {
      // Jika ganjil, kurangi dari sum
      sum -= numbers[i];
    }
  }
  
  // Bandingkan hasil sum dengan target
  if (sum === target) {
    // Jika sama, return "Lucky!"
    return "Lucky!";
    
  } else {
    // Jika tidak sama, return "Unlucky!"
    return "Unlucky!";
  }
}
```

---

## 📊 Contoh Penggunaan

### Contoh 1: Lucky (Beruntung)
```javascript
let angka = [10, 5, 3];
let target = 2;

console.log(fortuneTeller(angka, target));
// Output: "Lucky!"
```

**Penjelasan:**
- 10 (genap) → sum = 0 + 10 = 10
- 5 (ganjil) → sum = 10 - 5 = 5
- 3 (ganjil) → sum = 5 - 3 = 2
- Hasil: 2 = 2 → **"Lucky!"** ✨

### Contoh 2: Unlucky (Tidak Beruntung)
```javascript
let angka = [1, 2, 3, 4];
let target = 10;

console.log(fortuneTeller(angka, target));
// Output: "Unlucky!"
```

**Penjelasan:**
- 1 (ganjil) → sum = 0 - 1 = -1
- 2 (genap) → sum = -1 + 2 = 1
- 3 (ganjil) → sum = 1 - 3 = -2
- 4 (genap) → sum = -2 + 4 = 2
- Hasil: 2 ≠ 10 → **"Unlucky!"** 😢

### Contoh 3: Lucky dengan Angka Besar
```javascript
let angka = [20, 15, 8, 7];
let target = 6;

console.log(fortuneTeller(angka, target));
// Output: "Lucky!"
```

**Penjelasan:**
- 20 (genap) → sum = 0 + 20 = 20
- 15 (ganjil) → sum = 20 - 15 = 5
- 8 (genap) → sum = 5 + 8 = 13
- 7 (ganjil) → sum = 13 - 7 = 6
- Hasil: 6 = 6 → **"Lucky!"** 🍀

### Contoh 4: Unlucky dengan Hasil Negatif
```javascript
let angka = [1, 3, 5, 2];
let target = 0;

console.log(fortuneTeller(angka, target));
// Output: "Unlucky!"
```

**Penjelasan:**
- 1 (ganjil) → sum = 0 - 1 = -1
- 3 (ganjil) → sum = -1 - 3 = -4
- 5 (ganjil) → sum = -4 - 5 = -9
- 2 (genap) → sum = -9 + 2 = -7
- Hasil: -7 ≠ 0 → **"Unlucky!"** 💔

---

## 💡 Tips untuk Pemula

1. **Modulo (%)**: Operator `%` digunakan untuk mendapatkan sisa bagi. Angka genap jika `n % 2 === 0`
2. **If-Else Statement**: Digunakan untuk membuat keputusan berdasarkan kondisi tertentu
3. **Array Indexing**: `numbers[i]` mengakses elemen array pada posisi ke-i (dimulai dari 0)
4. **Loop**: `for` loop digunakan untuk mengiterasi setiap elemen dalam array
5. **Increment (i++)**: Menambahkan nilai i sebesar 1 setiap iterasi loop

---

## 🎓 Konsep yang Dipelajari

- ✅ Operasi matematika dasar (penjumlahan dan pengurangan)
- ✅ Conditional statement (if-else)
- ✅ Looping dengan for
- ✅ Array manipulation
- ✅ Operator modulo untuk cek genap/ganjil
- ✅ Comparison operator (===)
- ✅ Return statement

---

## 📚 Perbedaan Genap dan Ganjil

| Jenis | Ciri | Contoh | Operasi dalam Fungsi |
|-------|------|--------|---------------------|
| **Genap** | Habis dibagi 2 | 2, 4, 6, 8, 10 | Ditambahkan ke sum |
| **Ganjil** | Tidak habis dibagi 2 | 1, 3, 5, 7, 9 | Dikurangi dari sum |

---

## 🚀 Challenge

Coba modifikasi fungsi ini untuk:
1. Menghitung total angka genap dan ganjil secara terpisah
2. Mengembalikan informasi lebih detail (bukan hanya Lucky/Unlucky)
3. Menambahkan validasi input (cek apakah array kosong atau bukan)
4. Menampilkan selisih antara hasil dengan target

**Contoh Challenge:**
```javascript
// Tampilkan juga selisihnya
function fortuneTellerPlus(numbers, target) {
  let sum = 0;
  
  for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] % 2 === 0) {
      sum += numbers[i];
    } else {
      sum -= numbers[i];
    }
  }
  
  let difference = Math.abs(sum - target);
  
  if (sum === target) {
    return "Lucky! Tepat sasaran!";
  } else {
    return `Unlucky! Selisih ${difference} dari target`;
  }
}
```

---

## ❓ FAQ (Frequently Asked Questions)

**Q: Apa yang terjadi jika array kosong?**  
A: Fungsi akan mengembalikan "Lucky!" jika target = 0, atau "Unlucky!" jika target ≠ 0

**Q: Bisakah angka dalam array berupa desimal?**  
A: Ya bisa, tapi operasi modulo (%) akan tetap mengecek apakah habis dibagi 2 atau tidak

**Q: Apa yang terjadi jika target adalah angka negatif?**  
A: Fungsi akan tetap berjalan normal dan membandingkan hasil sum dengan target negatif tersebut
