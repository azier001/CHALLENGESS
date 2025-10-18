# 🌿 Tantangan Klasifikasi Umur Lumut

## 📋 Gambaran Umum

**Tingkat Kesulitan:** `Easy`

Sebagai fotografer alam yang menjelajahi hutan lebat, Anda menemukan berbagai batu yang ditumbuhi lumut. Tugas Anda adalah mengklasifikasikan lumut berdasarkan umurnya dengan mengimplementasikan sebuah function klasifikasi.

---

## 🎯 Deskripsi Tantangan

Buat sebuah function bernama **`classifyMoss`** yang menerima `mossAge` sebagai parameter dan mengembalikan string yang menjelaskan jenis lumut sesuai dengan klasifikasi umurnya.

---

## 📊 Aturan Klasifikasi

Lumut harus diklasifikasikan sesuai dengan rentang umur berikut:

| Rentang Umur (tahun) | Klasifikasi |
|-------------------|----------------|
| 0 - 5 | **Young Moss** |
| 6 - 20 | **Mature Moss** |
| 21 - 50 | **Old Moss** |
| 51 - 100 | **Ancient Moss** |
| Lebih dari 100 | **Legendary Moss** |

---

## 🔧 Spesifikasi Function

### Nama Function
```
classifyMoss
```

### Parameter
- **`mossAge`** (number): Integer yang merepresentasikan umur lumut dalam tahun.

### Return Value
- Sebuah **string** yang merepresentasikan klasifikasi lumut berdasarkan umurnya.

---

## 💡 Contoh Penggunaan

```javascript
classifyMoss(3);    // Returns: "Young Moss"
classifyMoss(15);   // Returns: "Mature Moss"
classifyMoss(35);   // Returns: "Old Moss"
classifyMoss(75);   // Returns: "Ancient Moss"
classifyMoss(150);  // Returns: "Legendary Moss"
```

---

## ✅ Checklist Implementasi

- [ ] Function menerima parameter `mossAge`
- [ ] Mengidentifikasi rentang umur 0-5 tahun dengan benar
- [ ] Mengidentifikasi rentang umur 6-20 tahun dengan benar
- [ ] Mengidentifikasi rentang umur 21-50 tahun dengan benar
- [ ] Mengidentifikasi rentang umur 51-100 tahun dengan benar
- [ ] Mengidentifikasi umur lebih dari 100 tahun dengan benar
- [ ] Mengembalikan string yang sesuai untuk setiap klasifikasi

---

## 🌲 Selamat Coding!

Semoga sukses dengan petualangan klasifikasi lumut Anda!
