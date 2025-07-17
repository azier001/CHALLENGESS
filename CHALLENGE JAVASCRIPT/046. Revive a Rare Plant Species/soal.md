# 🌿 Menghidupkan Kembali Spesies Tanaman Langka

## 🎯 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Sebagai seorang botanis dalam misi menyelamatkan spesies tanaman langka di hutan terpencil, Anda telah menemukan bahwa membalikkan sequence DNA tanaman dapat meremajakan dan mencegah kepunahan. Misi Anda adalah mengimplementasikan function yang membalikkan sequence DNA yang diberikan sambil mempertahankan format spesifiknya.

---

## 🧬 Ilmu di Baliknya

Sequence DNA direpresentasikan sebagai string dari nukleotida base:
- **A** (Adenine)
- **T** (Thymine) 
- **C** (Cytosine)
- **G** (Guanine)

Base-base ini dikelompokkan dalam set empat karakter, dipisahkan dengan spasi, meniru struktur codon genetik.

---

## 📋 Persyaratan Tugas

### Spesifikasi Function

Buat function bernama `reviveRarePlant` yang:

- **Nama Function:** `reviveRarePlant`
- **Parameter:** `dnaSequence` (string)
- **Return:** Modified DNA sequence (string)

### Format Input
- String dengan huruf kapital (A, T, C, G)
- Dikelompokkan dalam set empat karakter
- Setiap group dipisahkan dengan spasi
- Contoh: `'ATCG TGCA GCTA'`

### Format Output
- Sequence DNA yang dibalik
- Mempertahankan struktur grouping asli
- Menjaga spasi antar group
- Contoh: `'ATCG ACGT GCTA'`

---

## 💡 Contoh

### Input
```
'ATCG TGCA GCTA'
```

### Expected Output
```
'ATCG ACGT GCTA'
```

### Penjelasan
Function membalikkan seluruh sequence sambil mempertahankan pengelompokan 4 karakter dan pemisahan spasi.

---

## 🔬 Panduan Implementasi

1. **Preserve Structure:** Pertahankan pengelompokan asli 4 karakter
2. **Reverse Logic:** Terapkan pembalikan ke seluruh sequence
3. **Format Consistency:** Jaga spasi antar group
4. **Case Sensitivity:** Bekerja dengan huruf kapital saja

---

## 🌟 Kriteria Sukses

- ✅ Function berhasil membalikkan sequence DNA
- ✅ Mempertahankan format grouping asli
- ✅ Menjaga spasi antar group
- ✅ Menangani berbagai panjang input
- ✅ Return string dengan format yang tepat

---

## 🚨 Misi Kritis

> **Ingat:** Nasib spesies tanaman langka ada di tangan Anda! Implementasi Anda akan menentukan apakah spesies yang terancam punah ini bisa diselamatkan dari kepunahan.

**Semoga berhasil, botanis!** 🔬🌱

---

*Kategori Challenge: String Manipulation | Kesulitan: Easy | Tema: Bioinformatics*
