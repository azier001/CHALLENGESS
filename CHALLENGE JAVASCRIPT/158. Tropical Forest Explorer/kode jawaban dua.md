# 🌲 Dokumentasi Fungsi `exploreForest`

## 📋 Deskripsi

Fungsi `exploreForest` adalah sebuah fungsi JavaScript yang mensimulasikan eksplorasi hutan selama beberapa hari. Fungsi ini mengamati burung dan tanaman secara bergantian berdasarkan hari eksplorasi:
- **Hari ganjil** (1, 3, 5, ...): Mengamati burung 🐦
- **Hari genap** (2, 4, 6, ...): Mengamati tanaman 🌿

Fungsi ini akan mengembalikan daftar pengamatan unik (tanpa duplikasi) yang ditemukan selama eksplorasi.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `birds` | Array | Array yang berisi nama-nama burung yang dapat diamati |
| `plants` | Array | Array yang berisi nama-nama tanaman yang dapat diamati |
| `explorationDays` | Number | Jumlah hari eksplorasi yang akan dilakukan |

---

## 📊 Cara Kerja

1. **Inisialisasi**: Fungsi membuat array kosong `observations` untuk menyimpan hasil pengamatan dan Set `seen` untuk melacak item yang sudah diamati
2. **Iterasi Hari**: Loop berjalan dari hari 1 hingga `explorationDays`
3. **Pengamatan Bergantian**:
   - Hari ganjil → Amati burung dengan formula: `Math.floor((day - 1) / 2) % birds.length`
   - Hari genap → Amati tanaman dengan formula: `Math.floor((day - 2) / 2) % plants.length`
4. **Filter Duplikasi**: Hanya menambahkan pengamatan yang belum pernah dilihat sebelumnya
5. **Return**: Mengembalikan array berisi pengamatan unik

---

## 💻 Kode Fungsi

```javascript
function exploreForest(birds, plants, explorationDays) {
  // Array untuk menyimpan hasil pengamatan
  const observations = [];
  
  // Set untuk melacak item yang sudah pernah diamati (mencegah duplikasi)
  const seen = new Set();
  
  // Loop untuk setiap hari eksplorasi
  for (let day = 1; day <= explorationDays; day++) {
    let observation;
    
    // Hari ganjil - amati burung
    if (day % 2 === 1) {
      const birdIndex = Math.floor((day - 1) / 2) % birds.length;
      observation = birds[birdIndex];
    } 
    // Hari genap - amati tanaman
    else {
      const plantIndex = Math.floor((day - 2) / 2) % plants.length;
      observation = plants[plantIndex];
    }
    
    // Hanya tambahkan jika belum pernah diamati sebelumnya
    if (!seen.has(observation)) {
      seen.add(observation);
      observations.push(observation);
    }
  }
  
  return observations;
}
```

---

## 📝 Contoh Penggunaan

### Contoh 1: Eksplorasi 5 Hari

```javascript
const birds = ["Elang", "Merpati", "Burung Hantu"];
const plants = ["Mawar", "Anggrek"];
const days = 5;

const result = exploreForest(birds, plants, days);
console.log(result);
```

**Output:**
```javascript
["Elang", "Mawar", "Merpati", "Anggrek", "Burung Hantu"]
```

**Penjelasan:**
| Hari | Tipe | Indeks | Pengamatan | Ditambahkan? |
|------|------|--------|------------|--------------|
| 1 | Burung | 0 | Elang | ✅ Ya |
| 2 | Tanaman | 0 | Mawar | ✅ Ya |
| 3 | Burung | 1 | Merpati | ✅ Ya |
| 4 | Tanaman | 1 | Anggrek | ✅ Ya |
| 5 | Burung | 2 | Burung Hantu | ✅ Ya |

---

### Contoh 2: Eksplorasi dengan Duplikasi

```javascript
const birds = ["Kakaktua", "Beo"];
const plants = ["Melati", "Tulip"];
const days = 8;

const result = exploreForest(birds, plants, days);
console.log(result);
```

**Output:**
```javascript
["Kakaktua", "Melati", "Beo", "Tulip"]
```

**Penjelasan:**
| Hari | Tipe | Indeks | Pengamatan | Ditambahkan? |
|------|------|--------|------------|--------------|
| 1 | Burung | 0 | Kakaktua | ✅ Ya |
| 2 | Tanaman | 0 | Melati | ✅ Ya |
| 3 | Burung | 1 | Beo | ✅ Ya |
| 4 | Tanaman | 1 | Tulip | ✅ Ya |
| 5 | Burung | 0 | Kakaktua | ❌ Tidak (duplikat) |
| 6 | Tanaman | 0 | Melati | ❌ Tidak (duplikat) |
| 7 | Burung | 1 | Beo | ❌ Tidak (duplikat) |
| 8 | Tanaman | 1 | Tulip | ❌ Tidak (duplikat) |

---

## 🎯 Poin Penting

- 🔄 **Pola Berulang**: Jika hari eksplorasi lebih banyak dari jumlah burung/tanaman, fungsi akan mengulang dari awal menggunakan operator modulo (`%`)
- 🚫 **Tanpa Duplikasi**: Setiap item hanya akan muncul sekali dalam hasil akhir, meskipun diamati berkali-kali
- 📅 **Urutan Tetap**: Urutan dalam hasil mengikuti urutan pertama kali item tersebut diamati

---

## 💡 Tips untuk Pemula

1. **Set vs Array**: Fungsi ini menggunakan `Set` untuk tracking karena lebih efisien dalam memeriksa keberadaan item dibanding array
2. **Modulo (%)**: Operator ini digunakan untuk "mengulang" indeks ketika mencapai akhir array
3. **Math.floor()**: Membulatkan angka ke bawah untuk mendapatkan indeks integer yang valid

---

## 🔍 Return Value

**Tipe**: `Array`

**Deskripsi**: Array berisi string nama-nama burung dan tanaman yang diamati, tanpa duplikasi, dalam urutan pertama kali ditemukan.
