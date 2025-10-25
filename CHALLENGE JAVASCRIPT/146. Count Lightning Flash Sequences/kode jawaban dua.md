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
    let sequenceLength = 0;
    
    for (let i = 0; i < flashes.length; i++) {
        if (flashes[i] === '*') {
            sequenceLength++;
            
            // Cek apakah sudah melebihi 4 kilatan
            if (sequenceLength > 4) {
                // Lewati sisa urutan ini
                while (i < flashes.length && flashes[i] === '*') {
                    i++;
                }
                
                i--; // Sesuaikan karena for loop akan increment
                sequenceLength = 0;
                continue;
            }
        } else {
            // Kita menemukan '-', jadi cek apakah ada urutan yang valid
            if (sequenceLength > 0 && sequenceLength <= 4) {
                count++;
            }
            
            sequenceLength = 0;
        }
    }
    
    // Cek apakah string berakhir dengan urutan yang valid
    if (sequenceLength > 0 && sequenceLength <= 4) {
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

## 🔍 Cara Kerja Algoritma

1. **Inisialisasi**: Membuat variabel `count` (penghitung) dan `sequenceLength` (panjang urutan)

2. **Iterasi**: Menelusuri setiap karakter dalam string:
   - Jika karakter `*`: tambah panjang urutan
   - Jika panjang urutan > 4: lewati sisa urutan ini (tidak valid)
   - Jika karakter `-`: cek apakah urutan sebelumnya valid (1-4), jika ya tambah count

3. **Finalisasi**: Cek urutan terakhir (jika string berakhir tanpa `-`)

4. **Return**: Mengembalikan jumlah total kilatan yang valid

---

## ⚠️ Catatan Penting

- Fungsi ini case-sensitive terhadap karakter `*` dan `-`
- Urutan yang tepat di akhir string (tanpa `-`) tetap dihitung sebagai valid
- Urutan dengan panjang 0 (misalnya `--`) tidak dihitung
- Urutan dengan lebih dari 4 `*` akan diabaikan sepenuhnya

---

## 📝 Lisensi

Dokumentasi ini dibuat untuk tujuan pembelajaran dan referensi.
