# 🦸‍♂️ Fungsi `actOfValor`

## 📝 Deskripsi

Fungsi `actOfValor` adalah sebuah fungsi JavaScript yang digunakan untuk mengevaluasi apakah suatu tindakan dapat dikategorikan sebagai "tindakan kepahlawanan" atau tidak. Fungsi ini menerima satu parameter berupa string yang menggambarkan sebuah aksi, kemudian mengembalikan pesan yang menunjukkan apakah aksi tersebut termasuk tindakan kepahlawanan.

## 📋 Parameter

| Parameter | Tipe   | Wajib | Deskripsi                                    |
|-----------|--------|-------|----------------------------------------------|
| `action`  | string | Ya    | String yang menggambarkan tindakan/aksi     |

## 🎯 Return Value

Fungsi ini mengembalikan nilai bertipe `string`:

- **"This is an act of valor!"** - Jika tindakan termasuk kategori kepahlawanan
- **"This action is not considered an act of valor."** - Jika tindakan tidak termasuk kategori kepahlawanan

## 🏆 Tindakan yang Dikategorikan sebagai Act of Valor

| Tindakan          | Deskripsi                        |
|-------------------|----------------------------------|
| `save a life`     | Menyelamatkan nyawa seseorang    |
| `help the elderly`| Membantu orang tua/lansia        |
| `defend the weak` | Membela orang yang lemah         |

## 💾 Kode Fungsi

```javascript
function actOfValor(action) {
  // Menggunakan switch statement untuk mengecek jenis tindakan
  switch (action) {
    
    // Kasus-kasus yang dikategorikan sebagai tindakan kepahlawanan
    case 'save a life':        // Menyelamatkan nyawa
    case 'help the elderly':   // Membantu lansia
    case 'defend the weak':    // Membela yang lemah
      return 'This is an act of valor!';
    
    // Kasus default untuk tindakan lainnya
    default:
      return 'This action is not considered an act of valor.';
  }
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Tindakan Kepahlawanan
```javascript
console.log(actOfValor('save a life'));
// Output: "This is an act of valor!"

console.log(actOfValor('help the elderly'));
// Output: "This is an act of valor!"

console.log(actOfValor('defend the weak'));
// Output: "This is an act of valor!"
```

### Contoh 2: Tindakan Biasa
```javascript
console.log(actOfValor('go shopping'));
// Output: "This action is not considered an act of valor."

console.log(actOfValor('watch TV'));
// Output: "This action is not considered an act of valor."

console.log(actOfValor(''));
// Output: "This action is not considered an act of valor."
```

## 📊 Contoh Output Lengkap

```
Input: 'save a life'       → Output: "This is an act of valor!"
Input: 'help the elderly'  → Output: "This is an act of valor!"
Input: 'defend the weak'   → Output: "This is an act of valor!"
Input: 'eat breakfast'     → Output: "This action is not considered an act of valor."
Input: 'play games'        → Output: "This action is not considered an act of valor."
```

## 💡 Tips Penggunaan

- Pastikan parameter yang dikirim sesuai persis dengan string yang sudah didefinisikan
- Fungsi ini **case-sensitive**, jadi `'Save A Life'` berbeda dengan `'save a life'`
- Parameter kosong atau undefined akan dikembalikan sebagai bukan tindakan kepahlawanan

## ⚠️ Catatan Penting

- Fungsi ini menggunakan **perbandingan string yang eksak**, jadi penulisan harus tepat
- Hanya ada 3 tindakan yang dikategorikan sebagai "act of valor"
- Semua tindakan lain akan dikategorikan sebagai bukan tindakan kepahlawanan
