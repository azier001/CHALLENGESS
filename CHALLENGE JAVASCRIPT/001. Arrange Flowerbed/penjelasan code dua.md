# 🌸 Dokumentasi Fungsi `arrangeFlowerbed`

## 📘 Deskripsi
Fungsi `arrangeFlowerbed` digunakan untuk menanam tanaman baru pada *flowerbed* (hamparan bunga) dengan aturan bahwa **setiap tanaman tidak boleh bersebelahan langsung**. Fungsi ini akan mencoba menanam sebanyak mungkin tanaman baru sesuai dengan jumlah yang diminta, dengan tetap mempertahankan jarak antar tanaman.

---

## 🧾 Signature Fungsi
```javascript
function arrangeFlowerbed(flowerbed, newPlants)
```

---

## 📥 Parameter
| Nama Parameter | Tipe     | Deskripsi                                                                 |
|----------------|----------|---------------------------------------------------------------------------|
| `flowerbed`    | Array    | Array berisi angka 0 (slot kosong) dan 1 (sudah ada tanaman)              |
| `newPlants`    | Number   | Jumlah tanaman baru yang ingin ditanam                                     |

---

## 📤 Return Value
- `Array`: Flowerbed yang telah dimodifikasi dengan tanaman baru yang berhasil ditanam.

---

## 🔍 Penjelasan Kode Baris per Baris

### ✅ Baris 1: Deklarasi Fungsi
```javascript
function arrangeFlowerbed(flowerbed, newPlants) {
```
Mendefinisikan fungsi `arrangeFlowerbed` dengan dua parameter utama.

### ✅ Baris 2: Inisialisasi Counter
```javascript
let count = 0;
```
Inisialisasi penghitung jumlah tanaman yang berhasil ditanam.

### ✅ Baris 3: Loop Utama
```javascript
for (let i = 0; i < flowerbed.length && count < newPlants; i++) {
```
Melakukan iterasi sepanjang `flowerbed`, berhenti jika jumlah `newPlants` telah tercapai.

### ✅ Baris 4-8: Kondisi Penanaman
```javascript
if (
  flowerbed[i] === 0 &&
  (i === 0 || flowerbed[i - 1] === 0) &&
  (i === flowerbed.length - 1 || flowerbed[i + 1] === 0)
) {
```
Memastikan slot sekarang, sebelumnya, dan sesudahnya aman untuk ditanami.

### ✅ Baris 9-10: Aksi Penanaman
```javascript
flowerbed[i] = 1;
count++;
```
Menanam tanaman dan memperbarui jumlah tanaman yang berhasil ditanam.

### ✅ Baris 13: Return
```javascript
return flowerbed;
```
Mengembalikan array `flowerbed` yang telah diperbarui.

---

## 💡 Contoh Penggunaan

### Contoh 1
```javascript
let flowerbed = [1, 0, 0, 0, 1];
let newPlants = 1;
let result = arrangeFlowerbed(flowerbed, newPlants);
console.log(result); // Output: [1, 0, 1, 0, 1]
```

### Contoh 2
```javascript
let flowerbed = [1, 0, 0, 0, 0, 1];
let newPlants = 2;
let result = arrangeFlowerbed(flowerbed, newPlants);
console.log(result); // Output: [1, 0, 1, 0, 1, 1]
```

---

## 🧠 Algoritma dan Kompleksitas

### Algoritma
- **Greedy Algorithm**: Menanam tanaman secepat mungkin pada slot yang valid.
- **Single Pass**: Hanya memerlukan satu kali iterasi.

### Kompleksitas
- **Time Complexity**: `O(n)` — n adalah panjang dari `flowerbed`.
- **Space Complexity**: `O(1)` — hanya menggunakan variabel tambahan kecil.

---

## ⚠️ Catatan Penting
1. Fungsi ini **memodifikasi array asli** (`flowerbed`)
2. Gunakan salinan array jika ingin mempertahankan data awal
3. Fungsi akan berhenti setelah menanam jumlah yang diminta meskipun ada slot kosong yang masih tersedia
