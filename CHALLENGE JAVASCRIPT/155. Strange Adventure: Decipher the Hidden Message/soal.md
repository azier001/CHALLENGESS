# 🗺️ Strange Adventure: Decipher the Hidden Message

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Medium`

Buat sebuah function yang memecahkan pesan tersembunyi dengan menganalisis pola string dan susunan karakter. Challenge ini menggabungkan manipulasi string, pattern matching, dan pemikiran algoritma.

---

## 🎯 Function Signature

```javascript
function strangeAdventure(clues, cipher)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `clues` | `Array<string>` | Array berisi string yang mengandung potensi pesan tersembunyi |
| `cipher` | `string` | String referensi yang digunakan untuk mengidentifikasi pola yang cocok |

### Return Value

- **Tipe:** `string`
- **Mengembalikan:** Pesan tersembunyi yang telah dipecahkan atau `"No hidden message found!"` jika tidak ada yang cocok

---

## 🔍 Langkah-langkah Algorithm

### Langkah 1: Inisialisasi Storage
```javascript
let decipheredClues = [];
```
Buat array kosong untuk menyimpan substring yang valid.

### Langkah 2: Extract dan Bandingkan Substring

Untuk setiap string dalam array `clues`:

1. **Extract substring** yang panjangnya sama dengan string `cipher`
2. **Bandingkan setiap substring** dengan `cipher`:
   - Cek apakah mereka memiliki **panjang yang sama**
   - Verifikasi mereka mengandung **karakter yang sama** (urutan tidak masalah)
3. **Tambahkan substring yang cocok** ke `decipheredClues`

> 💡 **Tips:** Gunakan perbandingan frekuensi karakter atau sorting untuk mengecek apakah dua string adalah anagram

### Langkah 3: Handle Hasil Kosong

```javascript
if (decipheredClues.length === 0) {
    return "No hidden message found!";
}
```

Jika tidak ada substring yang cocok ditemukan, return pesan kegagalan.

### Langkah 4: Proses Deciphered Clues

#### 4a. Sort Berdasarkan Jumlah Character Code

Sort `decipheredClues` berdasarkan jumlah character code (nilai ASCII) dari setiap clue.

```javascript
// Contoh perhitungan jumlah character code
// "abc" → 97 + 98 + 99 = 294
```

#### 4b. Concatenate Sorted Clues

```javascript
let hiddenMessage = decipheredClues.join('');
```

Gabungkan semua clue yang sudah di-sort menjadi satu string.

#### 4c. Transform Message

Terapkan transformasi karakter:

| Karakter Asli | Transformasi |
|---------------|--------------|
| Huruf uppercase | Ganti dengan **spasi** ` ` |
| Huruf lowercase | Ubah menjadi **uppercase** |

#### 4d. Return Hasil

Return `hiddenMessage` yang sudah ditransformasi.

---

## 📝 Contoh Walkthrough

### Input
```javascript
clues = ["The quick brown", "fox jumps over", "the lazy dog"];
cipher = "abc";
```

### Proses
1. Extract substring 3 karakter: `"The"`, `"qui"`, `"ick"`, dll.
2. Temukan yang cocok (anagram dari `"abc"`): `"bac"`, `"cab"`, dll.
3. Sort berdasarkan jumlah character code
4. Concatenate dan transform

### Output
```javascript
"HIDDEN MESSAGE"
```

---

## 🎓 Konsep Utama

- **Manipulasi String**: Ekstraksi substring dan operasi karakter
- **Deteksi Anagram**: Membandingkan frekuensi karakter
- **Algoritma Sorting**: Custom sorting berdasarkan nilai yang dihitung
- **Operasi ASCII**: Bekerja dengan character code
- **Transformasi String**: Perubahan case karakter dan replacement

---

## ⚡ Pertimbangan Performance

- **Time Complexity**: O(n × m × k) di mana:
  - `n` = jumlah clue
  - `m` = rata-rata panjang setiap clue
  - `k` = panjang cipher
- **Space Complexity**: O(d) di mana `d` = jumlah deciphered clue

---

## 🚀 Tips Challenge

1. Gunakan helper function untuk menjaga kode tetap terorganisir
2. Pertimbangkan edge case (array kosong, single character)
3. Optimalkan pengecekan anagram dengan character frequency map
4. Test dengan berbagai panjang cipher dan kombinasi clue

---

**Semoga berhasil, petualang! Semoga kamu dapat memecahkan pesan tersembunyinya! 🔐✨**
