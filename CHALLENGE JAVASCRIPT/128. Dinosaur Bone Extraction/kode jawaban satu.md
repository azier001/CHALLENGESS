# 🦕 Dokumentasi Fungsi `extractBoneStructure`

## 📖 Deskripsi

Fungsi `extractBoneStructure` digunakan untuk mengekstrak bagian tertentu dari struktur tulang dinosaurus. Fungsi ini mengambil potongan (slice) dari array tulang dinosaurus berdasarkan posisi awal dan posisi akhir yang ditentukan.

Bayangkan kamu punya deretan tulang dinosaurus yang tersusun rapi, dan kamu ingin mengambil beberapa tulang saja dari posisi tertentu. Fungsi ini akan membantu kamu melakukan hal tersebut! 🦴

---

## 🔧 Sintaks

```javascript
extractBoneStructure(dinosaurBones, startPosition, endPosition)
```

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `dinosaurBones` | Array | Array yang berisi data tulang-tulang dinosaurus. Bisa berupa array string, number, atau tipe data lainnya. |
| `startPosition` | Number | Posisi indeks awal dari tulang yang ingin diambil (inklusif). Dimulai dari 0. |
| `endPosition` | Number | Posisi indeks akhir dari tulang yang ingin diambil (inklusif). |

> **💡 Catatan:** Berbeda dengan method `slice()` biasa yang eksklusif pada parameter kedua, fungsi ini sudah menambahkan `+1` sehingga `endPosition` bersifat **inklusif** (ikut diambil).

---

## 📤 Return Value

Fungsi ini mengembalikan array baru yang berisi elemen-elemen dari `dinosaurBones` mulai dari `startPosition` hingga `endPosition` (keduanya termasuk).

---

## 💻 Source Code

```javascript
function extractBoneStructure(dinosaurBones, startPosition, endPosition) {
  // Mengambil potongan array dari posisi awal hingga posisi akhir (inklusif)
  // Menambahkan +1 pada endPosition agar posisi akhir ikut terambil
  return dinosaurBones.slice(startPosition, endPosition + 1);
}
```

---

## 📝 Contoh Penggunaan

### Contoh 1: Mengekstrak Tulang Dinosaurus (String)

```javascript
const tulangDino = ['tengkorak', 'leher', 'punggung', 'ekor', 'kaki'];

const hasil = extractBoneStructure(tulangDino, 1, 3);

console.log(hasil);
```

**Output:**
```
['leher', 'punggung', 'ekor']
```

**Penjelasan:** Mengambil tulang dari indeks 1 sampai 3, yaitu 'leher', 'punggung', dan 'ekor'.

---

### Contoh 2: Mengekstrak Nomor Urut Tulang

```javascript
const nomorTulang = [1, 2, 3, 4, 5, 6, 7, 8];

const hasil = extractBoneStructure(nomorTulang, 2, 5);

console.log(hasil);
```

**Output:**
```
[3, 4, 5, 6]
```

**Penjelasan:** Mengambil nomor tulang dari indeks 2 sampai 5, menghasilkan [3, 4, 5, 6].

---

### Contoh 3: Mengambil Satu Tulang Saja

```javascript
const tulangDino = ['kepala', 'badan', 'kaki'];

const hasil = extractBoneStructure(tulangDino, 0, 0);

console.log(hasil);
```

**Output:**
```
['kepala']
```

**Penjelasan:** Ketika `startPosition` dan `endPosition` sama, hanya satu elemen yang diambil.

---

## ⚠️ Hal yang Perlu Diperhatikan

1. **Indeks Array Dimulai dari 0** - Elemen pertama array berada di indeks 0, bukan 1.

2. **EndPosition Bersifat Inklusif** - Berbeda dengan `slice()` bawaan JavaScript, fungsi ini membuat `endPosition` ikut terambil karena sudah ditambah 1.

3. **Array Original Tidak Berubah** - Fungsi ini mengembalikan array baru tanpa mengubah array asli.

4. **Index Out of Range** - Jika posisi melebihi panjang array, JavaScript akan menanganinya dengan aman (tidak error), tetapi hasilnya mungkin tidak sesuai harapan.

---

## 🎯 Kapan Menggunakan Fungsi Ini?

Gunakan fungsi `extractBoneStructure` ketika kamu perlu:
- ✅ Mengambil beberapa elemen dari array berdasarkan posisi
- ✅ Memisahkan bagian tertentu dari data yang tersusun berurutan
- ✅ Membuat subset dari array tanpa mengubah array asli
- ✅ Bekerja dengan data yang memiliki struktur berurutan seperti timeline, deret, atau sequence

---

## 🔗 Referensi

- [MDN Web Docs - Array.prototype.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)

---

**Dibuat dengan 💚 untuk memudahkan pemahaman coding**
