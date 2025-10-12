# 📍 Dokumentasi Fungsi `navigateFiords`

## 📖 Deskripsi

Fungsi `navigateFiords` digunakan untuk menavigasi posisi dalam sebuah array berdasarkan arah yang diberikan. Fungsi ini akan memproses setiap arah secara berurutan dan mengubah posisi saat ini sesuai dengan aturan pergerakan. Fungsi ini memiliki **validasi batas** yang ketat - setiap pergerakan akan diperiksa terlebih dahulu sebelum dilakukan. Jika pergerakan akan menyebabkan posisi keluar dari batas array, fungsi akan langsung mengembalikan status `'lost'`. Jika navigasi berhasil, fungsi akan mengembalikan nilai pada posisi akhir.

---

## 🎯 Fungsi Utama

Fungsi ini mensimulasikan perjalanan melalui fjord (teluk sempit) dengan mengikuti serangkaian petunjuk arah dengan sistem validasi keamanan yang ketat.

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `directions` | Array | Array yang berisi petunjuk arah navigasi (string) dan juga berfungsi sebagai peta perjalanan |
| `startingPoint` | Number | Posisi awal dalam array (indeks) |

---

## 🧭 Aturan Pergerakan

| Arah | Karakter | Efek pada Posisi | Kondisi Valid | Penjelasan |
|------|----------|------------------|---------------|------------|
| Utara | `'north'` | `-1` | `currentPosition > 0` | Posisi berkurang 1 (mundur ke indeks sebelumnya) |
| Selatan | `'south'` | `+1` | `currentPosition < directions.length - 1` | Posisi bertambah 1 (maju ke indeks berikutnya) |
| Timur | `'east'` | `0` | Selalu valid | Tetap di posisi saat ini (tidak bergerak) |
| Barat | `'west'` | `+2` | `currentPosition + 2 < directions.length` | Posisi bertambah 2 (loncat 2 indeks ke depan) |

---

## 📤 Return Value

| Kondisi | Return Value | Tipe |
|---------|--------------|------|
| Navigasi berhasil | Nilai pada posisi akhir di array `directions` | String |
| Pergerakan akan keluar dari batas array | `'lost'` | String |

---

## 💻 Source Code

```javascript
function navigateFiords(directions, startingPoint) {
  // Inisialisasi posisi saat ini dengan titik awal
  let currentPosition = startingPoint;
  
  // Loop melalui setiap arah dalam array directions
  for (let i = 0; i < directions.length; i++) {
    
    // Tentukan pergerakan berdasarkan arah dengan validasi batas
    switch (directions[i]) {
      case 'north':
        // Gerak ke utara: mundur 1 posisi
        if (currentPosition > 0) {
          currentPosition--;
        } else {
          // Tidak bisa mundur lagi (sudah di posisi 0)
          return 'lost';
        }
        break;
        
      case 'south':
        // Gerak ke selatan: maju 1 posisi
        if (currentPosition < directions.length - 1) {
          currentPosition++;
        } else {
          // Tidak bisa maju lagi (sudah di posisi terakhir)
          return 'lost';
        }
        break;
        
      case 'east':
        // Gerak ke timur: tetap di posisi saat ini
        // Tidak ada pergerakan, selalu aman
        break;
        
      case 'west':
        // Gerak ke barat: loncat 2 posisi ke depan
        if (currentPosition + 2 < directions.length) {
          currentPosition += 2;
        } else {
          // Loncatan akan keluar dari batas array
          return 'lost';
        }
        break;
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
const directions1 = ['north', 'south', 'east', 'west', 'north'];
const result1 = navigateFiords(directions1, 2);
console.log(result1);
```

**Output:**
```
'north'
```

**Penjelasan:**
- Mulai di indeks `2` (nilai: `'east'`)
- Baca `'north'` → validasi OK (2 > 0) → posisi: `2 - 1 = 1`
- Baca `'south'` → validasi OK (1 < 4) → posisi: `1 + 1 = 2`
- Baca `'east'` → posisi: `2` (tetap)
- Baca `'west'` → validasi OK (2 + 2 = 4 < 5) → posisi: `2 + 2 = 4`
- Baca `'north'` → validasi OK (4 > 0) → posisi: `4 - 1 = 3`
- **Hasil:** `directions[3]` = `'west'`

*Koreksi: Output sebenarnya adalah `'west'`*

---

### Contoh 2: Status Tersesat - Mundur dari Batas

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
- Baca `'north'` → validasi GAGAL (0 tidak > 0) → tidak bisa mundur!
- **Hasil:** `'lost'` (tersesat di langkah kedua)

---

### Contoh 3: Status Tersesat - Loncat Keluar Batas

```javascript
const directions3 = ['south', 'west', 'east', 'north'];
const result3 = navigateFiords(directions3, 2);
console.log(result3);
```

**Output:**
```
'lost'
```

**Penjelasan:**
- Mulai di indeks `2` (nilai: `'east'`)
- Baca `'south'` → validasi OK (2 < 3) → posisi: `2 + 1 = 3`
- Baca `'west'` → validasi GAGAL (3 + 2 = 5, tidak < 4) → akan keluar batas!
- **Hasil:** `'lost'` (loncatan terlalu jauh)

---

### Contoh 4: Navigasi Aman dengan East

```javascript
const directions4 = ['east', 'east', 'south', 'east'];
const result4 = navigateFiords(directions4, 0);
console.log(result4);
```

**Output:**
```
'south'
```

**Penjelasan:**
- Mulai di indeks `0` (nilai: `'east'`)
- Baca `'east'` → posisi: `0` (tetap)
- Baca `'east'` → posisi: `0` (tetap)
- Baca `'south'` → validasi OK (0 < 3) → posisi: `0 + 1 = 1`
- Baca `'east'` → posisi: `1` (tetap)
- **Hasil:** `directions[1]` = `'east'`

*Koreksi: Output sebenarnya adalah `'east'`*

---

## 🔒 Sistem Validasi Batas

Fungsi ini menggunakan **pendekatan preventif** untuk mencegah posisi keluar dari batas:

### Validasi Mundur (North)
```javascript
if (currentPosition > 0) {
  // Aman untuk mundur
} else {
  return 'lost'; // Sudah di awal array
}
```

### Validasi Maju (South)
```javascript
if (currentPosition < directions.length - 1) {
  // Aman untuk maju
} else {
  return 'lost'; // Sudah di akhir array
}
```

### Validasi Loncat (West)
```javascript
if (currentPosition + 2 < directions.length) {
  // Aman untuk loncat 2 posisi
} else {
  return 'lost'; // Loncatan akan keluar batas
}
```

---

## ⚠️ Catatan Penting

- Array `directions` berfungsi ganda: sebagai **petunjuk arah** yang dibaca dan sebagai **peta** yang menentukan nilai return
- **Validasi dilakukan SEBELUM pergerakan**, bukan setelah - ini mencegah posisi invalid
- Arah `'east'` tidak memerlukan validasi karena tidak mengubah posisi
- Fungsi akan **langsung berhenti** saat pergerakan tidak valid (tidak melanjutkan ke arah berikutnya)
- Perbedaan dengan versi sebelumnya: fungsi ini lebih aman karena memeriksa validitas sebelum melakukan pergerakan

---

## 🎓 Tips untuk Pemula

1. **Indeks Array**: Ingat bahwa array dimulai dari indeks 0
2. **Batas Array**: Indeks valid adalah dari `0` hingga `directions.length - 1`
3. **Validasi Preventif**: Selalu periksa batas sebelum mengubah nilai
4. **Loop dan Switch**: Fungsi ini menggabungkan loop `for` dan `switch-case` untuk kontrol alur
5. **Early Return**: Fungsi bisa berhenti lebih awal jika validasi gagal - ini adalah pola yang baik untuk error handling

---

## 🆚 Perbandingan dengan Versi Lain

| Aspek | Versi Ini | Versi Tanpa Validasi |
|-------|-----------|----------------------|
| Keamanan | ✅ Sangat aman | ⚠️ Bisa crash |
| Validasi | Sebelum pergerakan | Setelah pergerakan |
| Error Handling | Preventif | Reaktif |
| Performa | Sedikit lebih lambat | Lebih cepat |
| Rekomendasi | **Production-ready** | Hanya untuk demo |

---

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
