
# 🌸 Penjelasan Fungsi `arrangeFlowerbed` 

## 📌 Deskripsi Fungsi
Fungsi `arrangeFlowerbed` adalah algoritma **greedy** yang digunakan untuk menanam bunga pada sebuah hamparan (`flowerbed`) dengan **aturan penting**:
> **Tidak boleh ada dua bunga yang bersebelahan.**

Fungsi ini mencoba menanam **sebanyak mungkin** bunga baru pada slot kosong.

---

## 📥 Parameter
| Nama       | Tipe    | Deskripsi |
|------------|---------|-----------|
| `flowerbed`| `Array` | Representasi hamparan (0 = kosong, 1 = ada bunga) |
| `newPlants`| `Number`| Jumlah tanaman baru yang ingin ditanam |

---

## 🔍 Penjelasan Kode Baris per Baris

### 1. Deklarasi Fungsi
```js
function arrangeFlowerbed(flowerbed, newPlants) {
```
📌 Membuat fungsi `arrangeFlowerbed` dengan 2 parameter: array dan jumlah tanaman.

---

### 2. Inisialisasi Indeks
```js
let i = 0;
```
🔁 `i` sebagai index loop, mulai dari elemen pertama.

---

### 3. Perulangan Utama
```js
while (i < flowerbed.length && newPlants > 0) {
```
📌 Loop terus berjalan selama masih ada slot kosong **dan** bunga yang harus ditanam.

---

### 4. Cek Slot Kosong
```js
if (flowerbed[i] === 0) {
```
✅ Slot saat ini kosong → bisa jadi kandidat untuk ditanami.

---

### 5. Cek Slot Sebelumnya
```js
const prevEmpty = i === 0 || flowerbed[i - 1] === 0;
```
🧐 Slot sebelumnya aman jika:
- Ini adalah slot pertama, atau
- Slot sebelumnya juga kosong

---

### 6. Cek Slot Setelahnya
```js
const nextEmpty = i === flowerbed.length - 1 || flowerbed[i + 1] === 0;
```
🧐 Slot sesudahnya aman jika:
- Ini adalah slot terakhir, atau
- Slot sesudahnya kosong

---

### 7. Validasi Aman Tanam
```js
if (prevEmpty && nextEmpty) {
```
🌼 Hanya tanam jika **kedua sisi** aman.

---

### 8. Tanam Bunga & Update Counter
```js
flowerbed[i] = 1;
newPlants--;
i++;
```
🌱 Tanam bunga → kurangi `newPlants` → lompat satu slot (agar tidak bersebelahan).

---

### 9. Lanjut ke Slot Berikutnya (Jika Tidak Menanam)
```js
i++;
```

---

### 10. Return Hasil
```js
return flowerbed;
```
🔁 Mengembalikan array yang telah dimodifikasi.

---

## ✅ Contoh Eksekusi

### Input:
```js
flowerbed = [1, 0, 0, 0, 1]
newPlants = 1
```

### Proses:
1. `i=0` → Ada bunga → lanjut
2. `i=1` → Tetangga kiri ada bunga → skip
3. `i=2` → Tetangga aman → 🌼 tanam bunga
4. `newPlants=0` → Selesai

### Output:
```js
[1, 0, 1, 0, 1]
```

---

## 💡 Keuntungan Algoritma

- ⚡ **Efisien**: Time complexity O(n)
- 🌱 **Greedy**: Menanam secepat mungkin
- 🧠 **Optimal**: Maksimalkan penanaman yang valid
- 🔄 **In-place**: Tidak butuh array tambahan

---

## ⚠️ Catatan Tambahan

- Fungsi **mengubah array secara langsung** (`in-place`)
- Strategi **melewati slot setelah menanam** memastikan efisiensi dan validitas

---

> 💬 "Strategi sederhana, hasil optimal – tanam bunga tanpa konflik!" 🌼
