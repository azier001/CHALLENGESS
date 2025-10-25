# ⚡ Hitung Urutan Kilatan Petir

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang menganalisis pola kilatan petir yang direkam oleh sensor dan menghitung urutan yang valid.

---

## 🎯 Tujuan

Implementasikan function bernama `countLightningFlashes` yang memproses string data sensor petir.

---

## 📥 Input

Function menerima:
- Sebuah **string** yang hanya berisi dua karakter:
  - `*` → Kilatan petir terdeteksi
  - `-` → Tidak ada kilatan

**Contoh input:**
```
"**-***----*-**"
```

---

## 📤 Output

Return **total jumlah** urutan kilatan petir berurutan yang valid.

---

## 📏 Aturan & Batasan

### ✅ Yang Perlu Dihitung
- Sebuah **sequence** didefinisikan sebagai satu atau lebih karakter `*` yang muncul secara berurutan
- Setiap sequence yang valid berkontribusi `1` terhadap total hitungan

### ❌ Yang Harus Diabaikan
- **Sequence yang lebih panjang dari 4 kilatan** harus dikecualikan dari hitungan
- Gunakan statement `break` dan `continue` untuk menangani sequence yang panjang ini

### 💡 Contoh

| Input | Sequence Valid | Jumlah | Penjelasan |
|-------|----------------|--------|------------|
| `"**-***-*"` | `**`, `***`, `*` | **3** | Semua sequence ≤ 4 kilatan |
| `"*****-**"` | `**` | **1** | Sequence pertama (5 kilatan) diabaikan |
| `"*-**-***-****"` | `*`, `**`, `***`, `****` | **4** | Semua sequence ≤ 4 kilatan |
| `"*****"` | tidak ada | **0** | Sequence melebihi 4 kilatan |

---

## 🔧 Persyaratan Teknis

- **Nama function:** `countLightningFlashes`
- **Harus menggunakan:** statement `break` dan/atau `continue` untuk control flow
- **Parameter:** Single string argument
- **Return type:** Number (integer)

---

## 💭 Petunjuk

- Pikirkan tentang bagaimana mengidentifikasi kapan sebuah sequence dimulai dan berakhir
- Pertimbangkan untuk melacak panjang setiap sequence saat Anda melakukan iterasi
- Ingat untuk mereset sequence counter Anda dengan tepat
- Gunakan `continue` atau `break` ketika Anda mendeteksi sequence yang melebihi 4 kilatan

---

## 🚀 Memulai

```javascript
function countLightningFlashes(sensorData) {
  // Kode Anda di sini
}

// Test cases
console.log(countLightningFlashes("**-***-*"));        // Expected: 3
console.log(countLightningFlashes("*****-**"));        // Expected: 1
console.log(countLightningFlashes("*-**-***-****"));   // Expected: 4
```

---

**Semangat! ⚡**
