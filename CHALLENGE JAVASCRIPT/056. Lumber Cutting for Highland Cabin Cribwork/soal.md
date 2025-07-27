# 🏔️ Pemotongan Kayu untuk Highland Cabin Cribwork

## 🎯 Ringkasan Challenge
**Tingkat Kesulitan:** `Easy`

Selamat datang di Scottish Highlands! Sebagai tukang kayu berpengalaman yang mengerjakan proyek konstruksi cabin rustic, Anda akan mempersiapkan kayu untuk cribwork (kerangka) cabin. Misi Anda adalah memotong kayu yang tersedia menjadi panjang standar sambil meminimalkan waste.

---

## 📋 Deskripsi Tugas

Buatlah function bernama `cutLumberForCabin` yang memproses potongan kayu secara efisien untuk konstruksi.

### 🔧 Function Signature
```javascript
function cutLumberForCabin(availableLumber, standardLength)
```

### 📥 Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `availableLumber` | `Array<number>` | Array berisi angka yang merepresentasikan panjang potongan kayu dalam feet |
| `standardLength` | `number` | Panjang standar yang dibutuhkan untuk cribwork dalam feet |

### 📤 Return Value
- **Type:** `Array<number>`
- **Deskripsi:** Array yang berisi panjang semua potongan kayu yang telah diproses

---

## 🛠️ Aturan Pemrosesan

Pemotongan kayu mengikuti pedoman berikut:

1. **Pemotongan Standar:** Jika potongan kayu **lebih panjang atau sama dengan** panjang standar, potong menjadi sebanyak mungkin potongan dengan panjang standar
2. **Pertahankan Potongan Pendek:** Jika potongan kayu **lebih pendek dari** panjang standar, biarkan apa adanya (tidak perlu dipotong)
3. **Minimalkan Waste:** Fokus untuk mendapatkan jumlah maksimum potongan standar dari setiap kayu

---

## 💡 Contoh Walkthrough

### Input:
- `availableLumber`: `[10, 15, 8]`
- `standardLength`: `5`

### Pemrosesan:
| Panjang Asli | Aksi | Hasil Potongan |
|-------------|------|----------------|
| 10 feet | Potong menjadi potongan standar | `[5, 5]` |
| 15 feet | Potong menjadi potongan standar | `[5, 5, 5]` |
| 8 feet | Biarkan apa adanya (< standar) | `[8]` |

### Output:
```javascript
[5, 5, 5, 5, 5, 8]
```

---

## 🎯 Panduan Implementasi

- ✅ Gunakan basic array methods dan loops
- ✅ Fokus pada konsep programming fundamental
- ❌ Hindari advanced functions atau methods yang kompleks
- ❌ Tidak memerlukan external libraries

---

## 🧠 Tips untuk Sukses

1. **Loop Setiap Potongan:** Proses setiap potongan kayu secara individual
2. **Hitung Potongan:** Tentukan berapa banyak potongan standar yang bisa dipotong dari setiap kayu
3. **Tangani Remainders:** Pertimbangkan apa yang harus dilakukan dengan potongan yang lebih pendek dari panjang standar
4. **Bangun Result Array:** Kumpulkan semua potongan yang telah diproses ke dalam array final

---

## 🏗️ Memulai

Pikirkan tentang:
- Bagaimana cara melakukan iterasi melalui available lumber array
- Bagaimana menentukan jumlah potongan yang mungkin untuk setiap piece
- Bagaimana menambahkan resulting pieces ke output array Anda
- Kapan harus mempertahankan pieces yang terlalu pendek untuk dipotong

Semoga berhasil dengan proyek Highland cabin Anda! 🏕️
