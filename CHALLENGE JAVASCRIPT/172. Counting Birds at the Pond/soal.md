# 🦆 Menghitung Burung di Kolam

## 📊 Ringkasan Challenge

**Tingkat Kesulitan:** `Beginner` 🟢

---

## 🎯 Tujuan

Seorang penyair sedang mengamati burung-burung di kolam lokal. Setiap kali seekor burung mendarat di kolam, penyair mencatat namanya. Tugas Anda adalah membantu penyair menghitung berapa kali setiap jenis burung telah diamati.

---

## 📝 Deskripsi Tugas

Buat sebuah function bernama **`countBirds`** yang memproses observasi kolam dan mengembalikan jumlah dari setiap jenis burung.

### Function Signature

```javascript
function countBirds(pondObservations) {
  // Kode Anda di sini
}
```

---

## 🔧 Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `pondObservations` | `array` | Sebuah array of strings di mana setiap string merepresentasikan burung yang diamati di kolam |

### Contoh Input:
```javascript
['duck', 'swan', 'duck', 'goose']
```

---

## 📤 Return Value

Function ini harus mengembalikan sebuah **object** di mana:
- **Keys** adalah nama burung (string)
- **Values** adalah jumlah observasi untuk burung tersebut (number)

### Contoh Output:
```javascript
{ duck: 3, swan: 1, goose: 1 }
```

---

## 💡 Contoh

### Input:
```javascript
countBirds(['duck', 'swan', 'duck', 'goose', 'duck'])
```

### Output:
```javascript
{
  duck: 3,
  swan: 1,
  goose: 1
}
```

---

## ⚡ Requirements

- ✅ Solusi harus **ringkas** dan **efisien**
- ✅ Idealnya antara **1 hingga 9 baris kode**
- ✅ Menangani jumlah observasi burung berapa pun
- ✅ Menangani nama burung apa pun

---

## 🎓 Hints

<details>
<summary>Klik untuk melihat hints</summary>

1. Pertimbangkan menggunakan object untuk menyimpan jumlah burung
2. Iterasi melalui array dan perbarui jumlahnya
3. Pikirkan bagaimana menangani burung yang belum pernah terlihat sebelumnya
4. Method JavaScript modern seperti `reduce()` dapat membuat ini sangat ringkas

</details>

---

## 🏁 Mulai Coding

Siap membantu penyair? Mulai coding solusi Anda sekarang!

```javascript
function countBirds(pondObservations) {
  // Tulis solusi Anda di sini
}

// Test function Anda
console.log(countBirds(['duck', 'swan', 'duck', 'goose', 'duck']));
// Expected: { duck: 3, swan: 1, goose: 1 }
```

---

**Happy Coding!** 🚀
