# 🚤 Dokumentasi Fungsi riverBoatSimulation

## 📋 Deskripsi Fungsi

Fungsi `riverBoatSimulation` adalah sebuah simulasi pergerakan perahu-perahu di sungai. Fungsi ini mensimulasikan bagaimana perahu-perahu bergerak mengikuti arus sungai dengan kecepatan yang berbeda-beda tergantung urutan kedatangan mereka. Setiap perahu memiliki kecepatan yang unik berdasarkan posisinya dalam antrian.

## ⚡ Cara Kerja

- **Penambahan Perahu Baru**: Perahu baru ditambahkan di posisi 0 (titik awal sungai) pada langkah waktu genap (0, 2, 4, ...)
- **Kecepatan Perahu**: Setiap perahu memiliki kecepatan berdasarkan indeksnya + 1
  - Perahu pertama (indeks 0) bergerak dengan kecepatan 1
  - Perahu kedua (indeks 1) bergerak dengan kecepatan 2
  - Dan seterusnya...

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `initialPositions` | Array | Array berisi posisi awal perahu-perahu di sungai |
| `timeSteps` | Number | Jumlah langkah waktu untuk menjalankan simulasi |

## 🔄 Return Value

**Tipe**: `Array`

**Deskripsi**: Array berisi posisi akhir semua perahu setelah simulasi selesai

## 📊 Tabel Karakter Kecepatan

| Urutan Perahu | Indeks | Kecepatan | Simbol |
|---------------|--------|-----------|---------|
| 1️⃣ | 0 | 1 | 🚤 |
| 2️⃣ | 1 | 2 | ⛵ |
| 3️⃣ | 2 | 3 | 🛥️ |
| 4️⃣ | 3 | 4 | 🚢 |

## 💻 Kode Fungsi

```javascript
function riverBoatSimulation(initialPositions, timeSteps) {
    // Salin array posisi awal untuk menghindari mutasi data asli
    let boats = [...initialPositions];
    
    // Lakukan simulasi untuk setiap langkah waktu
    for (let step = 0; step < timeSteps; step++) {
        
        // Tambahkan perahu baru di posisi 0 pada langkah genap (0, 2, 4, ...)
        if (step % 2 === 0) {
            boats.unshift(0);
        }
        
        // Gerakkan semua perahu mengikuti arus sungai
        // Kecepatan setiap perahu = indeks + 1
        for (let i = 0; i < boats.length; i++) {
            boats[i] += (i + 1);
        }
    }
    
    // Kembalikan posisi akhir semua perahu
    return boats;
}
```

## 🧪 Contoh Penggunaan

### Contoh 1: Simulasi Dasar
```javascript
// Posisi awal: ada 2 perahu di posisi 1 dan 3
const initialPositions = [1, 3];
const timeSteps = 3;

const result = riverBoatSimulation(initialPositions, timeSteps);
console.log(result);
```

**Output:**
```javascript
[3, 9, 15]
```

### Contoh 2: Tanpa Perahu Awal
```javascript
// Mulai tanpa perahu
const initialPositions = [];
const timeSteps = 4;

const result = riverBoatSimulation(initialPositions, timeSteps);
console.log(result);
```

**Output:**
```javascript
[4, 6]
```

## 📈 Penjelasan Langkah Demi Langkah (Contoh 1)

| Langkah | Aksi | Posisi Perahu | Keterangan |
|---------|------|---------------|------------|
| **Awal** | - | `[1, 3]` | Posisi awal |
| **0** | ➕ Tambah perahu | `[0, 1, 3]` | Langkah genap, tambah perahu di posisi 0 |
| | 🏃 Gerak | `[1, 3, 6]` | Perahu bergerak: +1, +2, +3 |
| **1** | 🏃 Gerak | `[2, 5, 9]` | Perahu bergerak: +1, +2, +3 |
| **2** | ➕ Tambah perahu | `[0, 2, 5, 9]` | Langkah genap, tambah perahu |
| | 🏃 Gerak | `[1, 4, 8, 13]` | Perahu bergerak: +1, +2, +3, +4 |
| **Akhir** | - | `[3, 9, 15]` | Setelah langkah terakhir |

## 💡 Tips Penggunaan

1. **Untuk Pemula**: Mulai dengan `timeSteps` kecil (1-3) untuk memahami pola pergerakan
2. **Debugging**: Gunakan `console.log` di dalam loop untuk melihat pergerakan setiap langkah
3. **Optimasi**: Untuk simulasi besar, pertimbangkan untuk menggunakan struktur data yang lebih efisien

## ⚠️ Catatan Penting

- Perahu baru hanya ditambahkan pada langkah waktu genap (0, 2, 4, ...)
- Kecepatan perahu berubah setiap kali perahu baru ditambahkan (karena indeks berubah)
- Fungsi tidak mengubah array `initialPositions` yang asli

## 🎯 Use Case

Fungsi ini cocok untuk:
- Simulasi traffic management
- Game development (pergerakan objek)
- Pembelajaran algoritma dan struktur data
- Modeling sistem antrian dinamis
