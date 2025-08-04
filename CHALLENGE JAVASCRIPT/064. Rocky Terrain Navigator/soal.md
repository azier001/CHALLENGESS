# 🏔️ Rocky Terrain Navigator

## 📋 Gambaran Challenge

**Level Kesulitan:** `Easy` 🟢

Buatlah function yang mensimulasikan navigasi melalui medan berbatu yang penuh dengan rintangan. Misi Anda adalah menentukan di mana navigator akan berakhir setelah mengambil langkah tertentu melalui medan yang menantang ini.

---

## 🎯 Deskripsi Problem

Anda perlu mengimplementasikan function bernama `rockyTerrainNavigator` yang mensimulasikan pergerakan melalui terrain 1D yang direpresentasikan oleh array string. Terrain ini berisi dua jenis elemen:

- **"Path"** - Jalur aman untuk berjalan
- **"Obstacle"** - Rintangan berbatu yang menyebabkan tersandung

### 🚶‍♂️ Aturan Navigasi

1. **Posisi Awal**: Mulai dari index `0` pada array terrain
2. **Pergerakan Normal**: Setiap langkah memindahkan Anda maju satu posisi
3. **Penalty Obstacle**: Menginjak "Obstacle" menyebabkan tersandung dan mundur satu langkah
4. **Batas Boundary**: Jika langkah Anda melewati ujung array, Anda tetap berada di elemen terakhir

---

## 📝 Spesifikasi Function

### Function Signature
```javascript
rockyTerrainNavigator(terrain, steps)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `terrain` | `Array<String>` | Array yang merepresentasikan jalur terrain, berisi "Path" atau "Obstacle" |
| `steps` | `Number` | Jumlah langkah maju yang direncanakan navigator |

### Return Value

| Type | Deskripsi |
|------|-----------|
| `Number` | Posisi akhir (index) dalam array terrain setelah navigasi |

---

## 💡 Contoh

### Contoh 1: Navigasi Dasar
```javascript
const terrain = ["Path", "Path", "Obstacle", "Path", "Path"];
const steps = 4;
// Hasil yang diharapkan: Navigator berakhir di index 3
```

### Contoh 2: Multiple Obstacle
```javascript
const terrain = ["Path", "Obstacle", "Obstacle", "Path"];
const steps = 3;
// Hasil yang diharapkan: Navigator berakhir di index 1
```

### Contoh 3: Melebihi Batas Array
```javascript
const terrain = ["Path", "Path", "Path"];
const steps = 10;
// Hasil yang diharapkan: Navigator berakhir di index 2 (elemen terakhir)
```

---

## 🔍 Pertimbangan Penting

- ⚠️ **Mekanisme Stumble**: Ketika menabrak obstacle, navigator mundur satu posisi
- 🛡️ **Proteksi Boundary**: Cegah navigasi melewati batas array
- 🎯 **Zero-based Indexing**: Ingat bahwa posisi array dimulai dari 0
- 🔄 **Penghitungan Step**: Setiap pergerakan maju dihitung sebagai satu langkah, terlepas dari stumble

---

## 🎮 Tips Challenge

1. **Track Position**: Pantau posisi saat ini saat iterasi melalui steps
2. **Validasi Bounds**: Selalu cek apakah posisi berikutnya dalam batas array
3. **Handle Obstacle**: Implementasikan logic mundur ketika bertemu obstacle
4. **Edge Case**: Pertimbangkan skenario dengan consecutive obstacle atau step count yang sangat besar

---

## 🏆 Kriteria Sukses

Solusi Anda harus:
- ✅ Menangani navigasi path normal dengan benar
- ✅ Mengimplementasikan mekanisme stumbling obstacle
- ✅ Menghormati boundary array
- ✅ Mengembalikan index posisi akhir yang akurat
- ✅ Menangani edge case dengan baik

---

*Semoga berhasil menavigasi medan berbatu! 🗻*
