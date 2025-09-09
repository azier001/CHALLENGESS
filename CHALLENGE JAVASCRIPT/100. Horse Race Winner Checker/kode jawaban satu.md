# 🐎 Horse Race Winner Checker

## 📋 Deskripsi

Fungsi `horseRaceWinnerChecker` adalah sebuah fungsi JavaScript yang menentukan pemenang balapan kuda berdasarkan sistem poin. Fungsi ini menggabungkan posisi finish dengan bonus poin dari bendera yang sesuai dengan warna kuda menggunakan pendekatan objek untuk menyimpan poin setiap kuda.

## 🎯 Cara Kerja

Sistem penilaian menggunakan dua faktor:
1. **Poin Posisi**: Berdasarkan urutan finish dalam array
2. **Poin Bonus**: Berdasarkan jumlah bendera yang cocok dengan warna kuda

## 📊 Tabel Poin Posisi

| Posisi | Poin | Keterangan |
|--------|------|------------|
| 1      | 3    | Juara pertama |
| 2      | 2    | Juara kedua |
| 3      | 1    | Juara ketiga |
| 4+     | 0    | Tidak mendapat poin posisi |

## 🎨 Warna Kuda yang Didukung

| No | Warna | Keterangan |
|----|-------|------------|
| 1  | Red   | Merah |
| 2  | Blue  | Biru |
| 3  | Green | Hijau |
| 4  | Yellow| Kuning |
| 5  | White | Putih |

## 🏁 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `horses` | `Array<string>` | Array nama kuda yang sudah diurutkan berdasarkan posisi finish |
| `flags` | `Array<string>` | Array warna bendera yang tersedia di arena |

### Catatan Parameter
- **horses**: Urutan dalam array menentukan posisi finish (index 0 = juara 1)
- **flags**: Setiap bendera yang warnanya cocok dengan warna kuda memberikan +1 poin
- **Warna kuda**: Diambil dari kata pertama dalam nama kuda

## 💻 Kode Fungsi

```javascript
function horseRaceWinnerChecker(horses, flags) {
  const points = {};
  const colors = ['red', 'blue', 'green', 'yellow', 'white'];
  
  // Berikan poin berdasarkan posisi
  horses.forEach((horse, index) => {
    const color = horse.split(' ')[0].toLowerCase();
    
    // Tentukan poin posisi: 1st=3, 2nd=2, 3rd=1, sisanya=0
    points[horse] = index === 0 ? 3 : index === 1 ? 2 : index === 2 ? 1 : 0;
    
    // Hitung bendera untuk setiap kuda
    flags.forEach(flag => {
      if (flag.toLowerCase() === color) {
        points[horse]++;
      }
    });
  });
  
  // Cari pemenang
  let winner = horses[0];
  let maxPoints = points[winner];
  
  for (let i = 1; i < horses.length; i++) {
    if (points[horses[i]] > maxPoints) {
      winner = horses[i];
      maxPoints = points[horses[i]];
    }
  }
  
  return winner;
}
```

## 🔍 Aturan Tie-Breaking

⚠️ **Penting**: Dalam implementasi ini, jika dua kuda memiliki poin yang sama, **kuda yang muncul pertama** dalam array `horses` akan menang (karena loop dimulai dari index 1).

## 📝 Contoh Penggunaan

### Contoh 1: Pemenang Berdasarkan Poin Posisi
```javascript
const horses = ["Red Thunder", "Blue Lightning", "Green Storm"];
const flags = ["yellow", "purple"];

const winner = horseRaceWinnerChecker(horses, flags);
console.log(winner); // Output: "Red Thunder"

// Perhitungan poin:
// Red Thunder: 3 poin (posisi 1) + 0 poin bonus = 3 poin
// Blue Lightning: 2 poin (posisi 2) + 0 poin bonus = 2 poin
// Green Storm: 1 poin (posisi 3) + 0 poin bonus = 1 poin
```

### Contoh 2: Pemenang Berdasarkan Poin Bonus
```javascript
const horses = ["Red Thunder", "Blue Lightning", "Green Storm"];
const flags = ["blue", "blue", "blue"];

const winner = horseRaceWinnerChecker(horses, flags);
console.log(winner); // Output: "Blue Lightning"

// Perhitungan poin:
// Red Thunder: 3 poin + 0 poin bonus = 3 poin
// Blue Lightning: 2 poin + 3 poin bonus = 5 poin ← Pemenang!
// Green Storm: 1 poin + 0 poin bonus = 1 poin
```

### Contoh 3: Kuda dengan Warna Tidak Standar
```javascript
const horses = ["Purple Magic", "Red Thunder", "Blue Lightning"];
const flags = ["red", "blue"];

const winner = horseRaceWinnerChecker(horses, flags);
console.log(winner); // Output: "Red Thunder"

// Perhitungan poin:
// Purple Magic: 3 poin + 0 poin bonus = 3 poin (purple tidak ada di daftar warna)
// Red Thunder: 2 poin + 1 poin bonus = 3 poin
// Blue Lightning: 1 poin + 1 poin bonus = 2 poin
// Tie antara Purple Magic dan Red Thunder, Purple Magic menang karena lebih dulu
```

### Contoh 4: Multiple Flags dengan Warna Sama
```javascript
const horses = ["White Snow", "Red Fire", "Blue Ocean"];
const flags = ["white", "white", "red"];

const winner = horseRaceWinnerChecker(horses, flags);
console.log(winner); // Output: "White Snow"

// Perhitungan poin:
// White Snow: 3 poin + 2 poin bonus = 5 poin ← Pemenang!
// Red Fire: 2 poin + 1 poin bonus = 3 poin
// Blue Ocean: 1 poin + 0 poin bonus = 1 poin
```

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `string` | Nama kuda pemenang dengan poin tertinggi |

## 🏗️ Struktur Data Internal

Fungsi menggunakan objek `points` untuk menyimpan poin setiap kuda:
```javascript
// Contoh struktur objek points:
{
  "Red Thunder": 4,
  "Blue Lightning": 5,
  "Green Storm": 1
}
```

## 💡 Tips Penggunaan

1. **Format Nama Kuda**: Pastikan kata pertama adalah warna yang valid
2. **Case Insensitive**: Fungsi mengabaikan huruf besar/kecil pada warna
3. **Urutan Array**: Index 0 = juara 1, index 1 = juara 2, dst.
4. **Warna Valid**: Hanya 5 warna yang didukung (red, blue, green, yellow, white)
5. **Multiple Flags**: Semakin banyak bendera dengan warna sama, semakin besar bonus

## ⚠️ Catatan Penting

- **Tie-Breaking**: Kuda yang muncul lebih awal dalam array menang jika ada seri poin
- **Warna Harus Valid**: Warna di luar daftar yang didukung tidak akan mendapat poin bonus
- **Algoritma Linear**: Menggunakan loop sederhana untuk mencari pemenang
- **Objek Points**: Setiap kuda disimpan sebagai key dengan value berupa total poin

## 🔧 Perbedaan dengan Implementasi Lain

Implementasi ini menggunakan:
- **Objek** untuk menyimpan poin (bukan array of objects)
- **Loop sederhana** untuk mencari pemenang (bukan sorting)
- **Tie-breaking** berdasarkan urutan kemunculan dalam array horses
