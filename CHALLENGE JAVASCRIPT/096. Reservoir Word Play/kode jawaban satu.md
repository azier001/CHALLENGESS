# 🎮 Fungsi reservoirWordPlay

## 📝 Deskripsi

Fungsi `reservoirWordPlay` adalah sebuah fungsi JavaScript yang melakukan permainan kata dengan aturan khusus:

- **Jika kata adalah palindrom** (sama ketika dibaca dari depan atau belakang) → hapus semua huruf vokal
- **Jika kata bukan palindrom** → balik urutan huruf dalam kata

Fungsi ini case-sensitive untuk pengecekan palindrom, artinya huruf besar dan kecil harus sama persis.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `word` | `string` | Kata yang akan diproses dalam permainan kata |

## 📊 Tabel Karakter Vokal

Fungsi ini menghapus karakter vokal berikut jika kata adalah palindrom:

| Huruf Kecil | Huruf Besar |
|-------------|-------------|
| a | A |
| e | E |
| i | I |
| o | O |
| u | U |

## 💻 Kode Fungsi

```javascript
function reservoirWordPlay(word) {
  // Buat versi terbalik dari kata input
  const reversed = word.split('').reverse().join('');
  
  // Periksa apakah kata sama dengan versi terbaliknya (palindrom)
  if (word === reversed) {
    // Jika palindrom, hapus semua huruf vokal (case-insensitive)
    return word.replace(/[aeiou]/gi, '');
  } else {
    // Jika bukan palindrom, kembalikan versi terbalik
    return reversed;
  }
}
```

## 🎯 Cara Kerja

1. **Buat Versi Terbalik**: Kata dipecah menjadi array karakter, dibalik, lalu digabung kembali
2. **Cek Palindrom**: Bandingkan kata asli dengan kata yang sudah dibalik (case-sensitive)
3. **Kondisi Palindrom**: Jika palindrom, hapus semua vokal menggunakan regex case-insensitive
4. **Kondisi Non-Palindrom**: Jika bukan palindrom, kembalikan versi terbalik yang sudah dibuat

## 📋 Contoh Penggunaan dan Output

### Kata Palindrom (Case-Sensitive)

```javascript
// Contoh kata palindrom yang sesuai case
console.log(reservoirWordPlay("radar")); 
// Output: "rdr" (vokal a dihapus)

console.log(reservoirWordPlay("level")); 
// Output: "lvl" (vokal e dihapus)

console.log(reservoirWordPlay("civic")); 
// Output: "cvc" (vokal i dihapus)

console.log(reservoirWordPlay("noon")); 
// Output: "nn" (vokal o dihapus)

console.log(reservoirWordPlay("racecar")); 
// Output: "rccr" (vokal a dan e dihapus)
```

### Kata Yang Terlihat Palindrom Tapi Beda Case

```javascript
// Contoh kata yang palindrom tapi beda case (dianggap bukan palindrom)
console.log(reservoirWordPlay("Radar")); 
// Output: "radaR" (dibalik karena R ≠ r)

console.log(reservoirWordPlay("Level")); 
// Output: "leveL" (dibalik karena L ≠ l)

console.log(reservoirWordPlay("Madam")); 
// Output: "madaM" (dibalik karena M ≠ m)
```

### Kata Non-Palindrom

```javascript
// Contoh kata non-palindrom
console.log(reservoirWordPlay("hello")); 
// Output: "olleh" (dibalik)

console.log(reservoirWordPlay("world")); 
// Output: "dlrow" (dibalik)

console.log(reservoirWordPlay("JavaScript")); 
// Output: "tpircSavaJ" (dibalik)

console.log(reservoirWordPlay("coding")); 
// Output: "gnidoc" (dibalik)
```

## 🔍 Catatan Penting

- ⚠️ **Case-sensitive** untuk pengecekan palindrom (huruf besar/kecil harus sama persis)
- ✅ **Case-insensitive** untuk penghapusan vokal (huruf besar dan kecil vokal dihapus)
- ✅ Regex `/[aeiou]/gi` menangani semua vokal tanpa memperhatikan case
- 🔄 Proses pembalikan dilakukan terlebih dahulu untuk efisiensi

## 🚀 Tips Penggunaan

1. **Testing Palindrom**: Hanya kata dengan case yang sama persis seperti "radar", "level", "civic" yang dianggap palindrom
2. **Mixed Case**: Kata "Radar" atau "Level" TIDAK dianggap palindrom karena case berbeda
3. **Penghapusan Vokal**: Meskipun case-sensitive untuk palindrom, penghapusan vokal bersifat case-insensitive
4. **Optimasi**: Fungsi ini lebih efisien karena hanya membalik string sekali di awal

## 📖 Return Value

- **Tipe**: `string`
- **Palindrom case-sensitive**: String tanpa vokal (huruf besar dan kecil)
- **Non-palindrom atau beda case**: String dengan urutan huruf terbalik

## ⚖️ Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Ini | Versi Sebelumnya |
|-------|-----------|------------------|
| Pengecekan Palindrom | Case-sensitive | Case-insensitive |
| Efisiensi | Balik string sekali | Balik string dua kali |
| Regex Vokal | `/[aeiou]/gi` | `/[aeiouAEIOU]/g` |
| Kata "Radar" | Output: "radaR" | Output: "Rdr" |
