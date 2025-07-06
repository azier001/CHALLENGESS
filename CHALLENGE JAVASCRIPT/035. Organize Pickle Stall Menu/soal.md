# 🥒 Challenge Organisasi Menu Warung Acar

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Bantu seorang pengunjung yang penasaran untuk mengorganisir dan menampilkan acar di pasar desa tradisional Bashkir dengan membuat function yang mengurutkan acar berdasarkan harga dan memformatnya menjadi tampilan menu yang indah.

---

## 🎯 Tujuan

Buat function bernama `organizePickleStall` yang menerima nama-nama acar dan harga yang sesuai, kemudian mengorganisirnya menjadi menu yang terformat dengan rapi dan diurutkan berdasarkan harga.

---

## 📝 Spesifikasi Function

### Nama Function
```javascript
organizePickleStall(pickleNames, prices)
```

### Parameter

| Parameter | Type | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `pickleNames` | `Array<string>` | Array berisi nama-nama acar | `['Cucumber', 'Tomato', 'Cabbage']` |
| `prices` | `Array<number>` | Array berisi harga yang sesuai | `[2.5, 3.0, 1.8]` |

### Return Value
- **Type:** `string`
- **Deskripsi:** String menu terformat dengan header, item acar yang diurutkan, dan footer

---

## 🔧 Persyaratan

Function harus melakukan operasi berikut:

1. **Urutkan acar berdasarkan harga** secara ascending (dari rendah ke tinggi)
2. **Pertahankan pasangan** antara nama acar dan harganya selama pengurutan
3. **Buat menu terformat** dengan setiap acar dan harga pada baris baru
4. **Tambahkan header dan footer** untuk menciptakan tampilan menu yang proper

---

## 📊 Perilaku yang Diharapkan

### Contoh Input
```javascript
pickleNames = ['Cucumber', 'Tomato', 'Cabbage']
prices = [2.5, 3.0, 1.8]
```

### Struktur Output yang Diharapkan
```
[Header]
Cabbage - $1.8
Cucumber - $2.5
Tomato - $3.0
[Footer]
```

---

## ⚠️ Catatan Penting

- **Data Integrity:** Pastikan nama acar dan harga tetap terpasang dengan benar setelah pengurutan
- **Formatting:** Buat menu yang menarik secara visual dengan struktur yang proper
- **Sorting:** Selalu urutkan secara ascending (termurah dulu)
- **String Output:** Return single string yang terformat dengan baik

---

## 🏷️ Tags

`Array Manipulation` `Sorting` `String Formatting` `Data Pairing` `Market Simulation`
