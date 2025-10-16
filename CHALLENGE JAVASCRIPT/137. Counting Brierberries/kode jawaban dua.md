# 🫐 Dokumentasi Fungsi `countBrierberries`

## 📋 Deskripsi

Fungsi `countBrierberries` digunakan untuk menghitung **total buah brierberry** dari sekumpulan semak-semak. Fungsi ini akan menjumlahkan buah dari setiap semak **secara berurutan** sampai menemukan semak yang memiliki **lebih dari 10 buah**. Ketika menemukan semak dengan jumlah buah > 10, proses perhitungan akan **berhenti** dan mengembalikan total yang sudah dihitung sebelumnya.

---

## ⚙️ Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `bushes` | `Array<number>` | Array yang berisi jumlah buah brierberry di setiap semak. Setiap elemen array merepresentasikan satu semak dengan jumlah buahnya. |

---

## 🔄 Return Value

| Tipe Data | Deskripsi |
|-----------|-----------|
| `number` | Total jumlah buah brierberry yang berhasil dihitung sebelum menemukan semak dengan buah > 10, atau total semua buah jika tidak ada yang melebihi 10. |

---

## 💻 Source Code

```javascript
function countBrierberries(bushes) {
  // Variabel untuk menyimpan total buah
  let total = 0;
  
  // Looping melalui setiap semak dalam array
  for (let i = 0; i < bushes.length; i++) {
    
    // Cek apakah jumlah buah di semak ini lebih dari 10
    if (bushes[i] > 10) {
      // Jika iya, hentikan perhitungan
      break;
    }
    
    // Tambahkan jumlah buah dari semak ini ke total
    total += bushes[i];
  }
  
  // Kembalikan total buah yang sudah dihitung
  return total;
}
```

---

## 📊 Cara Kerja

1. **Inisialisasi**: Fungsi membuat variabel `total` dengan nilai awal 0
2. **Iterasi**: Fungsi melakukan looping dari semak pertama hingga semak terakhir
3. **Pengecekan**: Pada setiap semak, fungsi mengecek apakah jumlah buahnya > 10
   - Jika **YA** → Perhitungan dihentikan dengan `break`
   - Jika **TIDAK** → Jumlah buah ditambahkan ke `total`
4. **Return**: Fungsi mengembalikan nilai `total`

---

## 🎯 Contoh Penggunaan

### Contoh 1: Ada semak dengan buah > 10

```javascript
const semakSaya = [5, 3, 7, 15, 2, 4];
const hasil = countBrierberries(semakSaya);
console.log(hasil);
```

**Output:**
```
15
```

**Penjelasan:**
- Semak 1: 5 buah → total = 5
- Semak 2: 3 buah → total = 8
- Semak 3: 7 buah → total = 15
- Semak 4: 15 buah → **LEBIH DARI 10! Perhitungan berhenti**
- Semak 5 dan 6 tidak dihitung
- **Total akhir = 15**

---

### Contoh 2: Tidak ada semak dengan buah > 10

```javascript
const semakKecil = [3, 5, 2, 8, 1];
const hasil = countBrierberries(semakKecil);
console.log(hasil);
```

**Output:**
```
19
```

**Penjelasan:**
- Semua semak memiliki buah ≤ 10
- Semua buah dijumlahkan: 3 + 5 + 2 + 8 + 1 = 19
- **Total akhir = 19**

---

### Contoh 3: Semak pertama sudah > 10

```javascript
const semakBesar = [20, 5, 3, 7];
const hasil = countBrierberries(semakBesar);
console.log(hasil);
```

**Output:**
```
0
```

**Penjelasan:**
- Semak pertama langsung 20 buah (> 10)
- Perhitungan langsung berhenti sebelum menjumlahkan apapun
- **Total akhir = 0**

---

## ⚠️ Catatan Penting

- Fungsi ini **sensitif terhadap urutan** elemen dalam array
- Fungsi akan **berhenti** segera setelah menemukan nilai > 10
- Jika semak pertama sudah > 10, hasil akan **0**
- Array kosong akan mengembalikan **0**

---

## 🏷️ Use Case

Fungsi ini cocok digunakan untuk skenario seperti:
- ✅ Menghitung hasil panen yang masih dalam batas aman (tidak terlalu banyak per semak)
- ✅ Sistem monitoring yang berhenti ketika menemukan anomali
- ✅ Perhitungan progresif dengan kondisi pembatas tertentu
