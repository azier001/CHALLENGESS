# 🛫 **Fungsi: `airportTraffic`**

## 🔖 Deskripsi

Fungsi **`airportTraffic`** digunakan untuk mensimulasikan aktivitas di landasan pacu (*runway*) pada sebuah bandara kecil (airpark).
Fungsi ini memproses daftar aksi pilot yang akan **menambah atau mengurangi pesawat** di posisi tertentu pada landasan pacu.

Tujuannya adalah untuk memperbarui kondisi akhir landasan pacu setelah semua aksi pilot selesai diproses.

---

## ⚙️ **Struktur Kode**

```javascript
// Fungsi untuk mensimulasikan lalu lintas bandara
function airportTraffic(runway, pilotActions) {
  
  // Loop untuk memproses setiap aksi pilot
  for (let action of pilotActions) {

    // Jika aksi bernilai 0, tidak ada perubahan (skip)
    if (action === 0) continue;

    // Hitung indeks runway berdasarkan aksi pilot
    const index = Math.abs(action) - 1;

    // Jika aksi positif dan posisi runway kosong, tambahkan pesawat (1)
    if (action > 0 && runway[index] === 0) {
      runway[index] = 1;
    }
    // Jika aksi negatif dan posisi runway terisi, hapus pesawat (0)
    else if (action < 0 && runway[index] === 1) {
      runway[index] = 0;
    }
  }

  // Kembalikan kondisi akhir runway setelah semua aksi selesai
  return runway;
}
```

---

## 🧩 **Parameter Fungsi**

| Parameter      | Tipe Data | Deskripsi                                                                                                                                                                                                   |
| -------------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `runway`       | `array`   | Representasi awal kondisi landasan pacu. Setiap elemen bernilai `0` (kosong) atau `1` (terisi pesawat).                                                                                                     |
| `pilotActions` | `array`   | Daftar aksi pilot yang harus diproses. Nilai positif berarti pesawat **mendarat (menambah)** di posisi tertentu, sedangkan nilai negatif berarti pesawat **lepas landas (menghapus)** dari posisi tersebut. |

---

## 🧮 **Penjelasan Logika Sederhana**

| Nilai `action` | Arti                                      | Efek pada Runway                           |       |                                            |
| -------------- | ----------------------------------------- | ------------------------------------------ | ----- | ------------------------------------------ |
| `0`            | Tidak ada aksi                            | Tidak mengubah apapun                      |       |                                            |
| `> 0`          | Pesawat mendarat di posisi `(action - 1)` | Jika posisi kosong (`0`), ubah menjadi `1` |       |                                            |
| `< 0`          | Pesawat lepas landas dari posisi `(       | action                                     | - 1)` | Jika posisi terisi (`1`), ubah menjadi `0` |

---

## 🧠 **Cara Kerja Singkat**

1. Loop melalui setiap elemen `pilotActions`.
2. Abaikan nilai `0` karena tidak ada perubahan.
3. Gunakan nilai absolut `Math.abs(action) - 1` untuk menentukan posisi di runway.
4. Jika `action > 0`, isi posisi tersebut (pesawat mendarat).
5. Jika `action < 0`, kosongkan posisi tersebut (pesawat lepas landas).
6. Setelah semua aksi diproses, fungsi mengembalikan kondisi akhir dari `runway`.

---

## 💡 **Contoh Penggunaan**

```javascript
const runway = [0, 1, 0, 0];
const pilotActions = [1, -2, 3, 0, -3];

const result = airportTraffic(runway, pilotActions);
console.log(result);
```

### 🧾 **Proses Langkah Demi Langkah:**

1. `action = 1` ⟶ Pesawat mendarat di indeks 0 → `[1, 1, 0, 0]`
2. `action = -2` ⟶ Pesawat lepas landas di indeks 1 → `[1, 0, 0, 0]`
3. `action = 3` ⟶ Pesawat mendarat di indeks 2 → `[1, 0, 1, 0]`
4. `action = 0` ⟶ Tidak ada perubahan → `[1, 0, 1, 0]`
5. `action = -3` ⟶ Pesawat lepas landas di indeks 2 → `[1, 0, 0, 0]`

✅ **Output akhir:**

```javascript
[1, 0, 0, 0]
```

---

## 🧭 **Kesimpulan**

Fungsi `airportTraffic` sangat berguna untuk mensimulasikan kondisi lalu lintas pesawat secara sederhana di sebuah bandara.
Dengan konsep logika dasar menggunakan angka positif dan negatif, fungsi ini mudah dipahami bahkan oleh pemula dalam pemrograman.

> ✈️ **Intinya:** Aksi positif = mendarat 🛬, Aksi negatif = lepas landas 🛫, Aksi nol = diam di tempat.
