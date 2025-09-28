# 🎭 Tantangan Sorting Broadway Shows

## 📊 Tingkat Kesulitan
**Easy** ⭐

---

## 🎯 Gambaran Challenge

Buat sebuah function bernama `sortBroadwayShows` yang membantu aktor pemula memprioritaskan audisi mereka dengan mengurutkan Broadway shows berdasarkan rating popularitas.

### 🎪 Skenario
*Bayangkan Anda adalah bintang Broadway pemula yang mencoba memutuskan show mana yang akan diikuti audisinya. Anda ingin memprioritaskan show yang paling populer untuk memaksimalkan peluang mendapatkan peran di produksi yang sukses!*

---

## 📝 Requirements Function

### Function Signature
```javascript
function sortBroadwayShows(showTitles, ratings)
```

### 📥 Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `showTitles` | `Array<string>` | Array string yang merepresentasikan judul-judul Broadway shows |
| `ratings` | `Array<number>` | Array angka yang merepresentasikan rating dari show yang sesuai dalam urutan yang sama dengan `showTitles` |

### 📤 Return Value
- **Type:** `Array<string>`
- **Deskripsi:** Array judul show yang diurutkan berdasarkan rating dalam urutan **descending** (rating tertinggi pertama)

---

## 🛠️ Langkah-Langkah Implementasi

Ikuti langkah-langkah berikut untuk menyelesaikan challenge:

1. **📋 Buat Data Structure**
   - Buat array objek dimana setiap objek berisi:
     - Judul show
     - Rating yang sesuai

2. **🔄 Sort Data**
   - Urutkan array objek berdasarkan rating dalam urutan **descending**
   - Rating yang lebih tinggi harus muncul pertama

3. **🎯 Extract Results**
   - Extract judul show yang sudah diurutkan dari array objek yang telah disort

4. **✅ Return**
   - Return array judul show yang sudah diurutkan

---

## 📋 Asumsi & Constraints

> ⚠️ **Catatan Penting:**
> - Array input `showTitles` dan `ratings` akan selalu memiliki **panjang yang sama**
> - Kedua array akan berisi **minimal satu elemen**
> - Semua rating akan berupa **angka positif**
> - Index array berkorespondensi antara `showTitles` dan `ratings`

---

## 💡 Visualisasi Contoh

```
Input:
showTitles = ["Hamilton", "Cats", "The Lion King", "Phantom"]
ratings    = [9.5, 7.2, 8.8, 9.1]

Process:
[
  { title: "Hamilton", rating: 9.5 },
  { title: "Cats", rating: 7.2 },
  { title: "The Lion King", rating: 8.8 },
  { title: "Phantom", rating: 9.1 }
]
↓ Sort berdasarkan rating (descending)
[
  { title: "Hamilton", rating: 9.5 },
  { title: "Phantom", rating: 9.1 },
  { title: "The Lion King", rating: 8.8 },
  { title: "Cats", rating: 7.2 }
]

Output:
["Hamilton", "Phantom", "The Lion King", "Cats"]
```

---

## 🎪 Fun Fact
*Broadway shows dinilai oleh penonton dan kritikus, dan rating ini sering mempengaruhi penjualan tiket dan lamanya pertunjukan berlangsung. Show populer seperti Hamilton dan The Lion King memiliki rating tinggi yang konsisten dan telah berjalan selama bertahun-tahun!*

---

## 🚀 Siap untuk Coding?
Sekarang saatnya mengimplementasikan function `sortBroadwayShows` Anda dan membantu aktor yang bercita-cita tinggi membuat pilihan audisi terbaik! 🎭✨
