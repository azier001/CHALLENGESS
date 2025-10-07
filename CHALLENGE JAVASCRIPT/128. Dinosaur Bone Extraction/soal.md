# 🦕 Tantangan Ekstraksi Tulang Dinosaurus

## Tingkat Kesulitan
**Easy** ⭐

---

## 📋 Gambaran Umum Tantangan

Bantu para paleontolog di museum sejarah alam untuk mengekstrak tulang-tulang tertentu dari kerangka dinosaurus untuk dipelajari lebih lanjut! Tugasmu adalah membuat sebuah function yang secara selektif mengambil segmen tulang dari array kerangka lengkap.

---

## 🎯 Objektif

Buat sebuah function bernama `extractBoneStructure` yang menerima tiga parameter dan mengembalikan array baru yang berisi hanya tulang-tulang terpilih dari rentang yang ditentukan.

---

## 📥 Parameter Function

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `dinosaurBones` | `array` | Sebuah array dari string yang merepresentasikan tulang-tulang berbeda dalam kerangka dinosaurus |
| `startPosition` | `number` | Index awal untuk ekstraksi **(inklusif)** |
| `endPosition` | `number` | Index akhir untuk ekstraksi **(inklusif)** |

---

## 📤 Return Value

Function harus mengembalikan **array baru** yang berisi tulang-tulang yang diekstrak dari posisi yang ditentukan.

---

## 🔧 Persyaratan Implementasi

- Gunakan **array slicing** untuk mengekstrak tulang-tulang yang ditentukan
- Ekstrak tulang mulai dari `startPosition` hingga dan **termasuk** `endPosition`
- Return array baru tanpa memodifikasi array `dinosaurBones` yang asli

---

## 💡 Poin Penting untuk Diingat

- ✅ Posisi awal bersifat **inklusif**
- ✅ Posisi akhir bersifat **inklusif**
- ✅ Gunakan metode array slicing
- ✅ Return array baru
- ✅ Jangan memodifikasi array asli

---

## 📝 Function Signature

```javascript
function extractBoneStructure(dinosaurBones, startPosition, endPosition) {
  // Kode kamu di sini
}
```

---

## 🧪 Contoh Penggunaan

```javascript
const skeleton = ['skull', 'vertebra', 'rib', 'femur', 'tibia', 'claw'];
const extracted = extractBoneStructure(skeleton, 1, 3);

console.log(extracted);
// Expected output: ['vertebra', 'rib', 'femur']
```

---

## 🎓 Tujuan Pembelajaran

- Memahami operasi array slicing
- Bekerja dengan rentang index inklusif
- Mengekstrak subarray tanpa mutasi
- Menerapkan metode array secara praktis

---

**Semangat, paleontolog! 🦴🔬**
