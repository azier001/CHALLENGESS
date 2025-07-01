# 🕳️ Tantangan Penjelajah Gua

<div align="center">

![Difficulty](https://img.shields.io/badge/Tingkat%20Kesulitan-Mudah-brightgreen?style=for-the-badge)
![Language](https://img.shields.io/badge/Bahasa-JavaScript-yellow?style=for-the-badge&logo=javascript)

</div>

---

## 🎯 Briefing Misi

Kamu sedang mengembangkan sistem komunikasi untuk para penjelajah gua! Ketika penjelajah mengirim pesan di dalam sistem gua, terkadang mereka mendengar suara mereka sendiri bergema kembali. Tugasmu adalah membuat fungsi yang dapat membedakan antara pesan gema dan komunikasi yang berbeda.

---

## 📋 Spesifikasi Fungsi

### 🔧 Signature Fungsi
```javascript
function exploreCave(message1, message2) {
    // Implementasi kamu di sini
}
```

### 📥 Parameter Input

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `message1` | `string` | Pesan penjelajah pertama | `"Halo disana"` |
| `message2` | `string` | Pesan penjelajah kedua | `"Semua aman"` |

### 📤 Output yang Diharapkan

| Skenario | Kondisi | Format Output | 
|----------|---------|---------------|
| 🔊 **Gema Terdeteksi** | `message1 === message2` | `"Echo: [message]"` |
| 💬 **Pesan Berbeda** | `message1 !== message2` | `"[message1] & [message2]"` |

---

## 🎮 Contoh dalam Aksi

### 📢 Skenario Gema
```javascript
exploreCave("Hello", "Hello")
```
**Output:** `"Echo: Hello"`

*Penjelajah mendengar suara mereka sendiri memantul kembali dari dinding gua!*

---

### 🗣️ Skenario Komunikasi  
```javascript
exploreCave("Help needed", "On my way")
```
**Output:** `"Help needed & On my way"`

*Dua penjelajah yang berbeda sedang berkomunikasi satu sama lain.*

---

### 🌟 Contoh Lainnya

```javascript
// Pesan kosong (tetap gema!)
exploreCave("", "")
// Mengembalikan: "Echo: "

// Huruf besar-kecil penting!
exploreCave("SOS", "sos") 
// Mengembalikan: "SOS & sos"

// Angka sebagai string
exploreCave("Gua 1", "Gua 2")
// Mengembalikan: "Gua 1 & Gua 2"
```

---

## 🎯 Misi Kamu

Bangun fungsi `exploreCave` yang membantu para penjelajah gua memahami apakah mereka sedang mendengar gema dari suara mereka sendiri atau menerima pesan dari penjelajah lain. Semoga berhasil, penjelajah! 🗺️

---

## 📝 Catatan Penting

- Fungsi melakukan perbandingan **kesetaraan ketat** (`===`)
- Perbandingan **case-sensitive** (contoh: "Hello" ≠ "hello")  
- Bekerja dengan **string kosong** dan **karakter khusus**
- Tidak diperlukan validasi input untuk level tantangan ini
