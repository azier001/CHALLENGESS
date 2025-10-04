# 🔮 Fortune Teller Challenge

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang memprediksi apakah target number adalah lucky atau unlucky berdasarkan array of numbers.

---

## 🎯 Tujuan

Implementasikan function bernama `fortuneTeller` yang:
- Menerima **array of numbers** dan **target number**
- Memproses array menggunakan aturan tertentu
- Mengembalikan prediksi keberuntungan berdasarkan hasil

---

## 📝 Persyaratan

### Function Signature
```javascript
fortuneTeller(array, target)
```

### Parameter
| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `array` | `Array<number>` | Array berisi numbers untuk diproses |
| `target` | `number` | Target number untuk dibandingkan |

### Return Value
| Value | Tipe | Kondisi |
|-------|------|-----------|
| `"Lucky!"` | `string` | Ketika sum sama dengan target |
| `"Unlucky!"` | `string` | Ketika sum tidak sama dengan target |

---

## ⚙️ Langkah-langkah Algorithm

Ikuti langkah-langkah berikut untuk mengimplementasikan solusi:

1. **Inisialisasi** variable `sum` menjadi `0`

2. **Loop** melalui setiap number dalam array

3. **Untuk setiap number:**
   - ✅ Jika number tersebut **even** → **tambahkan** ke `sum`
   - ❌ Jika number tersebut **odd** → **kurangkan** dari `sum`

4. **Setelah loop:**
   - Bandingkan `sum` dengan `target`
   - Return `"Lucky!"` jika keduanya sama
   - Return `"Unlucky!"` jika keduanya tidak sama

---

## 📌 Catatan Penting

> **Array Kosong:** Jika input array kosong, anggap sum sebagai `0`.

> **Target Number:** Target bisa berupa integer apapun (positif, negatif, atau nol).

---

## 💡 Contoh

### Contoh 1: Prediksi Unlucky
```javascript
fortuneTeller([2, 3, 4, 5], 2)
// Proses: 2 (even) + (-3) (odd) + 4 (even) + (-5) (odd) = -2
// Expected: "Unlucky!"
```

### Contoh 2: Array Kosong
```javascript
fortuneTeller([], 0)
// Proses: sum = 0
// Expected: "Lucky!"
```

### Contoh 3: Semua Even Numbers
```javascript
fortuneTeller([2, 4, 6, 8], 20)
// Proses: 2 + 4 + 6 + 8 = 20
// Expected: "Lucky!"
```

---

## 🏆 Kriteria Keberhasilan

Solusi Anda harus:
- ✓ Menangani array kosong dengan benar
- ✓ Memproses even numbers dengan penambahan
- ✓ Memproses odd numbers dengan pengurangan
- ✓ Mengembalikan format string yang benar
- ✓ Bekerja dengan target positif, negatif, dan nol

---

**Semoga beruntung dengan fortune telling-mu! 🍀**
