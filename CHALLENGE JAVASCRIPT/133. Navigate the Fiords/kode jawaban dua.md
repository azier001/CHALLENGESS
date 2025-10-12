# 📍 Dokumentasi Fungsi `navigateFiords`

## 📖 Deskripsi

Fungsi `navigateFiords` digunakan untuk menavigasi posisi dalam sebuah array berdasarkan arah yang diberikan. Fungsi ini akan memproses setiap arah secara berurutan dan mengubah posisi saat ini sesuai dengan aturan pergerakan. Jika posisi keluar dari batas array, fungsi akan mengembalikan status `'lost'`. Jika navigasi berhasil, fungsi akan mengembalikan nilai pada posisi akhir.

---

## 🎯 Fungsi Utama

Fungsi ini mensimulasikan perjalanan melalui fjord (teluk sempit) dengan mengikuti serangkaian petunjuk arah.

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `directions` | Array | Array yang berisi petunjuk arah navigasi (string) dan juga berfungsi sebagai peta perjalanan |
| `startingPoint` | Number | Posisi awal dalam array (indeks) |

---

## 🧭 Aturan Pergerakan

| Arah | Karakter | Efek pada Posisi | Penjelasan |
|------|----------|------------------|------------|
| Utara | `'north'` | `-1` | Posisi berkurang 1 (mundur ke indeks sebelumnya) |
| Selatan | `'south'` | `+1` | Posisi bertambah 1 (maju ke indeks berikutnya) |
| Timur | `'east'` | `0` | Tetap di posisi saat ini (tidak bergerak) |
| Barat | `'west'` | `+2` | Posisi bertambah 2 (loncat 2 indeks ke depan) |

---

## 📤 Return Value

| Kondisi | Return Value | Tipe |
|---------|--------------|------|
| Navigasi berhasil | Nilai pada posisi akhir di array `directions` | String |
| Keluar dari batas array | `'lost'` | String |

---

## 💻 Source Code

```javascript
function navigateFiords(directions, startingPoint) {
  // Inisialisasi posisi saat ini dengan titik awal
  let currentPosition = startingPoint;
  
  // Loop melalui setiap arah dalam array directions
  for (let i = 0; i < directions.length; i++) {
    
    // Tentukan pergerakan berdasarkan arah
    switch (directions[i]) {
      case 'north':
        // Gerak ke utara: mundur 1 posisi
        currentPosition--;
        break;
        
      case 'south':
        // Gerak ke selatan: maju 1 posisi
        currentPosition++;
        break;
        
      case 'east':
        // Gerak ke timur: tetap di posisi saat ini
        break;
        
      case 'west':
        // Gerak ke barat: loncat 2 posisi ke depan
        currentPosition += 2;
        break;
    }
    
    // Cek apakah posisi keluar dari batas array
    if (currentPosition < 0 || currentPosition >= directions.length) {
      return 'lost'; // Kembali dengan status tersesat
    }
  }
  
  // Kembali dengan nilai pada posisi akhir
  return directions[currentPosition];
}
```

---

## 🎮 Contoh Penggunaan

### Contoh 1: Navigasi Berhasil

```javascript
const directions1 = ['north', 'south', 'east', 'west'];
const result1 = navigateFiords(directions1, 2);
console.log(result1);
```

**Output:**
```
'lost'
```

**Penjelasan:**
- Mulai di indeks `2` (nilai: `'east'`)
- Baca `'north'` → posisi: `2 - 1 = 1`
- Baca `'south'` → posisi: `1 + 1 = 2`
- Baca `'east'` → posisi: `2` (tetap)
- Baca `'west'` → posisi: `2 + 2 = 4` (keluar batas!)
- **Hasil:** `'lost'`

---

### Contoh 2: Status Tersesat

```javascript
const directions2 = ['east', 'north', 'west', 'south'];
const result2 = navigateFiords(directions2, 0);
console.log(result2);
```

**Output:**
```
'lost'
```

**Penjelasan:**
- Mulai di indeks `0` (nilai: `'east'`)
- Baca `'east'` → posisi: `0` (tetap)
- Baca `'north'` → posisi: `0 - 1 = -1` (keluar batas!)
- **Hasil:** `'lost'` (karena posisi negatif)

---

### Contoh 3: Tetap di Jalur

```javascript
const directions3 = ['south', 'east', 'east', 'north'];
const result3 = navigateFiords(directions3, 1);
console.log(result3);
```

**Output:**
```
'east'
```

**Penjelasan:**
- Mulai di indeks `1` (nilai: `'east'`)
- Baca `'south'` → posisi: `1 + 1 = 2`
- Baca `'east'` → posisi: `2` (tetap)
- Baca `'east'` → posisi: `2` (tetap)
- Baca `'north'` → posisi: `2 - 1 = 1`
- **Hasil:** `directions[1]` = `'east'`

---

## ⚠️ Catatan Penting

- Array `directions` berfungsi ganda: sebagai **petunjuk arah** yang dibaca dan sebagai **peta** yang menentukan nilai return
- Posisi dianggap `'lost'` jika:
  - Kurang dari `0` (terlalu jauh ke belakang)
  - Lebih besar atau sama dengan `directions.length` (terlalu jauh ke depan)
- Arah `'east'` tidak mengubah posisi sama sekali
- Fungsi akan memproses **semua arah** dalam array sebelum mengembalikan hasil akhir

---

## 🎓 Tips untuk Pemula

1. **Indeks Array**: Ingat bahwa array dimulai dari indeks 0
2. **Batas Array**: Pastikan posisi selalu berada di antara `0` dan `directions.length - 1`
3. **Loop dan Switch**: Fungsi ini menggabungkan loop `for` dan `switch-case` untuk kontrol alur
4. **Return Awal**: Fungsi bisa berhenti lebih awal jika kondisi `'lost'` terpenuhi

---

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
