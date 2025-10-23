# 🚢 Seaway Sightseeing Journey

> **Tingkat Kesulitan:** `Easy`

---

## 📋 Ringkasan Challenge

Buat sebuah function bernama `seawaySightseeing` yang menghitung jumlah setiap pemandangan yang terlihat selama perjalanan naik perahu dan mengembalikan sebuah object yang memetakan setiap pemandangan ke jumlah kemunculannya.

---

## 🎯 Tujuan

Tugas Anda adalah mengimplementasikan sebuah function yang memproses array pemandangan dan menghasilkan penghitungan frekuensi dari setiap pemandangan unik yang ditemui selama perjalanan.

---

## 🛠️ Spesifikasi Function

### Nama Function
```javascript
seawaySightseeing(sights)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `sights` | `Array<string>` | Sebuah array di mana setiap elemen merepresentasikan pemandangan yang terlihat selama perjalanan perahu. Pemandangan bisa berulang. |

### Return Value

**Tipe:** `Object`

Sebuah object di mana:
- **Keys** = Pemandangan unik yang terlihat (string)
- **Values** = Jumlah kemunculan setiap pemandangan (number)

---

## 📝 Langkah-langkah Implementasi

Ikuti langkah-langkah berikut untuk menyelesaikan challenge:

1. **Inisialisasi** sebuah object kosong untuk menyimpan jumlah setiap pemandangan

2. **Loop melalui** array `sights`

3. **Untuk setiap pemandangan:**
   - Jika pemandangan tidak ada dalam object → tambahkan dengan jumlah `1`
   - Jika pemandangan sudah ada → tambahkan jumlahnya dengan `1`

4. **Return** object yang berisi jumlah pemandangan

---

## 💡 Contoh

### Input
```javascript
const sights = ['dolphin', 'whale', 'seagull', 'dolphin', 'whale', 'dolphin'];
```

### Output yang Diharapkan
```javascript
{
  dolphin: 3,
  whale: 2,
  seagull: 1
}
```

---

## ✅ Poin-poin Penting

- Tangani **pemandangan duplikat** dengan benar dengan menambahkan jumlahnya
- Kembalikan sebuah **object**, bukan array
- Nama pemandangan bersifat **case-sensitive**
- Urutan keys dalam object yang dikembalikan tidak masalah

---

## 🚀 Memulai

Mulai dengan membuat struktur function Anda:

```javascript
function seawaySightseeing(sights) {
  // Kode Anda di sini
}
```

Selamat berpetualang di lautan! 🌊
