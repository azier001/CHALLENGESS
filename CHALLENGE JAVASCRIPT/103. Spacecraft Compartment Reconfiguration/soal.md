# 🚀 Rekonfigurasi Kompartemen Spacecraft

## Gambaran Challenge

**Tingkat Kesulitan:** `Easy` ⭐

Buat sebuah function yang mensimulasikan rekonfigurasi kompartemen spacecraft vintage dengan menambahkan custom spacer di antara kompartemen untuk meningkatkan performa dan kompatibilitas.

---

## 📋 Deskripsi Problem

Misi Anda adalah mengembangkan function bernama `reconfigureSpacecraft` yang mengambil data kompartemen spacecraft dan menyisipkan spacer di antara kompartemen untuk konfigurasi yang optimal.

### Function Signature
```javascript
function reconfigureSpacecraft(compartmentSizes, spacerSize)
```

---

## 🎯 Tujuan

Transform array ukuran kompartemen dengan menyisipkan spacer di antara setiap kompartemen, menciptakan layout spacecraft yang terkonfigurasi ulang untuk meningkatkan performa dan kompatibilitas dengan custom spacer baru.

---

## 📝 Langkah-langkah Algorithm

Ikuti langkah-langkah tepat berikut untuk merekonfigurasi spacecraft:

1. **Initialize** - Buat array kosong baru bernama `reconfiguredSizes` untuk menyimpan hasil
2. **Iterate** - Loop melalui setiap ukuran kompartemen dalam input array
3. **Process Setiap Kompartemen**:
   - ✅ Append ukuran kompartemen saat ini ke `reconfiguredSizes`
   - ✅ Jika bukan kompartemen terakhir, append `spacerSize` juga
4. **Return** - Output array `reconfiguredSizes` dengan spacer yang telah disisipkan

---

## 📊 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `compartmentSizes` | `Array<number>` | Array integer yang merepresentasikan ukuran kompartemen spacecraft |
| `spacerSize` | `number` | Integer yang merepresentasikan ukuran spacer untuk disisipkan antar kompartemen |

---

## 📤 Return Value

**Type:** `Array<number>`

**Deskripsi:** Array integer yang merepresentasikan ukuran kompartemen yang telah dikonfigurasi ulang dengan spacer ditambahkan di antara setiap kompartemen original.

---

## 💡 Contoh

### Input:
```javascript
compartmentSizes = [10, 20, 15, 30]
spacerSize = 5
```

### Expected Output:
```javascript
[10, 5, 20, 5, 15, 5, 30]
```

### Representasi Visual:
```
Original:     [10] [20] [15] [30]
                   ↓
Reconfigured: [10] [5] [20] [5] [15] [5] [30]
```

---

## 🎨 Tips Implementasi

- Gunakan method array seperti `push()` atau spread operator untuk menambahkan elemen
- Pertimbangkan menggunakan loop dengan tracking index untuk mengidentifikasi elemen terakhir
- Ingat: tidak ada spacer yang harus ditambahkan setelah kompartemen terakhir

---

## 🧪 Test Cases

Pertimbangkan untuk menguji function Anda dengan skenario berikut:

- **Single kompartemen:** `[100]` → `[100]`
- **Dua kompartemen:** `[10, 20]` → `[10, 5, 20]` (asumsi spacerSize = 5)
- **Empty array:** `[]` → `[]`
- **Spacer besar:** Test dengan ukuran spacer yang lebih besar dari ukuran kompartemen

---

*Semoga berhasil dengan misi rekonfigurasi spacecraft Anda! 🚀✨*
