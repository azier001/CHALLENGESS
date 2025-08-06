# 🌺 Orchid Picket Shuffle

> **Tingkat Kesulitan:** `Easy` 🟢

## 📋 Gambaran Challenge

Bantu seorang botanis di greenhouse untuk melabeli picket anggrek dengan benar! Setiap picket ditandai dengan nomor, tetapi untuk memastikan anggrek mendapat sinar matahari yang cukup, digit-digit perlu diproses secara khusus.

## 🎯 Tujuan

Buat function bernama `orchidPicketShuffle` yang mentransformasi nomor picket melalui proses manipulasi digit tertentu.

## 📥 Function Signature

```javascript
function orchidPicketShuffle(picketNumber)
```

### Parameter
- **`picketNumber`** *(number)*: Nomor asli yang tertera pada picket anggrek

### Return
- **`number`**: Nomor picket yang sudah ditransformasi setelah diproses

## ⚙️ Langkah-Langkah Algorithm

Function harus melakukan operasi berikut **secara berurutan**:

1. **🔄 Convert ke String**
   - Ubah `picketNumber` menjadi string untuk mengakses digit individual

2. **↩️ Reverse Digit**
   - Balik urutan digit dalam string

3. **➕ Increment Setiap Digit**
   - Tambahkan 1 pada setiap digit
   - **Aturan Khusus:** `9` menjadi `0` setelah increment

4. **🔗 Gabungkan Hasil**
   - Gabungkan kembali digit yang sudah dimodifikasi menjadi string

5. **🔢 Convert ke Integer**
   - Ubah string akhir kembali menjadi number

## 💡 Contoh

### Contoh 1
```
Input:  1234
Step 1: "1234"        (convert ke string)
Step 2: "4321"        (reverse digit)
Step 3: "5432"        (increment setiap: 4→5, 3→4, 2→3, 1→2)
Output: 5432
```

### Contoh 2
```
Input:  9876
Step 1: "9876"        (convert ke string)
Step 2: "6789"        (reverse digit)
Step 3: "7890"        (increment setiap: 6→7, 7→8, 8→9, 9→0)
Output: 7890
```

## 🔍 Poin Penting yang Harus Diingat

- ⚠️ **Penting:** Digit `9` berubah menjadi `0` ketika di-increment
- 📊 Transformasi mempengaruhi **urutan** dan **nilai** digit
- 🎪 Operasi harus dilakukan dalam **urutan yang tepat** sesuai spesifikasi

## 🧪 Test Cases

| Input | Reversed | Setelah Increment | Output |
|-------|----------|-------------------|--------|
| `1234` | `"4321"` | `"5432"` | `5432` |
| `9876` | `"6789"` | `"7890"` | `7890` |
| `505` | `"505"` | `"616"` | `616` |
| `9999` | `"9999"` | `"0000"` | `0` |

---

*Selamat coding! 🚀 Transform picket anggrek tersebut dan bantu botanis menciptakan environment greenhouse yang sempurna!*
