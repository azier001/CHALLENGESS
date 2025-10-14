# 🚗 Road Trip Statistics Calculator

> **Tingkat Kesulitan:** `Easy` | **Topik:** Manipulasi Array & Statistik

---

## 📋 Deskripsi Challenge

Buat sebuah function bernama `calculateTripStats` yang menganalisis perjalanan lintas negara melintasi berbagai lanskap Amerika. Function Anda akan menghitung berbagai statistik berdasarkan data jarak tempuh harian.

---

## 🎯 Tujuan

Analisis array dari jarak tempuh harian dan hitung statistik perjalanan yang komprehensif termasuk total, rata-rata, dan nilai ekstrem.

---

## 📊 Statistik yang Diperlukan

Function Anda harus menghitung dan mengembalikan informasi berikut:

- **Total Miles** - Jumlah keseluruhan mil yang ditempuh selama perjalanan
- **Average Miles** - Rata-rata mil yang ditempuh per hari
- **Maximum Day** - Hari ketika Anda menempuh jarak paling jauh *(index berbasis 0)*
- **Minimum Day** - Hari ketika Anda menempuh jarak paling pendek *(index berbasis 0)*
- **Trip Duration** - Total jumlah hari perjalanan berlangsung

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
calculateTripStats
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `dailyMiles` | `array` | Sebuah array berisi angka yang merepresentasikan mil yang ditempuh setiap hari perjalanan |

### Return Value

**Tipe:** `Object`

Function mengembalikan sebuah object yang berisi semua statistik yang telah dihitung.

---

## ⚠️ Batasan Penting

> **Catatan:** Jangan gunakan built-in method seperti `Math.max()` atau `Math.min()`. 
> 
> Gunakan **iterasi array dasar** dan **operasi perbandingan** untuk menemukan nilai maksimum dan minimum.

---

## 💡 Tips Implementasi

- Gunakan loop untuk iterasi melalui array
- Catat running total untuk kalkulasi jumlah
- Bandingkan nilai secara manual untuk menemukan max/min
- Simpan index saat menemukan nilai ekstrem
- Hitung rata-rata setelah menentukan total

---

## 🚀 Memulai

Mulai dengan mendefinisikan struktur function Anda:

```javascript
function calculateTripStats(dailyMiles) {
  // Implementasi Anda di sini
}
```

Selamat coding! 🛣️
