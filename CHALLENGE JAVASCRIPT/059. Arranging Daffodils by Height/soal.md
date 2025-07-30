# 🌼 Menyusun Daffodil Berdasarkan Tinggi

## 🎯 Gambaran Challenge
**Tingkat Kesulitan:** `Easy`

Pada pagi musim semi yang cerah, seorang tukang kebun sedang merawat deretan daffodil yang indah. Untuk menciptakan susunan yang rapi sempurna, tukang kebun perlu mengurutkan daffodil berdasarkan tingginya. Misi Anda adalah membantu tukang kebun mengorganisir pengukuran bunga-bunga ini dalam urutan ascending.

---

## 📋 Deskripsi Tugas

Buat sebuah function bernama **`arrangeDaffodils`** yang akan membantu mengurutkan tinggi daffodil dari yang terpendek hingga tertinggi.

### Function Signature
```javascript
function arrangeDaffodils(daffodilHeights) {
    // Implementasi Anda di sini
}
```

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `daffodilHeights` | `Array<number>` | Sebuah array berisi integer yang mewakili tinggi daffodil dalam sentimeter |

---

## 📤 Return Value

- **Tipe:** `Array<number>`
- **Deskripsi:** Sebuah array berisi integer yang mewakili tinggi daffodil yang sudah diurutkan secara ascending (terpendek ke tertinggi)

---

## 💡 Contoh

### Input:
```javascript
daffodilHeights = [15, 8, 23, 12, 19, 6, 21]
```

### Output yang Diharapkan:
```javascript
[6, 8, 12, 15, 19, 21, 23]
```

### Representasi Visual:
```
Sebelum: 🌼15  🌼8   🌼23  🌼12  🌼19  🌼6   🌼21
Sesudah: 🌼6   🌼8   🌼12  🌼15  🌼19  🌼21  🌼23
```

---

## ✅ Requirements

- ✨ Urutkan array secara **ascending** (terpendek ke tertinggi)
- 🔄 Return array yang sudah diurutkan
- 📏 Tinggi diukur dalam sentimeter
- 🌱 Handle array dengan panjang berapa pun (termasuk empty array)

---

## 🌟 Tips

> 💭 **Pikirkan tentang:** Method JavaScript built-in apa yang bisa membantu Anda mengurutkan array berisi angka?
> 
> ⚠️ **Ingat:** Method sort default JavaScript memperlakukan elemen sebagai string, jadi hati-hati saat mengurutkan angka!

---

*Happy coding! 🌼✨*
