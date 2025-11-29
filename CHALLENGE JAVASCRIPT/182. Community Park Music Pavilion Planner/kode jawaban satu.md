# 🎢 Dokumentasi Fungsi `planParkDay`

## 📋 Deskripsi

Fungsi `planParkDay` adalah fungsi untuk merencanakan hari operasional taman hiburan. Fungsi ini membantu mengelola jadwal pertunjukan, menghitung kebutuhan ruang untuk pengunjung, dan mengidentifikasi tugas perawatan yang perlu dilakukan.

Fungsi ini akan menghasilkan ringkasan jadwal dengan jumlah penonton, menghitung total ruang yang dibutuhkan berdasarkan jumlah pengunjung, dan menemukan tugas perawatan pertama yang masih pending.

---

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `schedules` | Array (String) | Daftar jadwal pertunjukan atau acara di taman |
| `inventory` | Array | Inventaris item (parameter ini tidak digunakan dalam fungsi saat ini) |
| `audienceCounts` | Array (Number) | Jumlah penonton untuk setiap jadwal pertunjukan |
| `tasks` | Array (String) | Daftar tugas perawatan dengan format "namaTugas:status" |

---

## 📊 Return Value

Fungsi ini mengembalikan sebuah **objek** dengan struktur berikut:

| Property | Tipe | Deskripsi |
|----------|------|-----------|
| `summary` | String | Ringkasan jadwal dengan jumlah penonton dalam format "Jadwal1(jumlah)Jadwal2(jumlah)..." |
| `spaceNeeded` | Number | Total ruang yang dibutuhkan (dihitung dengan rumus: jumlah penonton × 1.5) |
| `nextMaintenance` | String | Nama tugas perawatan pertama yang berstatus "pending", atau string kosong jika tidak ada |

---

## 💻 Kode Fungsi

```javascript
function planParkDay(schedules, inventory, audienceCounts, tasks) {
    
    // Membuat ringkasan string dengan menggabungkan jadwal dan jumlah penonton
    let summary = "";
    for (let i = 0; i < schedules.length; i++) {
        summary += schedules[i] + "(" + audienceCounts[i] + ")";
    }
    
    // Menghitung total ruang yang dibutuhkan
    let spaceNeeded = 0;
    for (let i = 0; i < audienceCounts.length; i++) {
        spaceNeeded += Math.floor(audienceCounts[i] * 1.5);
    }
    
    // Mencari tugas perawatan pertama yang berstatus pending
    let nextMaintenance = "";
    for (let i = 0; i < tasks.length; i++) {
        let taskParts = tasks[i].split(":");
        let taskName = taskParts[0];
        let status = taskParts[1];
        
        if (status === "pending") {
            nextMaintenance = taskName;
            break; // Berhenti setelah menemukan tugas pending pertama
        }
    }
    
    return {
        summary: summary,
        spaceNeeded: spaceNeeded,
        nextMaintenance: nextMaintenance
    };
}
```

---

## 🔍 Penjelasan Detail

### 1. **Membuat Ringkasan Jadwal** 📝
Fungsi ini menggabungkan setiap jadwal dengan jumlah penontonnya dalam format string:
- Loop melalui array `schedules`
- Untuk setiap jadwal, tambahkan format: `NamaJadwal(JumlahPenonton)`
- Semua digabung menjadi satu string tanpa pemisah

### 2. **Menghitung Kebutuhan Ruang** 📐
Fungsi menghitung berapa banyak ruang yang dibutuhkan:
- Setiap penonton membutuhkan ruang 1.5x (mungkin untuk mempertimbangkan area berjalan, antrian, dll)
- Menggunakan `Math.floor()` untuk membulatkan ke bawah
- Semua hasil dijumlahkan untuk mendapat total kebutuhan ruang

### 3. **Mencari Tugas Perawatan** 🔧
Fungsi mencari tugas perawatan yang perlu dilakukan:
- Loop melalui array `tasks`
- Setiap task dipisah berdasarkan karakter `:` menjadi nama dan status
- Jika ditemukan status "pending", simpan nama tugasnya
- Hanya mengambil tugas pending **pertama** yang ditemukan

---

## 📚 Contoh Penggunaan

```javascript
// Data input
const schedules = ["Parade Pagi", "Show Siang", "Kembang Api Malam"];
const inventory = ["Balon", "Topi", "Mainan"];
const audienceCounts = [150, 300, 500];
const tasks = [
  "Cek Rollercoaster:completed",
  "Bersihkan Toilet:pending",
  "Perbaiki Lampu:pending"
];

// Memanggil fungsi
const result = planParkDay(schedules, inventory, audienceCounts, tasks);

console.log(result);
```

### 🎉 Output yang Dihasilkan:

```javascript
{
  summary: "Parade Pagi(150)Show Siang(300)Kembang Api Malam(500)",
  spaceNeeded: 1425,
  nextMaintenance: "Bersihkan Toilet"
}
```

### 📊 Penjelasan Output:

- **summary**: Menggabungkan semua jadwal dengan jumlah penontonnya
  - `"Parade Pagi(150)Show Siang(300)Kembang Api Malam(500)"`

- **spaceNeeded**: Total ruang yang dibutuhkan = 1425
  - Perhitungan: 
    - Parade Pagi: `Math.floor(150 × 1.5)` = 225
    - Show Siang: `Math.floor(300 × 1.5)` = 450
    - Kembang Api: `Math.floor(500 × 1.5)` = 750
    - **Total**: 225 + 450 + 750 = **1425**

- **nextMaintenance**: `"Bersihkan Toilet"`
  - Tugas pertama yang berstatus "pending"

---

## 📝 Contoh Lain

### Kasus: Tidak Ada Tugas Pending

```javascript
const schedules = ["Show Pagi"];
const inventory = [];
const audienceCounts = [100];
const tasks = [
  "Bersihkan Area:completed",
  "Cek Lampu:completed"
];

const result = planParkDay(schedules, inventory, audienceCounts, tasks);
console.log(result);
```

**Output:**
```javascript
{
  summary: "Show Pagi(100)",
  spaceNeeded: 150,
  nextMaintenance: ""  // String kosong karena tidak ada tugas pending
}
```

---

## ⚠️ Catatan Penting

1. **Parameter `inventory` tidak digunakan** dalam fungsi ini. Mungkin untuk pengembangan fitur di masa mendatang.

2. **Format string tasks** harus menggunakan format `"namaTugas:status"` dengan pemisah titik dua (`:`).

3. **Tidak ada pemisah** antara jadwal dalam summary. Jika ingin ada koma atau spasi, perlu modifikasi kode.

4. **Nilai `nextMaintenance`** akan menjadi **string kosong** (`""`) jika tidak ada tugas yang berstatus "pending".

5. **Panjang array `schedules` dan `audienceCounts`** sebaiknya sama untuk menghindari hasil yang tidak sesuai.

---

## 🚀 Tips Pengembangan

Beberapa saran untuk meningkatkan fungsi ini:

- Tambahkan pemisah (misalnya koma atau spasi) antara jadwal dalam summary
- Validasi input untuk memastikan array memiliki panjang yang sama
- Gunakan parameter `inventory` untuk fitur tambahan (misalnya cek ketersediaan barang)
- Tambahkan handling untuk format tasks yang tidak sesuai atau tidak memiliki titik dua
- Pertimbangkan untuk mengembalikan semua tugas pending dalam bentuk array
- Tambahkan error handling jika input tidak valid

---

**Dibuat dengan ❤️ untuk membantu pengelolaan taman hiburan**
