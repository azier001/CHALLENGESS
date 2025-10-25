# ⚡ Dokumentasi Fungsi `countLightningFlashes`

## 📋 Deskripsi

Fungsi `countLightningFlashes` digunakan untuk menghitung jumlah kilatan petir yang valid dalam sebuah string. Fungsi ini akan menghitung urutan karakter bintang (`*`) yang panjangnya antara 1 sampai 4 karakter, yang dipisahkan oleh karakter strip (`-`).

### Aturan Penghitungan:
- ✅ Kilatan valid: urutan `*` dengan panjang 1-4 karakter
- ❌ Kilatan tidak valid: urutan `*` dengan panjang lebih dari 4 karakter
- Kilatan dipisahkan oleh karakter `-`

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `flashes` | `string` | String yang berisi karakter `*` (kilatan) dan `-` (pemisah) |

---

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `number` | Jumlah kilatan petir yang valid (urutan `*` dengan panjang 1-4) |

---

## 💻 Code Fungsi

```javascript
function countLightningFlashes(flashes) {
  let count = 0;
  let currentSequence = 0;
  
  for (let i = 0; i < flashes.length; i++) {
    if (flashes[i] === '*') {
      // Tambah panjang urutan saat menemukan bintang
      currentSequence++;
    } else {
      // Jika bukan bintang (karakter '-'), cek validitas urutan
      if (currentSequence > 0 && currentSequence <= 4) {
        count++;
      }
      
      // Reset urutan untuk memulai penghitungan baru
      currentSequence = 0;
    }
  }
  
  // Cek urutan terakhir jika string berakhir dengan bintang
  if (currentSequence > 0 && currentSequence <= 4) {
    count++;
  }
  
  return count;
}
```

---

## 📊 Tabel Karakter

| Karakter | Fungsi | Keterangan |
|----------|--------|------------|
| `*` | Kilatan | Merepresentasikan satu flash/kilatan petir |
| `-` | Pemisah | Memisahkan antar urutan kilatan |

---

## 🎯 Contoh Penggunaan

### Contoh 1: Kilatan Valid
```javascript
const input1 = "*-**-***-****";
console.log(countLightningFlashes(input1));
```
**Output:** `4`

**Penjelasan:** 
- `*` → 1 kilatan (✅ valid)
- `**` → 2 kilatan (✅ valid)
- `***` → 3 kilatan (✅ valid)
- `****` → 4 kilatan (✅ valid)
- **Total: 4 kilatan valid**

---

### Contoh 2: Ada Kilatan Tidak Valid
```javascript
const input2 = "*-**-*****-***";
console.log(countLightningFlashes(input2));
```
**Output:** `3`

**Penjelasan:**
- `*` → 1 kilatan (✅ valid)
- `**` → 2 kilatan (✅ valid)
- `*****` → 5 kilatan (❌ tidak valid, lebih dari 4)
- `***` → 3 kilatan (✅ valid)
- **Total: 3 kilatan valid**

---

### Contoh 3: Tanpa Pemisah di Akhir
```javascript
const input3 = "**-***-**";
console.log(countLightningFlashes(input3));
```
**Output:** `3`

**Penjelasan:**
- `**` → 2 kilatan (✅ valid)
- `***` → 3 kilatan (✅ valid)
- `**` → 2 kilatan di akhir (✅ valid, dihitung meski tanpa `-`)
- **Total: 3 kilatan valid**

---

### Contoh 4: Hanya Kilatan Tidak Valid
```javascript
const input4 = "*****-******";
console.log(countLightningFlashes(input4));
```
**Output:** `0`

**Penjelasan:**
- `*****` → 5 kilatan (❌ tidak valid)
- `******` → 6 kilatan (❌ tidak valid)
- **Total: 0 kilatan valid**

---

### Contoh 5: String Kosong dan Edge Cases
```javascript
const input5 = "";
console.log(countLightningFlashes(input5));
// Output: 0

const input6 = "---";
console.log(countLightningFlashes(input6));
// Output: 0

const input7 = "****";
console.log(countLightningFlashes(input7));
// Output: 1
```

**Penjelasan:**
- String kosong: tidak ada kilatan (0)
- Hanya pemisah: tidak ada kilatan (0)
- Tepat 4 bintang: dihitung sebagai 1 kilatan valid

---

## 🔍 Cara Kerja Algoritma

1. **Inisialisasi**: 
   - Membuat variabel `count` untuk menghitung jumlah kilatan valid (dimulai dari 0)
   - Membuat variabel `currentSequence` untuk melacak panjang urutan bintang saat ini (dimulai dari 0)

2. **Iterasi Character by Character**:
   - **Jika karakter adalah `*`**: Tambahkan 1 ke `currentSequence`
   - **Jika karakter bukan `*` (pemisah `-`)**:
     - Cek apakah `currentSequence` valid (antara 1-4)
     - Jika valid, tambahkan 1 ke `count`
     - Reset `currentSequence` menjadi 0

3. **Pengecekan Akhir**: 
   - Setelah loop selesai, cek apakah ada urutan valid di akhir string
   - Ini menangani kasus di mana string berakhir dengan bintang (tanpa pemisah)

4. **Return**: Mengembalikan total `count` kilatan yang valid

---

## 🧩 Logika Program

```
Input: "*-**-***-****"

Iterasi:
i=0: '*' → currentSequence=1
i=1: '-' → valid (1≤4), count=1, reset
i=2: '*' → currentSequence=1
i=3: '*' → currentSequence=2
i=4: '-' → valid (2≤4), count=2, reset
i=5: '*' → currentSequence=1
i=6: '*' → currentSequence=2
i=7: '*' → currentSequence=3
i=8: '-' → valid (3≤4), count=3, reset
i=9: '*' → currentSequence=1
i=10: '*' → currentSequence=2
i=11: '*' → currentSequence=3
i=12: '*' → currentSequence=4

Setelah loop: currentSequence=4 (valid), count=4

Output: 4
```

---

## ⚠️ Catatan Penting

- Fungsi ini **case-sensitive** terhadap karakter `*` dan `-`
- Urutan yang tepat di akhir string (tanpa `-`) tetap dihitung sebagai valid
- Urutan dengan panjang 0 (misalnya `--`) tidak dihitung
- Urutan dengan lebih dari 4 `*` akan **diabaikan** dan tidak menambah count
- Karakter selain `*` dianggap sebagai pemisah dan akan mereset penghitungan urutan

---

## 🎨 Keunggulan Implementasi

- ✅ **Sederhana dan efisien**: Algoritma hanya memerlukan satu kali loop (O(n))
- ✅ **Mudah dipahami**: Logika yang straightforward tanpa nested loop
- ✅ **Memory efficient**: Hanya menggunakan 2 variabel tambahan
- ✅ **Handle edge cases**: Menangani string kosong, pemisah berurutan, dan akhiran tanpa pemisah

---

## 📝 Lisensi

Dokumentasi ini dibuat untuk tujuan pembelajaran dan referensi.
