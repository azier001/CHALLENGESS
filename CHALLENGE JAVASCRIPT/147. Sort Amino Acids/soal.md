# 🧬 Tantangan Sort Amino Acids

## 📋 Ringkasan Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function yang mengurutkan amino acids secara alfabetis sambil memfilter entri yang tidak valid.

---

## 🎯 Objektif

Implementasikan sebuah function bernama **`sortProtein`** yang:

1. Menerima sebuah **array of strings** yang merepresentasikan amino acids
2. Mengurutkan amino acids secara **alfabetis**
3. Mengembalikan **sorted array**
4. **Melewati amino acids yang tidak valid** dan melanjutkan sorting untuk yang valid

---

## ✅ Amino Acids yang Valid

Function harus mengenali **20 amino acids standar** berikut:

- **Alanine**
- **Arginine**
- **Asparagine**
- **Aspartic acid**
- **Cysteine**
- **Glutamic acid**
- **Glutamine**
- **Glycine**
- **Histidine**
- **Isoleucine**
- **Leucine**
- **Lysine**
- **Methionine**
- **Phenylalanine**
- **Proline**
- **Serine**
- **Threonine**
- **Tryptophan**
- **Tyrosine**
- **Valine**

---

## 📝 Function Signature

```javascript
function sortProtein(aminoAcids) {
  // Implementasi Anda di sini
}
```

---

## 💡 Persyaratan

| Persyaratan | Deskripsi |
|------------|-------------|
| **Input** | Array of strings (nama amino acids) |
| **Output** | Sorted array dari amino acids yang valid |
| **Validasi** | Filter amino acids yang tidak valid |
| **Sorting** | Urutan alfabetis (A-Z) |

---

## 🧪 Contoh Penggunaan

```javascript
// Contoh 1: Semua amino acids valid
sortProtein(['Glycine', 'Alanine', 'Valine']);
// Expected output: ['Alanine', 'Glycine', 'Valine']

// Contoh 2: Campuran valid dan invalid
sortProtein(['Glycine', 'InvalidAcid', 'Alanine', 'Unknown', 'Valine']);
// Expected output: ['Alanine', 'Glycine', 'Valine']

// Contoh 3: Empty array
sortProtein([]);
// Expected output: []
```

---

## 🔑 Poin Penting

> **Catatan:** Function harus case-sensitive dan mencocokkan nama amino acids persis seperti yang tercantum di atas.

- ✨ Hanya 20 amino acids standar yang dianggap valid
- 🔍 Entri yang tidak valid harus diabaikan secara diam-diam
- 📊 Return empty array jika tidak ada amino acids yang valid ditemukan
- 🎨 Pertahankan alphabetical sorting untuk output

---

## 🚀 Memulai

Pikirkan tentang:
- Bagaimana cara memvalidasi amino acids secara efisien
- Pendekatan sorting terbaik untuk strings
- Edge cases (empty arrays, semua entri invalid, duplikat)

Semangat! 🍀
