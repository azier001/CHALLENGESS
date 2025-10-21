# ✈️ Busy Day at the Airpark

## 🧩 Gambaran Umum Tantangan

**Tingkat Kesulitan:** Easy
**Nama Fungsi:** `airportTraffic`

Simulasikan **hari yang sibuk di airpark** dengan mengatur runway dan memproses berbagai aksi pilot.
Tujuan kamu adalah memperbarui kondisi runway berdasarkan aksi-aksi tersebut dan mengembalikan konfigurasi akhirnya.

---

## 📥 Parameter

### `runway` (Array)

* Merepresentasikan **kondisi awal** dari runway di airpark.
* Setiap elemen menunjukkan:

  * `0` → posisi kosong
  * `1` → sedang ditempati oleh pesawat

### `pilotActions` (Array)

* Daftar **aksi pilot** sepanjang hari.
* Setiap elemen berupa angka integer yang menggambarkan apa yang terjadi di runway.

---

## ⚙️ Aturan & Perilaku

Proses setiap aksi di `pilotActions` secara berurutan dan perbarui `runway` sesuai aturan berikut:

| Jenis Aksi  | Contoh | Arti                                      | Efek                          |
| ----------- | ------ | ----------------------------------------- | ----------------------------- |
| **Positif** | `2`    | Sebuah pesawat mendarat di posisi 2       | Ubah `runway[1]` dari `0 → 1` |
| **Negatif** | `-3`   | Sebuah pesawat lepas landas dari posisi 3 | Ubah `runway[2]` dari `1 → 0` |
| **Nol (0)** | `0`    | Tidak ada perubahan pada giliran ini      | Lewati aksi tersebut          |

> 🧠 **Catatan:**
>
> * Jika aksi **landing** mengarah ke posisi yang sudah terisi (`1`), **abaikan**.
> * Jika aksi **takeoff** mengarah ke posisi yang kosong (`0`), **abaikan**.
> * Posisi menggunakan **1-based index** (misalnya, `1` berarti elemen pertama).

---

## 🧾 Deskripsi Fungsi

```javascript
function airportTraffic(runway, pilotActions) {
  // kode kamu di sini
}
```

Fungsi ini harus:

1. Melakukan iterasi pada setiap aksi di `pilotActions`.
2. Memperbarui `runway` sesuai aturan di atas.
3. Mengembalikan **kondisi akhir** runway setelah semua aksi diproses.

---

## 💡 Contoh

### Input

```javascript
const runway = [0, 1, 0, 0];
const pilotActions = [1, -2, 3, 0, -4];
```

### Proses Langkah demi Langkah

| Langkah | Aksi | Kondisi Runway | Deskripsi                                    |
| ------- | ---- | -------------- | -------------------------------------------- |
| 1       | `1`  | `[1, 1, 0, 0]` | Pesawat mendarat di posisi 1                 |
| 2       | `-2` | `[1, 0, 0, 0]` | Pesawat lepas landas dari posisi 2           |
| 3       | `3`  | `[1, 0, 1, 0]` | Pesawat mendarat di posisi 3                 |
| 4       | `0`  | `[1, 0, 1, 0]` | Tidak ada perubahan                          |
| 5       | `-4` | `[1, 0, 1, 0]` | Tidak valid (posisi sudah kosong), diabaikan |

### Output

```javascript
[1, 0, 1, 0]
```

---

## 🏁 Output Akhir

Fungsi mengembalikan **kondisi akhir runway** dalam bentuk array setelah semua aksi pilot selesai diproses.

```javascript
return [/* updated runway */];
```

---

✨ **Tips:** Fokus pada penanganan aksi tidak valid dengan benar agar simulasi runway tetap akurat.
