# 🌱 Garden Label Formatter

## Tingkat Kesulitan Challenge
**Easy** ⭐

---

## 📋 Gambaran Umum

Buat sebuah function bernama `createGardenLabel` yang menghasilkan label terformat untuk tanaman. Function ini menerima informasi tentang tanaman dan mengembalikan string label yang terformat dengan rapi.

---

## 🎯 Deskripsi Challenge

Tugas Anda adalah mengimplementasikan function yang menerima tiga parameter tentang tanaman dan mengembalikan string label yang terformat.

### Function Signature
```javascript
createGardenLabel(plantName, plantAge, isFlowering)
```

---

## 📝 Format Label

Function harus menghasilkan label dalam format berikut:

```
Plant: [plantName], Age: [plantAge] years, Flowering: [yes/no]
```

### Aturan Format:
- **`[plantName]`** - Ganti dengan nama tanaman
- **`[plantAge]`** - Ganti dengan umur tanaman dalam tahun
- **`[yes/no]`** - Ganti dengan:
  - `"yes"` jika `isFlowering` bernilai `true`
  - `"no"` jika `isFlowering` bernilai `false`

---

## 💡 Contoh

### Contoh 1:
```javascript
createGardenLabel("Rose", 3, true)
// Output: "Plant: Rose, Age: 3 years, Flowering: yes"
```

### Contoh 2:
```javascript
createGardenLabel("Cactus", 5, false)
// Output: "Plant: Cactus, Age: 5 years, Flowering: no"
```

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `plantName` | `string` | Nama tanaman |
| `plantAge` | `number` | Umur tanaman dalam tahun (bilangan bulat positif) |
| `isFlowering` | `boolean` | Menunjukkan apakah tanaman sedang berbunga |

---

## 📤 Return Value

**Tipe:** `string`

**Deskripsi:** String label taman yang terformat berisi informasi tanaman.

---

## ✅ Checklist Persyaratan

- [ ] Function diberi nama `createGardenLabel`
- [ ] Menerima tiga parameter: `plantName`, `plantAge`, `isFlowering`
- [ ] Mengembalikan string dengan format yang benar
- [ ] Mengkonversi boolean ke "yes"/"no" dengan benar
- [ ] Menyertakan spasi dan tanda baca yang tepat

---

## 🚀 Memulai

Mulailah dengan mendefinisikan function Anda dan membangun string label secara bertahap. Ingat untuk menangani konversi boolean untuk status berbunga!

```javascript
function createGardenLabel(plantName, plantAge, isFlowering) {
  // Kode Anda di sini
}
```

Semangat! 🌻
