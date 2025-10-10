# 📚 Dokumentasi Fungsi `stackHayBales`

## 📝 Deskripsi

Fungsi `stackHayBales` digunakan untuk menggabungkan daftar item (seperti bale jerami) menjadi sebuah kalimat yang mudah dibaca dengan format yang rapi. Fungsi ini akan menambahkan item baru ke dalam tumpukan yang sudah ada, lalu memformatnya dengan koma dan kata "and" sesuai aturan tata bahasa Inggris.

### 🎯 Kegunaan
- Menggabungkan array string menjadi kalimat yang natural
- Otomatis menambahkan tanda koma dan kata "and" di tempat yang tepat
- Cocok untuk membuat daftar item dalam format kalimat

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `currentStack` | `Array` | Array yang berisi item-item yang sudah ada sebelumnya |
| `newBale` | `String` | Item baru yang akan ditambahkan ke dalam tumpukan |

---

## 🔄 Return Value

| Kondisi | Return Value | Contoh |
|---------|--------------|---------|
| Array kosong | String kosong (`''`) | `''` |
| 1 item | String item tersebut | `'hay'` |
| 2 item | "item1 and item2" | `'hay and straw'` |
| 3+ item | "item1, item2, and item3" | `'hay, straw, and grass'` |

---

## 💻 Kode Fungsi

```javascript
function stackHayBales(currentStack, newBale) {
  // Gabungkan array lama dengan item baru
  const fullStack = [...currentStack, newBale];
  
  // Jika array kosong, kembalikan string kosong
  if (fullStack.length === 0) {
    return '';
  }
  
  // Jika hanya ada 1 item, kembalikan item tersebut
  if (fullStack.length === 1) {
    return fullStack[0];
  }
  
  // Jika ada 2 item, gabungkan dengan "and"
  if (fullStack.length === 2) {
    return `${fullStack[0]} and ${fullStack[1]}`;
  }
  
  // Jika ada 3 item atau lebih:
  // Ambil semua item kecuali yang terakhir, gabungkan dengan koma
  const allButLast = fullStack.slice(0, -1).join(', ');
  
  // Ambil item terakhir
  const last = fullStack[fullStack.length - 1];
  
  // Kembalikan format: "item1, item2, and itemTerakhir"
  return `${allButLast}, and ${last}`;
}
```

---

## 📊 Contoh Output

### Contoh 1: Menambahkan item pertama
```javascript
stackHayBales([], 'hay');
```
**Output:**
```
'hay'
```

---

### Contoh 2: Menambahkan item kedua
```javascript
stackHayBales(['hay'], 'straw');
```
**Output:**
```
'hay and straw'
```

---

### Contoh 3: Menambahkan item ketiga
```javascript
stackHayBales(['hay', 'straw'], 'grass');
```
**Output:**
```
'hay, straw, and grass'
```

---

### Contoh 4: Menambahkan banyak item
```javascript
stackHayBales(['hay', 'straw', 'grass'], 'wheat');
```
**Output:**
```
'hay, straw, grass, and wheat'
```

---

## 🔍 Cara Kerja

Fungsi ini bekerja dengan langkah-langkah berikut:

1. **Penggabungan Array**: Fungsi pertama-tama menggabungkan `currentStack` dengan `newBale` menggunakan spread operator (`...`) untuk membuat array baru

2. **Pengecekan Kondisi**: 
   - Jika array kosong → return string kosong `''`
   - Jika 1 item → return item tersebut langsung
   - Jika 2 item → return dengan format "item1 and item2"
   - Jika 3+ item → lanjut ke langkah 3

3. **Format dengan Koma dan "and"**:
   - Ambil semua item kecuali yang terakhir menggunakan `slice(0, -1)`
   - Gabungkan dengan koma dan spasi menggunakan `join(', ')`
   - Ambil item terakhir
   - Gabungkan semuanya dengan format: `"item1, item2, and itemTerakhir"`

---

## 💡 Penjelasan untuk Pemula

Bayangkan kamu punya keranjang yang berisi beberapa jenis jerami, dan kamu ingin menulis daftarnya dalam bentuk kalimat yang enak dibaca.

**Contoh dalam kehidupan sehari-hari:**
- 1 item: "Saya punya apel"
- 2 item: "Saya punya apel and pisang"
- 3+ item: "Saya punya apel, pisang, and mangga"

Fungsi ini otomatis mengatur penulisan koma dan kata "and" di tempat yang tepat sesuai aturan bahasa Inggris!

---

## ⚙️ Catatan Teknis

- ✅ Fungsi ini **tidak mengubah** array `currentStack` yang asli (immutable)
- ✅ Mengikuti aturan **Oxford comma** (koma sebelum "and")
- ✅ Return value selalu berupa string
- ⚠️ Fungsi ini dirancang untuk bahasa Inggris

---

## 🌟 Modifikasi untuk Bahasa Indonesia

Jika ingin menggunakan untuk bahasa Indonesia, ubah "and" menjadi "dan":

```javascript
function stackHayBales(currentStack, newBale) {
  const fullStack = [...currentStack, newBale];
  
  if (fullStack.length === 0) {
    return '';
  }
  
  if (fullStack.length === 1) {
    return fullStack[0];
  }
  
  if (fullStack.length === 2) {
    return `${fullStack[0]} dan ${fullStack[1]}`;  // ubah "and" jadi "dan"
  }
  
  const allButLast = fullStack.slice(0, -1).join(', ');
  const last = fullStack[fullStack.length - 1];
  
  return `${allButLast}, dan ${last}`;  // ubah "and" jadi "dan"
}
```

**Contoh output dalam bahasa Indonesia:**
```javascript
stackHayBales(['jerami', 'rumput', 'gandum'], 'padi');
// Output: 'jerami, rumput, gandum, dan padi'
```
