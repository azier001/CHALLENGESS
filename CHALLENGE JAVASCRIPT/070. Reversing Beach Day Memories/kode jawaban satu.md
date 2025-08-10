# 🏖️ Dokumentasi Fungsi `reverseBeachDay`

## 📋 Deskripsi

Fungsi `reverseBeachDay` adalah sebuah utilitas yang digunakan untuk membalik urutan array dan string sekaligus. Fungsi ini cocok digunakan ketika Anda ingin membalik dua jenis data berbeda dalam satu pemanggilan fungsi yang sederhana.

## ⚙️ Parameter

| Parameter | Tipe     | Deskripsi                                    |
|-----------|----------|----------------------------------------------|
| `items`   | Array    | Array yang berisi item-item yang akan dibalik urutannya |
| `phrase`  | String   | Teks/kalimat yang akan dibalik karakter-karakternya |

## 📤 Return Value

Fungsi ini mengembalikan sebuah array dengan 2 elemen:
- **Elemen ke-0**: Array yang sudah dibalik urutannya
- **Elemen ke-1**: String yang sudah dibalik karakter-karakternya

## 💾 Source Code

```javascript
function reverseBeachDay(items, phrase) {
  // Membalik urutan elemen dalam array
  const reversedItems = items.reverse();
  
  // Membalik urutan karakter dalam string
  // 1. Pecah string menjadi array karakter dengan split('')
  // 2. Balik urutan array dengan reverse()
  // 3. Gabungkan kembali menjadi string dengan join('')
  const reversedPhrase = phrase.split('').reverse().join('');
  
  // Mengembalikan array berisi hasil pembalikan items dan phrase
  return [reversedItems, reversedPhrase];
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Data Pantai
```javascript
const itemsPantai = ['payung', 'sandal', 'sunscreen', 'handuk'];
const kalimatPantai = 'hari pantai yang menyenangkan';

const hasil = reverseBeachDay(itemsPantai, kalimatPantai);

console.log('Array terbalik:', hasil[0]);
console.log('Kalimat terbalik:', hasil[1]);
```

**Output:**
```
Array terbalik: ['handuk', 'sunscreen', 'sandal', 'payung']
Kalimat terbalik: nakgnaneysnem gnay iatinap irah
```

### Contoh 2: Data Angka dan Nama
```javascript
const angka = [1, 2, 3, 4, 5];
const nama = 'JavaScript';

const [angkaTerbalik, namaTerbalik] = reverseBeachDay(angka, nama);

console.log('Angka terbalik:', angkaTerbalik);
console.log('Nama terbalik:', namaTerbalik);
```

**Output:**
```
Angka terbalik: [5, 4, 3, 2, 1]
Nama terbalik: tpircSavaJ
```

## ⚠️ Hal yang Perlu Diperhatikan

1. **Mutasi Array**: Fungsi `reverse()` akan mengubah array asli. Jika Anda ingin mempertahankan array asli, buat salinan terlebih dahulu:
   ```javascript
   const reversedItems = [...items].reverse();
   ```

2. **Parameter Harus Sesuai Tipe**: Pastikan parameter pertama adalah array dan parameter kedua adalah string untuk hasil yang optimal.

3. **Karakter Khusus**: Fungsi ini akan membalik semua karakter termasuk spasi dan karakter khusus lainnya.

## 🎯 Kasus Penggunaan

- Membalik daftar item dan teks secara bersamaan
- Membuat efek "mirror" pada data
- Utilitas untuk game atau aplikasi yang membutuhkan pembalikan data
- Testing dan debugging dengan data yang dibalik

---

*Dokumentasi ini dibuat untuk membantu pemahaman fungsi `reverseBeachDay` dengan penjelasan yang mudah dipahami oleh pemula.*
