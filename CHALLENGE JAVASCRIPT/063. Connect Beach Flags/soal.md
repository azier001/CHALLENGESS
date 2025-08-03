# 🏖️ Challenge Connect Beach Flags

## 📋 Gambaran Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function bernama `connectBeachFlags` yang menghubungkan array beach flags menjadi satu string, mensimulasikan flags yang diikat bersama di pantai saat hari berangin.

---

## 🎯 Tujuan

Tugas Anda adalah menghubungkan semua beach flags sesuai urutan kemunculannya dalam array, menggunakan string `"--"` sebagai penghubung antara setiap flag.

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
connectBeachFlags(flags)
```

### Parameter
- **`flags`** *(string-array)*: Array berisi string dimana setiap string merepresentasikan sebuah beach flag

### Return Value
- **Type:** `string`
- **Deskripsi:** String yang merepresentasikan semua beach flags yang terhubung bersama sesuai urutan, dipisahkan dengan `"--"`

---

## 💡 Contoh

| Input | Output |
|-------|--------|
| `["red", "blue", "green"]` | `"red--blue--green"` |
| `["yellow", "red"]` | `"yellow--red"` |
| `["pink"]` | `"pink"` |

### Penjelasan Contoh

```javascript
// Multiple flags
connectBeachFlags(["red", "blue", "green"])
// Result: "red--blue--green"

// Two flags
connectBeachFlags(["yellow", "red"])
// Result: "yellow--red"

// Single flag
connectBeachFlags(["pink"])
// Result: "pink"
```

---

## 🛠️ Pendekatan Implementasi

Untuk menyelesaikan challenge ini, Anda dapat menggunakan:

- Teknik **manipulasi array**
- Method **string concatenation**
- **Iterasi** melalui array flags

### Pertimbangan Penting

> ⚠️ **Penting:** Tangani kasus khusus ketika hanya ada satu flag dalam array (tidak perlu connector)

---

## 🎨 Representasi Visual

```
Input:  ["red", "blue", "green"]
        
Process: red + "--" + blue + "--" + green

Output: "red--blue--green"
```

---

## 🏁 Kriteria Berhasil

Function Anda harus:
- ✅ Menghubungkan semua flags dalam urutan yang benar
- ✅ Menggunakan `"--"` sebagai string penghubung
- ✅ Menangani array dengan single flag dengan benar
- ✅ Mengembalikan string yang terformat dengan benar
