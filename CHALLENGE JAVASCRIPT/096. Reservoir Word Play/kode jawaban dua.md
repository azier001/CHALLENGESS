# 🎮 Fungsi reservoirWordPlay

## 📝 Deskripsi

Fungsi `reservoirWordPlay` adalah sebuah fungsi JavaScript yang melakukan permainan kata dengan aturan khusus:

- **Jika kata adalah palindrom** (sama ketika dibaca dari depan atau belakang) → hapus semua huruf vokal
- **Jika kata bukan palindrom** → balik urutan huruf dalam kata

Fungsi ini case-insensitive untuk pengecekan palindrom, artinya huruf besar dan kecil dianggap sama.

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
    // Periksa apakah kata adalah palindrom (tidak sensitif terhadap huruf besar/kecil)
    const normalizedWord = word.toLowerCase();
    const isPalindrome = normalizedWord === normalizedWord.split('').reverse().join('');
    
    if (isPalindrome) {
        // Hapus semua huruf vokal (a, e, i, o, u)
        return word.replace(/[aeiouAEIOU]/g, '');
    } else {
        // Balik urutan string
        return word.split('').reverse().join('');
    }
}
```

## 🎯 Cara Kerja

1. **Normalisasi**: Kata diubah ke huruf kecil untuk pengecekan palindrom
2. **Cek Palindrom**: Bandingkan kata asli dengan kata yang dibalik
3. **Kondisi Palindrom**: Jika palindrom, hapus semua vokal dari kata asli
4. **Kondisi Non-Palindrom**: Jika bukan palindrom, balik urutan huruf

## 📋 Contoh Penggunaan dan Output

### Kata Palindrom

```javascript
// Contoh kata palindrom
console.log(reservoirWordPlay("radar")); 
// Output: "rdr" (vokal a dihapus)

console.log(reservoirWordPlay("level")); 
// Output: "lvl" (vokal e dihapus)

console.log(reservoirWordPlay("Madam")); 
// Output: "Mdm" (vokal a dihapus, case tetap dipertahankan)

console.log(reservoirWordPlay("civic")); 
// Output: "cvc" (vokal i dihapus)
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

- ✅ **Case-insensitive** untuk pengecekan palindrom (huruf besar/kecil diabaikan)
- ✅ **Case-preserving** untuk hasil output (huruf besar/kecil dipertahankan)
- ✅ Bekerja dengan kata yang mengandung huruf besar dan kecil
- ⚠️ Hanya menangani huruf vokal bahasa Inggris (a, e, i, o, u)

## 🚀 Tips Penggunaan

1. **Testing Palindrom**: Kata seperti "Racecar", "Level", "Noon" akan dianggap palindrom
2. **Mixed Case**: Kata "MaDaM" tetap dianggap palindrom dan outputnya "MdM"
3. **Kata Pendek**: Fungsi bekerja dengan kata sepanjang apapun, termasuk satu huruf

## 📖 Return Value

- **Tipe**: `string`
- **Palindrom**: String tanpa vokal
- **Non-palindrom**: String dengan urutan huruf terbalik
