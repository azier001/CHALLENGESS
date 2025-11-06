# 🌲 Dokumentasi Fungsi `exploreForest`

## 📋 Deskripsi

Fungsi `exploreForest` adalah sebuah fungsi JavaScript yang mensimulasikan eksplorasi hutan selama beberapa hari. Fungsi ini mengamati burung dan tanaman secara bergantian berdasarkan hari eksplorasi:
- **Hari ganjil** (1, 3, 5, ...): Mengamati burung 🐦
- **Hari genap** (2, 4, 6, ...): Mengamati tanaman 🌿

Yang membedakan dengan versi sebelumnya, fungsi ini akan **menambahkan satu item baru per hari** secara berurutan dari array, dan akan **berhenti** jika semua item dari kategori tersebut sudah diamati.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `birds` | Array | Array yang berisi nama-nama burung yang dapat diamati |
| `plants` | Array | Array yang berisi nama-nama tanaman yang dapat diamati |
| `explorationDays` | Number | Jumlah hari eksplorasi yang akan dilakukan |

---

## 📊 Cara Kerja

1. **Inisialisasi**: 
   - Array `observations` untuk menyimpan hasil pengamatan
   - Set `seenBirds` untuk melacak burung yang sudah diamati
   - Set `seenPlants` untuk melacak tanaman yang sudah diamati

2. **Iterasi Hari**: Loop berjalan dari hari 1 hingga `explorationDays`

3. **Pengamatan Bergantian**:
   - **Hari ganjil**: Loop melalui array `birds`, cari burung pertama yang belum diamati, tambahkan ke observations, lalu `break`
   - **Hari genap**: Loop melalui array `plants`, cari tanaman pertama yang belum diamati, tambahkan ke observations, lalu `break`

4. **Stop Otomatis**: Jika semua burung/tanaman sudah diamati, tidak ada yang ditambahkan pada hari tersebut

5. **Return**: Mengembalikan array berisi pengamatan dalam urutan penemuan

---

## 💻 Kode Fungsi

```javascript
function exploreForest(birds, plants, explorationDays) {
  // Array untuk menyimpan hasil pengamatan
  const observations = [];
  
  // Set untuk melacak burung yang sudah diamati
  const seenBirds = new Set();
  
  // Set untuk melacak tanaman yang sudah diamati
  const seenPlants = new Set();
  
  // Loop untuk setiap hari eksplorasi
  for (let day = 1; day <= explorationDays; day++) {
    
    // Hari ganjil - amati burung
    if (day % 2 !== 0) {
      
      // Loop melalui semua burung
      for (const bird of birds) {
        
        // Jika burung ini belum pernah diamati
        if (!seenBirds.has(bird)) {
          observations.push(bird);
          seenBirds.add(bird);
          break; // Keluar dari loop, hanya 1 burung per hari
        }
      }
    } 
    // Hari genap - amati tanaman
    else {
      
      // Loop melalui semua tanaman
      for (const plant of plants) {
        
        // Jika tanaman ini belum pernah diamati
        if (!seenPlants.has(plant)) {
          observations.push(plant);
          seenPlants.add(plant);
          break; // Keluar dari loop, hanya 1 tanaman per hari
        }
      }
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
| Hari | Tipe | Iterasi | Pengamatan | Status |
|------|------|---------|------------|--------|
| 1 | Burung (Ganjil) | Loop burung | Elang | ✅ Ditambahkan (pertama kali) |
| 2 | Tanaman (Genap) | Loop tanaman | Mawar | ✅ Ditambahkan (pertama kali) |
| 3 | Burung (Ganjil) | Loop burung | Merpati | ✅ Ditambahkan (pertama kali) |
| 4 | Tanaman (Genap) | Loop tanaman | Anggrek | ✅ Ditambahkan (pertama kali) |
| 5 | Burung (Ganjil) | Loop burung | Burung Hantu | ✅ Ditambahkan (pertama kali) |

---

### Contoh 2: Eksplorasi Lebih Lama dari Jumlah Item

```javascript
const birds = ["Kakaktua", "Beo"];
const plants = ["Melati", "Tulip", "Anggrek"];
const days = 10;

const result = exploreForest(birds, plants, days);
console.log(result);
```

**Output:**
```javascript
["Kakaktua", "Melati", "Beo", "Tulip", "Anggrek"]
```

**Penjelasan:**
| Hari | Tipe | Pencarian | Pengamatan | Status |
|------|------|-----------|------------|--------|
| 1 | Burung (Ganjil) | Loop burung | Kakaktua | ✅ Ditambahkan |
| 2 | Tanaman (Genap) | Loop tanaman | Melati | ✅ Ditambahkan |
| 3 | Burung (Ganjil) | Loop burung | Beo | ✅ Ditambahkan |
| 4 | Tanaman (Genap) | Loop tanaman | Tulip | ✅ Ditambahkan |
| 5 | Burung (Ganjil) | Loop burung | - | ❌ Semua burung sudah diamati |
| 6 | Tanaman (Genap) | Loop tanaman | Anggrek | ✅ Ditambahkan |
| 7 | Burung (Ganjil) | Loop burung | - | ❌ Semua burung sudah diamati |
| 8 | Tanaman (Genap) | Loop tanaman | - | ❌ Semua tanaman sudah diamati |
| 9 | Burung (Ganjil) | Loop burung | - | ❌ Semua burung sudah diamati |
| 10 | Tanaman (Genap) | Loop tanaman | - | ❌ Semua tanaman sudah diamati |

---

### Contoh 3: Eksplorasi Singkat

```javascript
const birds = ["Pipit", "Gagak", "Rajawali"];
const plants = ["Lily", "Dahlia"];
const days = 3;

const result = exploreForest(birds, plants, days);
console.log(result);
```

**Output:**
```javascript
["Pipit", "Lily", "Gagak"]
```

**Penjelasan:**
| Hari | Tipe | Pengamatan | Keterangan |
|------|------|------------|------------|
| 1 | Burung (Ganjil) | Pipit | Burung pertama |
| 2 | Tanaman (Genap) | Lily | Tanaman pertama |
| 3 | Burung (Ganjil) | Gagak | Burung kedua |

Eksplorasi berhenti di hari ke-3, masih ada item yang belum diamati (Rajawali dan Dahlia).

---

## 🎯 Poin Penting

- 🔄 **Urutan Sequential**: Fungsi akan mengamati item secara berurutan dari array (tidak menggunakan modulo/pengulangan)
- 🚫 **Tanpa Duplikasi**: Setiap item hanya akan diamati sekali
- ⏹️ **Auto-Stop**: Jika semua item dari kategori sudah diamati, hari tersebut tidak menambahkan pengamatan baru
- 📏 **Jumlah Maksimal**: Hasil maksimal adalah `birds.length + plants.length` item
- 🎲 **Tracking Terpisah**: Burung dan tanaman ditrack secara terpisah dengan Set masing-masing

---

## 🆚 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Ini | Versi Formula (Sebelumnya) |
|-------|-----------|----------------------------|
| Pengulangan | ❌ Tidak mengulang item | ✅ Mengulang dengan modulo |
| Tracking | 2 Set terpisah | 1 Set gabungan |
| Hasil Maksimal | Terbatas (`birds + plants`) | Bisa tak terbatas |
| Logika | Sequential (berurutan) | Calculated (dihitung) |

---

## 💡 Tips untuk Pemula

1. **Break Statement**: Kata kunci `break` digunakan untuk keluar dari loop setelah menemukan 1 item yang belum diamati
2. **Set per Kategori**: Menggunakan 2 Set berbeda memungkinkan tracking independen untuk burung dan tanaman
3. **For...of Loop**: Loop `for...of` lebih mudah dibaca untuk iterasi array dibanding `for` biasa
4. **Modulo !== 0**: Ekspresi `day % 2 !== 0` mengecek apakah hari ganjil (sisa bagi 2 bukan 0)

---

## 🔍 Return Value

**Tipe**: `Array`

**Deskripsi**: Array berisi string nama-nama burung dan tanaman yang diamati secara berurutan, maksimal sebanyak jumlah total item unik di kedua array input.

**Ukuran Maksimal**: `birds.length + plants.length`

---

## ⚠️ Edge Cases

1. **Array Kosong**: Jika `birds` atau `plants` kosong, kategori tersebut tidak akan memberikan kontribusi
2. **Hari Lebih Banyak**: Jika `explorationDays` lebih besar dari total item, hasil tetap maksimal sesuai jumlah item
3. **Hari Kurang**: Jika `explorationDays` lebih kecil dari total item, hanya sebagian item yang diamati
