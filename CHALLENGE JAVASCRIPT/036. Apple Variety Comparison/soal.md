# 🍎 Challenge Perbandingan Varietas Apel

## 📋 Gambaran Umum
Buat sebuah function yang mensimulasikan analisis ilmuwan terhadap varietas apel di kebun dengan membandingkan dua nama varietas apel dan menghitung skor kemiripannya.

---

## 🎯 Detail Challenge

**Tingkat Kesulitan:** `Easy`

**Nama Function:** `compareApples`

---

## 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `variety1` | `string` | Nama varietas apel pertama |
| `variety2` | `string` | Nama varietas apel kedua |
| `appleCount` | `number` | Jumlah apel yang akan dibandingkan |

---

## 🔍 Persyaratan Algorithm

### Perbandingan Character-by-Character
- Bandingkan dua nama varietas apel **character by character**
- Increment counter untuk setiap **matching character** pada posisi yang sama
- Jika nama memiliki panjang yang berbeda, hentikan perbandingan di akhir **nama yang lebih pendek**

### Perhitungan Similarity Score
```
Similarity Score = (Matching Characters / Length of Shorter Name) × 100
```

### Pembulatan
- Bulatkan similarity score ke **dua decimal places**

---

## 📤 Return Value

Function harus mengembalikan sebuah **string** yang mencakup:
- ✅ Nama kedua varietas apel
- ✅ Jumlah apel yang dibandingkan
- ✅ Similarity score (dibulatkan ke 2 decimal places)

---

## 💡 Contoh Penggunaan

```javascript
// Contoh pemanggilan function
compareApples("Gala", "Granny", 50);

// Format output yang diharapkan:
// "Comparing Gala and Granny varieties with 50 apples. Similarity score: 20.00%"
```

---

## 🧪 Konteks Ilmiah

Function ini mensimulasikan bagaimana para ilmuwan pertanian bisa:
- 🔬 Menganalisis kesamaan genetik antar varietas apel
- 📊 Membandingkan karakteristik morfologi
- 🌱 Mempelajari kompatibilitas breeding
- 📈 Menilai akurasi klasifikasi varietas

---

## 🎨 Tips Implementasi

> **Hint:** Pertimbangkan menggunakan string methods seperti `.length`, `.charAt()`, atau array indexing untuk mengakses individual characters.

> **Catatan:** Ingat untuk menangani edge cases dimana salah satu atau kedua string mungkin kosong.

---

*Selamat coding! 🚀*
