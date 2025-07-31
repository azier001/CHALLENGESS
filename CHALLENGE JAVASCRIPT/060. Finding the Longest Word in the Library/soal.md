# 📚 Mencari Kata Terpanjang di Perpustakaan

## 🎯 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Bayangkan diri Anda berada di perpustakaan yang tenang pada sore hari yang damai, dikelilingi oleh buku-buku tua dan kata-kata yang terlupakan. Misi Anda adalah menemukan kata terpanjang di antara koleksi kata-kata dari naskah kuno tersebut.

---

## 📋 Deskripsi Tugas

Buat sebuah function bernama `findLongestWord` yang menerima array kata-kata dan mengembalikan kata terpanjang yang ditemukan.

### 🔧 Function Signature

```javascript
function findLongestWord(words) {
    // Implementasi Anda di sini
}
```

---

## 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `words` | `Array<string>` | Sebuah array string, di mana setiap string merepresentasikan kata dari buku-buku perpustakaan |

---

## 📤 Return Value

- **Type:** `string`
- **Deskripsi:** Kata terpanjang yang ditemukan dalam input array
- **Kasus Khusus:** Jika ada beberapa kata dengan panjang maksimum yang sama, kembalikan kata **pertama yang ditemukan**

---

## 🛠️ Panduan Implementasi

Ikuti langkah-langkah berikut untuk menyelesaikan challenge:

1. **Inisialisasi** variabel untuk menyimpan kata terpanjang, mulai dengan string kosong
2. **Loop** melalui setiap kata dalam input array menggunakan basic loops (`for` atau `while`)
3. **Bandingkan** panjang setiap kata dengan panjang kata terpanjang saat ini
4. **Update** variabel kata terpanjang jika kata saat ini lebih panjang
5. **Return** kata terpanjang setelah memeriksa semua kata

---

## 📏 Persyaratan Code

- ✅ Gunakan basic loops (`for` atau `while` loops)
- ✅ Panjang code: **10-19 baris**
- ✅ Tangani edge cases dengan tepat
- ✅ Ikuti langkah-langkah algoritma yang dijelaskan di atas

---

## 💡 Contoh Skenario

```javascript
// Contoh penggunaan
const libraryWords = ["ancient", "tome", "manuscript", "scroll", "book"];
const result = findLongestWord(libraryWords);
// Expected: "manuscript" (10 karakter)
```

---

## 🎨 Visual Algorithm Flow

```
Start
  ↓
Initialize longestWord = ""
  ↓
For each word in words array
  ↓
Apakah kata saat ini lebih panjang dari longestWord?
  ↓ Ya         ↓ Tidak
Update         Lanjut ke
longestWord    kata berikutnya
  ↓              ↓
Lanjut ←---------
  ↓
Semua kata sudah diperiksa?
  ↓ Ya
Return longestWord
  ↓
End
```

---

## 🎯 Poin Penting yang Harus Diingat

> - Fokus pada **perbandingan panjang**, bukan urutan alfabetis
> - Return kata terpanjang **pertama** jika ada yang sama panjangnya
> - Gunakan **struktur loop dasar** sesuai yang ditentukan
> - Jaga agar solusi Anda **bersih dan mudah dibaca**

---

*Selamat coding! Semoga Anda menemukan kata-kata terpanjang di perpustakaan digital! 📖✨*
