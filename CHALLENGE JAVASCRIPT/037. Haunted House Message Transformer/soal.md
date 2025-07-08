# 🏚️ Haunted House Message Transformer

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mengubah pesan biasa menjadi komunikasi yang menyeramkan, seolah-olah ditemukan di kedalaman rumah berhantu. Challenge ini terinspirasi dari petualangan anniversary pasangan yang menyeramkan di sebuah rumah tua dan misterius dimana pesan-pesan rahasia menanti untuk didekode.

---

## 🎯 Tujuan

Kembangkan sebuah function bernama `createSpookyMessage` yang menerima pesan biasa dan mengubahnya menjadi komunikasi yang menakutkan dengan membalik urutan kata dan mengganti kata-kata tertentu dengan padanan yang lebih menyeramkan.

---

## 📝 Persyaratan Function

### Function Signature
```javascript
function createSpookyMessage(message)
```

### Parameter
- **`message`** *(string)*: Pesan asli yang ditemukan di rumah berhantu

### Return Value
- **Returns**: String yang merepresentasikan pesan spooky yang telah diubah

---

## 🔧 Langkah-langkah Implementasi

Ikuti langkah-langkah berurutan berikut untuk membuat transformasi spooky:

1. **Split the Message**
   - Pecah input string menjadi kata-kata individual

2. **Reverse Word Order**
   - Susun ulang kata-kata dalam urutan terbalik

3. **Apply Spooky Replacements**
   - Ubah kata-kata tertentu menggunakan kamus haunted di bawah

4. **Reconstruct the Message**
   - Gabungkan kembali kata-kata yang telah dimodifikasi menjadi satu string

---

## 👻 Kamus Kata Spooky

Ganti kata-kata berikut dengan alternatif menyeramkan:

| Kata Asli | Pengganti Spooky |
|-----------|------------------|
| `"happy"`     | `"haunted"`       |
| `"love"`      | `"fear"`          |
| `"together"`  | `"trapped"`       |
| `"forever"`   | `"nevermore"`     |

---

## 🏠 Konteks Cerita

*Pada anniversary pernikahan mereka, sepasang suami istri memutuskan untuk menjelajahi sebuah rumah tua yang ditinggalkan dan dikabarkan berhantu. Saat mereka beranjak lebih dalam ke dalam mansion, mereka menemukan pesan-pesan misterius yang terukir di dinding dan tertulis di kertas-kertas berdebu. Pesan-pesan ini tampaknya dikodekan dengan cara yang aneh - kata-katanya tercampur dan frasa-frasa tertentu telah diganti dengan alternatif yang lebih menyeramkan. Tugas Anda adalah membuat decoder yang dapat mengubah pesan-pesan spooky ini kembali ke bentuk aslinya... atau mungkin mengubah pesan-pesan tak berdosa menjadi peringatan yang menakutkan.*

---

## 💡 Contoh Penggunaan

```javascript
// Contoh input
const originalMessage = "We will be happy together forever in love";

// Proses transformasi yang diharapkan:
// 1. Split: ["We", "will", "be", "happy", "together", "forever", "in", "love"]
// 2. Reverse: ["love", "in", "forever", "together", "be", "happy", "will", "We"]
// 3. Replace: ["fear", "in", "nevermore", "trapped", "be", "haunted", "will", "We"]
// 4. Join: "fear in nevermore trapped be haunted will We"

const spookyMessage = createSpookyMessage(originalMessage);
console.log(spookyMessage); // Output: "fear in nevermore trapped be haunted will We"
```

---

## 🎃 Catatan Challenge

- Function harus dapat menangani input string apapun
- Pencocokan kata untuk penggantian harus case-sensitive
- Pertahankan spasi asli antara kata-kata dalam output final
- Transformasi ini menciptakan narasi yang menyeramkan dan terbalik, sempurna untuk suasana Halloween

---

*Semoga berhasil mendekode misteri rumah berhantu! 👻*
