# 🐍 Anaconda Reticle Viewfinder Simulator

## 📋 Gambaran Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function bernama `anacondaReticle` yang menerima `name`, `length`, `color`, dan `action` sebagai parameter-nya.

Function ini mensimulasikan reticle viewfinder kamera yang fokus pada anaconda di hutan hujan untuk dokumenter alam. Function harus me-return string yang terformat yang merepresentasikan tampilan viewfinder kamera, menggabungkan detail input dengan beberapa teks yang sudah ditetapkan untuk membuat deskripsi bergaya dokumenter alam.

Gunakan string concatenation untuk menggabungkan parameter input dengan teks tetap untuk membuat output yang terformat. Ini akan membantu kamu berlatih operasi string dasar dan penggunaan variabel di JavaScript.

---

## 📝 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `name` | `string` | Nama yang diberikan untuk anaconda yang sedang difilmkan |
| `length` | `string` | Panjang anaconda dalam meter |
| `color` | `string` | Warna anaconda |
| `action` | `string` | Aktivitas anaconda saat ini |

**Return Value:** Function me-return string yang merepresentasikan tampilan viewfinder kamera.

---

## 📺 Format Output

Berikut contoh bagaimana output harus diformat:

```js
[RETICLE ACTIVE]
Subject: Anaconda
Name: (name input)
Length: (length input) meters
Color: (color input)
Activity: (action input)
[RECORDING]
```

---

## 🔍 Requirements

- ✅ Pastikan untuk menyertakan **semua informasi** yang disediakan dalam parameter
- ✅ Pertahankan **format yang tepat** seperti yang ditunjukkan dalam contoh
- ✅ Gunakan **string concatenation** untuk menggabungkan parameter dengan teks tetap

---

## 🎬 Contoh Penggunaan

```javascript
// Contoh pemanggilan function
anacondaReticle("Sasha", "8.5", "Hijau", "Berenang");

// Output yang diharapkan:
// [RETICLE ACTIVE]
// Subject: Anaconda
// Name: Sasha
// Length: 8.5 meters
// Color: Hijau
// Activity: Berenang
// [RECORDING]
```

---

## 💡 Tujuan Pembelajaran

Challenge ini membantu kamu berlatih:

- 🔤 Teknik **string concatenation**
- 🔧 **Penggunaan variabel** di JavaScript
- 📝 **Penanganan parameter function**
- 🎨 **String formatting** dan struktur
- 🧩 **Sintaks dasar JavaScript**

---

## 🌟 Tips untuk Sukses

> **Penting:** Perhatikan dengan seksama requirement format yang tepat, termasuk line break, spacing, dan penempatan bracket serta titik dua. Pastikan tampilan akhir mudah dibaca dan siap untuk di-copy.

Selamat coding! 🚀
