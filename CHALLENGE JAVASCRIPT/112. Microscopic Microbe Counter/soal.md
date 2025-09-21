# 🔬 Penghitung Mikroba Mikroskopis

## Ikhtisar Challenge

**Level Kesulitan:** `Easy` 🟢

Buat sebuah function yang menghitung berbagai jenis mikroorganisme yang diamati di bawah mikroskop dan mengembalikan distribusi frekuensinya.

---

## 📋 Deskripsi Masalah

Tugas Anda adalah mengembangkan sebuah function bernama `microbeCounter` yang menganalisis sampel mikroskopis dan menyediakan data statistik tentang mikroba yang diamati.

### Spesifikasi Function

```javascript
function microbeCounter(sample) {
    // Implementasi Anda di sini
}
```

---

## 🔧 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `sample` | `Array<string>` | Array berisi string yang merepresentasikan mikroba yang diamati di bawah mikroskop |

---

## 📤 Return Value

Function harus mengembalikan sebuah **object** dengan karakteristik berikut:
- **Keys**: Nama mikroba yang unik (strings)
- **Values**: Jumlah setiap mikroba dalam sampel (integers)

---

## 💡 Contoh

### Input
```javascript
["amoeba", "paramecium", "amoeba", "euglena"]
```

### Output yang Diharapkan
```javascript
{
  "amoeba": 2,
  "paramecium": 1,
  "euglena": 1
}
```

### Representasi Visual
```
🦠 amoeba      ██ (2 kemunculan)
🦠 paramecium  █  (1 kemunculan)
🦠 euglena     █  (1 kemunculan)
```

---

## 🎯 Persyaratan Utama

- ✅ Function harus bernama `microbeCounter`
- ✅ Menerima satu parameter: `sample` (array)
- ✅ Mengembalikan object dengan jumlah mikroba
- ✅ Menangani nama mikroba duplikat dengan benar
- ✅ Mempertahankan format huruf nama mikroba asli

---

## 🧪 Test Cases

Pertimbangkan untuk menguji function Anda dengan berbagai skenario:

1. **Sample kosong**: `[]`
2. **Mikroba tunggal**: `["bacteria"]`
3. **Semua mikroba sama**: `["virus", "virus", "virus"]`
4. **Case sensitivity campuran**: `["Amoeba", "amoeba"]`
5. **Dataset besar**: Array dengan 100+ entri mikroba

---

## 🎨 Tips Implementasi

> 💡 **Hint**: Pertimbangkan menggunakan pola akses properti object dan metode iterasi untuk membangun solusi Anda secara efisien.

Selamat menganalisis mikroskopis! 🔬✨
