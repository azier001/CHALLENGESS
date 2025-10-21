# 🛫 **Fungsi: `airportTraffic`**

## 📖 Deskripsi

Fungsi **`airportTraffic`** digunakan untuk mensimulasikan lalu lintas pesawat di landasan pacu (*runway*) pada bandara kecil.
Fungsi ini memproses daftar aksi pilot yang akan **menambah (mendarat)** atau **menghapus (lepas landas)** pesawat dari posisi tertentu di landasan pacu.

Tujuan utama fungsi ini adalah untuk mengembalikan kondisi akhir landasan pacu setelah semua aksi pilot diproses.

---

## ⚙️ **Struktur Kode**

```javascript
// Fungsi untuk mensimulasikan aktivitas di landasan pacu
function airportTraffic(runway, pilotActions) {
  
  // Loop untuk memproses setiap aksi dari pilot
  for (let action of pilotActions) {

    // Jika nilai action positif dan posisi masih kosong (0), pesawat mendarat
    if (action > 0 && runway[action - 1] === 0) {
      runway[action - 1] = 1;
    } 
    // Jika nilai action negatif dan posisi sedang terisi (1), pesawat lepas landas
    else if (action < 0 && runway[Math.abs(action) - 1] === 1) {
      runway[Math.abs(action) - 1] = 0;
    }
  }

  // Kembalikan kondisi akhir runway setelah semua aksi selesai
  return runway;
}
```

---

## 🧩 **Parameter Fungsi**

| Parameter      | Tipe Data | Deskripsi                                                                                                                              |
| -------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `runway`       | `array`   | Representasi kondisi awal landasan pacu. Nilai `0` menunjukkan posisi kosong dan `1` menunjukkan posisi yang sedang ditempati pesawat. |
| `pilotActions` | `array`   | Daftar aksi pilot. Nilai positif menandakan pesawat mendarat, sedangkan nilai negatif menandakan pesawat lepas landas.                 |

---

## 🧮 **Penjelasan Logika Sederhana**

| Nilai `action` | Arti                                      | Efek pada Runway                           |       |                                            |
| -------------- | ----------------------------------------- | ------------------------------------------ | ----- | ------------------------------------------ |
| `> 0`          | Pesawat mendarat di posisi `(action - 1)` | Jika posisi kosong (`0`), ubah menjadi `1` |       |                                            |
| `< 0`          | Pesawat lepas landas dari posisi `(       | action                                     | - 1)` | Jika posisi terisi (`1`), ubah menjadi `0` |

---

## 🧠 **Cara Kerja Singkat**

1. Loop melalui setiap aksi dalam `pilotActions`.
2. Jika aksi bernilai positif (`> 0`), pesawat mendarat di posisi tersebut bila kosong.
3. Jika aksi bernilai negatif (`< 0`), pesawat lepas landas dari posisi tersebut bila terisi.
4. Setelah semua aksi selesai diproses, fungsi mengembalikan kondisi akhir `runway`.

---

## 💡 **Contoh Penggunaan**

```javascript
const runway = [0, 1, 0, 0];
const pilotActions = [1, -2, 3, -3, 2];

const result = airportTraffic(runway, pilotActions);
console.log(result);
```

### 🧾 **Proses Langkah Demi Langkah:**

1. `action = 1` ⟶ Pesawat mendarat di indeks 0 → `[1, 1, 0, 0]`
2. `action = -2` ⟶ Pesawat lepas landas di indeks 1 → `[1, 0, 0, 0]`
3. `action = 3` ⟶ Pesawat mendarat di indeks 2 → `[1, 0, 1, 0]`
4. `action = -3` ⟶ Pesawat lepas landas di indeks 2 → `[1, 0, 0, 0]`
5. `action = 2` ⟶ Pesawat mendarat di indeks 1 → `[1, 1, 0, 0]`

✅ **Output akhir:**

```javascript
[1, 1, 0, 0]
```

---

## 🧭 **Kesimpulan**

Fungsi `airportTraffic` memungkinkan kita mensimulasikan perubahan kondisi landasan pacu dengan cara sederhana namun efektif.
Logika berbasis angka positif dan negatif memudahkan pemula memahami proses **mendarat (1)** dan **lepas landas (0)** pada sistem berbasis array.

> ✈️ **Intinya:** Nilai positif = pesawat mendarat 🛬, Nilai negatif = pesawat lepas landas 🛫.
