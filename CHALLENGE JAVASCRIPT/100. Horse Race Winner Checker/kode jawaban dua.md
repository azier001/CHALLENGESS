# 🐎 Horse Race Winner Checker

## 📋 Deskripsi

Fungsi `horseRaceWinnerChecker` adalah sebuah fungsi JavaScript yang menentukan pemenang balapan kuda berdasarkan sistem poin. Fungsi ini menggabungkan posisi finish dengan bonus poin dari bendera yang sesuai dengan warna kuda.

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
    // Hitung poin posisi untuk setiap kuda
    const horsePoints = horses.map((horse, index) => {
        let points = 0;
        
        // Berikan poin berdasarkan posisi
        if (index === 0) points += 3;      // Posisi pertama
        else if (index === 1) points += 2; // Posisi kedua
        else if (index === 2) points += 1; // Posisi ketiga
        
        // Ambil warna kuda (kata pertama dari nama kuda)
        const horseColor = horse.split(' ')[0].toLowerCase();
        
        // Hitung bendera yang cocok dengan warna kuda ini
        const matchingFlags = flags.filter(flag => flag.toLowerCase() === horseColor).length;
        points += matchingFlags;
        
        return {
            name: horse,
            points: points,
            originalIndex: index
        };
    });
    
    // Urutkan berdasarkan poin (menurun), lalu berdasarkan posisi asli (naik) untuk tie-breaking
    horsePoints.sort((a, b) => {
        if (b.points !== a.points) {
            return b.points - a.points; // Poin lebih tinggi menang
        }
        return a.originalIndex - b.originalIndex; // Posisi lebih awal menang jika seri
    });
    
    // Kembalikan nama kuda pemenang
    return horsePoints[0].name;
}
```

## 🔍 Aturan Tie-Breaking

Jika dua kuda memiliki poin yang sama, pemenang ditentukan berdasarkan:
- Kuda yang **finish lebih awal** (posisi asli lebih rendah) akan menang

## 📝 Contoh Penggunaan

### Contoh 1: Pemenang Berdasarkan Poin Posisi
```javascript
const horses = ["Red Thunder", "Blue Lightning", "Green Storm"];
const flags = ["yellow", "purple"];

const winner = horseRaceWinnerChecker(horses, flags);
console.log(winner); // Output: "Red Thunder"
```

**Penjelasan:**
- Red Thunder: 3 poin (posisi 1) + 0 poin bonus = **3 poin**
- Blue Lightning: 2 poin (posisi 2) + 0 poin bonus = **2 poin**
- Green Storm: 1 poin (posisi 3) + 0 poin bonus = **1 poin**

### Contoh 2: Pemenang Berdasarkan Poin Bonus
```javascript
const horses = ["Red Thunder", "Blue Lightning", "Green Storm"];
const flags = ["blue", "blue", "blue"];

const winner = horseRaceWinnerChecker(horses, flags);
console.log(winner); // Output: "Blue Lightning"
```

**Penjelasan:**
- Red Thunder: 3 poin (posisi 1) + 0 poin bonus = **3 poin**
- Blue Lightning: 2 poin (posisi 2) + 3 poin bonus = **5 poin** ← Pemenang!
- Green Storm: 1 poin (posisi 3) + 0 poin bonus = **1 poin**

### Contoh 3: Tie-Breaking
```javascript
const horses = ["Red Thunder", "Blue Lightning", "Green Storm"];
const flags = ["red", "blue"];

const winner = horseRaceWinnerChecker(horses, flags);
console.log(winner); // Output: "Red Thunder"
```

**Penjelasan:**
- Red Thunder: 3 poin + 1 poin bonus = **4 poin**
- Blue Lightning: 2 poin + 1 poin bonus = **3 poin**
- Green Storm: 1 poin + 0 poin bonus = **1 poin**

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `string` | Nama kuda pemenang dengan poin tertinggi |

## 💡 Tips Penggunaan

1. **Format Nama Kuda**: Pastikan kata pertama adalah warna (contoh: "Red Thunder", "Blue Lightning")
2. **Case Insensitive**: Fungsi akan mengabaikan huruf besar/kecil pada warna
3. **Urutan Array**: Index 0 dalam array `horses` = juara 1, index 1 = juara 2, dst.
4. **Multiple Flags**: Semakin banyak bendera dengan warna yang sama, semakin besar bonus poinnya

## ⚠️ Catatan Penting

- Warna kuda harus berada di kata pertama nama kuda
- Fungsi case-insensitive untuk pencocokan warna
- Jika ada seri poin, kuda yang finish lebih awal akan menang
- Hanya 3 posisi teratas yang mendapat poin posisi (1st, 2nd, 3rd)
