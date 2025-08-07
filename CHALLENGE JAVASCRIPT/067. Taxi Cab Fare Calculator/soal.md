# 🚖 Challenge Kalkulator Tarif Taksi

## 📊 Level Challenge
**Mudah**

## 🎯 Tujuan
Buat function bernama `calculateCabFare` yang mensimulasikan meter taksi dengan menghitung total tarif berdasarkan jarak tempuh dan tarif dasar.

## 📋 Persyaratan Function

### Function Signature
```javascript
function calculateCabFare(distances, baseFare)
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `distances` | `array` | Array berisi integer yang merepresentasikan jarak dalam kilometer untuk setiap segmen perjalanan |
| `baseFare` | `number` | Integer yang merepresentasikan tarif dasar sebelum biaya berdasarkan jarak ditambahkan |

### Return Value
- **Type**: `integer`
- **Deskripsi**: Total tarif yang dihitung

## 🔄 Langkah-langkah Algorithm

Function harus melakukan operasi berikut secara berurutan:

1. **Reverse array distances** 
   - Ubah input array menjadi urutan terbalik

2. **Hitung total jarak**
   - Jumlahkan semua jarak dari array yang sudah di-reverse untuk mendapat total kilometer

3. **Terapkan pricing berdasarkan jarak**
   - Kalikan total jarak dengan **$10 per kilometer**

4. **Hitung tarif final**
   - Tambahkan tarif berdasarkan jarak ke tarif dasar

## 💡 Contoh Penggunaan

```javascript
// Contoh 1
const distances = [5, 3, 8, 2];
const baseFare = 15;
const totalFare = calculateCabFare(distances, baseFare);
// Expected: 15 + (5+3+8+2) * 10 = 15 + 180 = 195

// Contoh 2  
const distances = [10, 7];
const baseFare = 20;
const totalFare = calculateCabFare(distances, baseFare);
// Expected: 20 + (10+7) * 10 = 20 + 170 = 190
```

## 📝 Catatan Implementasi

- Pastikan array distances di-reverse **sebelum** menghitung sum
- Rate tetap **$10 per kilometer**
- Semua input berupa integer, dan return value harus integer
- Handle edge cases seperti empty array dengan tepat

## 🧪 Test Cases

Pertimbangkan untuk testing dengan:
- ✅ Case normal dengan multiple distances
- ✅ Single distance dalam array
- ✅ Empty distances array
- ✅ Zero base fare
- ✅ Large distance values

---

*Semoga berhasil dengan implementasinya! 🚀*
