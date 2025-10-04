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
4. **Perbandingan**: Hasil akhir dibandingkan dengan target
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
  // Return "Lucky!" jika sama, "Unlucky!" jika tidak
  return sum === target ? "Lucky!" : "Unlucky!";
}
```

---

## 📊 Contoh Penggunaan

### Contoh 1: Lucky (Beruntung)
```javascript
let angka = [2, 4, 6, 1, 3];
let target = 6;

console.log(fortuneTeller(angka, target));
// Output: "Lucky!"
```

**Penjelasan:**
- 2 (genap) → sum = 0 + 2 = 2
- 4 (genap) → sum = 2 + 4 = 6
- 6 (genap) → sum = 6 + 6 = 12
- 1 (ganjil) → sum = 12 - 1 = 11
- 3 (ganjil) → sum = 11 - 3 = 8
- Hasil: 8 ≠ 6 → **"Unlucky!"**

*(Maaf, koreksi: hasilnya Unlucky karena 8 ≠ 6)*

### Contoh 2: Lucky (Beruntung) - Yang Benar
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

### Contoh 3: Unlucky (Tidak Beruntung)
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

---

## 💡 Tips untuk Pemula

1. **Modulo (%)**: Operator `%` digunakan untuk mendapatkan sisa bagi. Angka genap jika `n % 2 === 0`
2. **Ternary Operator**: `kondisi ? nilaiJikaTrue : nilaiJikaFalse` adalah cara singkat menulis if-else
3. **Array Indexing**: `numbers[i]` mengakses elemen array pada posisi ke-i
4. **Loop**: `for` loop digunakan untuk mengiterasi setiap elemen dalam array

---

## 🎓 Konsep yang Dipelajari

- ✅ Operasi matematika dasar (penjumlahan dan pengurangan)
- ✅ Conditional statement (if-else)
- ✅ Looping dengan for
- ✅ Array manipulation
- ✅ Operator modulo untuk cek genap/ganjil
- ✅ Ternary operator

---

## 🚀 Challenge

Coba modifikasi fungsi ini untuk:
1. Menghitung total angka genap dan ganjil secara terpisah
2. Mengembalikan informasi lebih detail (bukan hanya Lucky/Unlucky)
3. Menambahkan validasi input (cek apakah array kosong atau bukan)
