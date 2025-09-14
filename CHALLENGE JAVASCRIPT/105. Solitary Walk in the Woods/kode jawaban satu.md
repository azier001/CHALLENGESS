# 🚶‍♂️ Dokumentasi Fungsi `solitary_walk`

## 📋 Deskripsi

Fungsi `solitary_walk` adalah sebuah fungsi JavaScript yang mensimulasikan perjalanan dengan langkah-langkah yang dapat bernilai positif atau negatif. Fungsi ini akan berhenti ketika total langkah menjadi negatif (di bawah 0) dan mengembalikan total langkah yang telah ditempuh.

Fungsi ini berguna untuk simulasi perjalanan di mana setiap langkah memiliki nilai tertentu, dan perjalanan harus dihentikan jika total nilai langkah menjadi negatif.

## 🔧 Sintaks

```javascript
solitary_walk(steps)
```

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `steps` | `Array<number>` | Array berisi angka yang merepresentasikan nilai setiap langkah. Bisa positif atau negatif |

## 🔄 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `number` | Total langkah yang berhasil ditempuh sebelum berhenti |

## ⚙️ Cara Kerja

1. Fungsi dimulai dengan `total_steps = 0`
2. Iterasi melalui setiap langkah dalam array `steps`
3. Sebelum menambahkan langkah baru, periksa apakah `total_steps + steps[i] < 0`
4. Jika ya, hentikan loop dan kembalikan `total_steps` saat ini
5. Jika tidak, tambahkan nilai langkah ke `total_steps`
6. Lanjutkan hingga semua langkah selesai atau kondisi berhenti terpenuhi

## 💻 Code

```javascript
function solitary_walk(steps) {
  // Inisialisasi total langkah dengan nilai 0
  let total_steps = 0;
  
  // Loop melalui setiap langkah dalam array
  for (let i = 0; i < steps.length; i++) {
    // Cek apakah langkah selanjutnya akan membuat total menjadi negatif
    if (total_steps + steps[i] < 0) {
      // Jika ya, hentikan perjalanan
      break;
    }
    
    // Jika tidak, tambahkan langkah ke total
    total_steps += steps[i];
  }
  
  // Kembalikan total langkah yang berhasil ditempuh
  return total_steps;
}
```

## 🧪 Contoh Penggunaan

### Contoh 1: Perjalanan Normal
```javascript
const langkah1 = [1, 2, 3, 4, 5];
console.log(solitary_walk(langkah1)); 
// Output: 15
// Semua langkah berhasil ditempuh (1+2+3+4+5 = 15)
```

### Contoh 2: Perjalanan Terhenti
```javascript
const langkah2 = [2, 4, -3, 1, -5];
console.log(solitary_walk(langkah2)); 
// Output: 3
// Berhenti di langkah ke-4 karena 3 + (-5) = -2 < 0
// Urutan: 0 → 2 → 6 → 3 → (akan jadi -2, jadi berhenti)
```

### Contoh 3: Langkah Negatif di Awal
```javascript
const langkah3 = [-1, 5, 3];
console.log(solitary_walk(langkah3)); 
// Output: 0
// Berhenti langsung karena 0 + (-1) = -1 < 0
```

### Contoh 4: Array Kosong
```javascript
const langkah4 = [];
console.log(solitary_walk(langkah4)); 
// Output: 0
// Tidak ada langkah untuk ditempuh
```

## 📊 Tabel Hasil Contoh

| Input | Proses Langkah | Output | Keterangan |
|-------|----------------|--------|------------|
| `[1, 2, 3, 4, 5]` | 0→1→3→6→10→15 | `15` | Semua langkah berhasil |
| `[2, 4, -3, 1, -5]` | 0→2→6→3→(stop) | `3` | Berhenti sebelum -5 |
| `[-1, 5, 3]` | 0→(stop) | `0` | Berhenti di langkah pertama |
| `[]` | - | `0` | Array kosong |
| `[5, -2, 1, -4]` | 0→5→3→4→(stop) | `4` | Berhenti sebelum -4 |

## ⚠️ Catatan Penting

- Fungsi akan berhenti **sebelum** menambahkan langkah yang akan membuat total negatif
- Jika langkah pertama sudah negatif, fungsi langsung mengembalikan 0
- Array kosong akan mengembalikan 0
- Fungsi tidak memodifikasi array input (non-destructive)

## 🎯 Use Cases

1. **Simulasi Game**: Menghitung skor pemain yang tidak boleh negatif
2. **Manajemen Keuangan**: Tracking saldo yang tidak boleh minus
3. **Sistem Poin**: Akumulasi poin dengan penalty yang tidak boleh di bawah 0
4. **Simulasi Energi**: Tracking energi karakter dalam game
