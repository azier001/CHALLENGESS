# 🌋 Interdigitating Nature's Patterns

## Ringkasan Challenge

**Level Kesulitan:** `Medium` 🟡

Challenge ini mensimulasikan fenomena alam yang menarik yaitu **interdigitation**, di mana dua lapisan geologis yang berbeda saling terjalin membentuk struktur yang menyatu. Tugas Anda adalah membuat fungsi yang menjalin dua array string bersama-sama, merepresentasikan lapisan batuan yang berbeda, menjadi satu pola yang terjalin.

---

## 📋 Deskripsi Challenge

Buat sebuah fungsi bernama `interdigitate` yang menerima dua parameter dan menghasilkan pola elemen yang bergantian dari kedua array input.

### Function Signature

```javascript
function interdigitate(strata1, strata2)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `strata1` | `Array<string>` | Sebuah array string yang merepresentasikan lapisan batuan pertama |
| `strata2` | `Array<string>` | Sebuah array string yang merepresentasikan lapisan batuan kedua |

### Return Value

- **Tipe:** `Array<string>`
- **Deskripsi:** Sebuah array yang merepresentasikan lapisan yang terjalin dengan elemen bergantian antara `strata1` dan `strata2`

---

## 🎯 Objektif

Manipulasi array input dan kontrol alur program untuk membuat array yang terjalin di mana elemen dari kedua array input ditenun dalam pola yang bergantian.

---

## 🔧 Strategi Implementasi

Ikuti pendekatan step-by-step berikut untuk menyelesaikan challenge ini:

### Step 1: Inisialisasi Result Array
Buat array kosong bernama `interdigitated` untuk menyimpan elemen yang terjalin.

### Step 2: Tentukan Maximum Length
Temukan panjang maksimum di antara kedua array input menggunakan `Math.max()` dan simpan dalam variabel bernama `maxLength`.

### Step 3: Iterasi dan Jalin
Loop dari `0` hingga `maxLength - 1` menggunakan variabel loop `i`:

- **Kondisi 1:** Jika `i` kurang dari panjang `strata1`
  - Tambahkan elemen pada index `i` dari `strata1` ke array `interdigitated`
  
- **Kondisi 2:** Jika `i` kurang dari panjang `strata2`
  - Tambahkan elemen pada index `i` dari `strata2` ke array `interdigitated`

### Step 4: Return Hasilnya
Setelah loop selesai, return array `interdigitated`.

---

## 💡 Visualisasi Contoh

```
Input:
strata1 = ["A", "B", "C"]
strata2 = ["1", "2", "3", "4"]

Proses:
i=0: Tambah "A" dari strata1, Tambah "1" dari strata2 → ["A", "1"]
i=1: Tambah "B" dari strata1, Tambah "2" dari strata2 → ["A", "1", "B", "2"]
i=2: Tambah "C" dari strata1, Tambah "3" dari strata2 → ["A", "1", "B", "2", "C", "3"]
i=3: Skip strata1 (out of bounds), Tambah "4" dari strata2 → ["A", "1", "B", "2", "C", "3", "4"]

Output:
["A", "1", "B", "2", "C", "3", "4"]
```

---

## ⚡ Pertimbangan Penting

- Handle array dengan **panjang berbeda** dengan baik
- Pertahankan **urutan bergantian** (strata1 dulu, kemudian strata2)
- Gunakan **pengecekan kondisional** untuk menghindari error index out of bounds
- Fungsi harus bekerja dengan **panjang array apapun**, termasuk array kosong

---

## 🧪 Testing Solusi Anda

Pertimbangkan untuk testing dengan skenario berikut:

- ✅ Array dengan panjang sama
- ✅ Array dengan panjang berbeda
- ✅ Array kosong
- ✅ Array dengan satu elemen
- ✅ Satu array kosong, satu array berisi elemen

---

## 🎓 Learning Outcomes

Dengan menyelesaikan challenge ini, Anda akan berlatih:

- Teknik manipulasi array
- Struktur kontrol loop
- Logika kondisional
- Handling edge case dengan array yang memiliki panjang bervariasi

---

> **Hint:** Pikirkan bagaimana proses geologis alami menciptakan pola yang terjalin ini selama jutaan tahun. Kode Anda meniru fenomena alam yang indah ini! 🪨✨
