# 🌱 Tantangan Garden Growth Tracker

> **Tingkat Kesulitan:** `Easy` 🟢

## 🎯 Gambaran Umum Tantangan

Buat sebuah function yang membantu keluarga petani memantau kebun mereka yang subur dan kaya klorofil dengan melacak tahap pertumbuhan tanaman berdasarkan jumlah hari sejak penanaman.

---

## 📋 Persyaratan Function

### Function Signature
```javascript
function gardenStatus(plantType, daysGrown)
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `plantType` | `string` | Jenis tanaman (contoh: "tomato", "carrot", "lettuce") |
| `daysGrown` | `number` | Jumlah hari sejak tanaman ditanam |

---

## 🌿 Tahap Pertumbuhan & Return Value

Function harus mengembalikan string yang mendeskripsikan status tanaman berdasarkan kondisi berikut:

| Rentang Hari | Status | Return String |
|---------------|--------|---------------|
| `< 0` | Invalid | `"Invalid number of days."` |
| `= 0` | Baru Ditanam | `"The [plantType] seed is just planted."` |
| `1 - 10` | Bertunas | `"The [plantType] seedling is sprouting."` |
| `11 - 20` | Tumbuh | `"The [plantType] plant is growing steadily."` |
| `21 - 30` | Dewasa | `"The [plantType] plant is mature and thriving."` |
| `> 30` | Siap Panen | `"The [plantType] plant is ready for harvest!"` |

> **Catatan:** Ganti `[plantType]` dengan jenis tanaman yang sebenarnya dalam return string Anda.

---

## 🛠️ Panduan Implementasi

### ✅ Requirements
- Gunakan **conditional statements** untuk mengecek nilai `daysGrown`
- Gunakan **string concatenation** atau **template literals** untuk menyertakan `plantType`
- Handle semua tahap pertumbuhan yang ditentukan dengan benar
- Return pesan status yang sesuai

### 💡 Tips
- Pertimbangkan menggunakan `if-else` statements atau `switch` cases
- Template literals (`` `string ${variable}` ``) membuat string interpolation lebih mudah
- Test edge cases seperti angka negatif dan boundary values

---

## 🧪 Contoh Penggunaan

```javascript
// Contoh pemanggilan function
gardenStatus("tomato", -1);    // "Invalid number of days."
gardenStatus("carrot", 0);     // "The carrot seed is just planted."
gardenStatus("lettuce", 5);    // "The lettuce seedling is sprouting."
gardenStatus("tomato", 15);    // "The tomato plant is growing steadily."
gardenStatus("carrot", 25);    // "The carrot plant is mature and thriving."
gardenStatus("lettuce", 35);   // "The lettuce plant is ready for harvest!"
```

---

## 🎨 Pendekatan Implementasi

1. **Validasi Input**: Cek apakah `daysGrown` bernilai negatif
2. **Cek Tahap Pertumbuhan**: Gunakan conditional logic untuk menentukan tahap yang sesuai
3. **Format Response**: Sertakan `plantType` dalam return string
4. **Return Result**: Berikan pesan status yang deskriptif

---

*Happy coding! 🌻 Semoga garden tracker Anda membantu merawat kebun digital yang paling berwarna-warni!*
