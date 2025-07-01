# 🎉 Winter Party Scene Function

## 📝 Deskripsi

Fungsi `winter_party_scene()` adalah sebuah fungsi JavaScript yang membuat visualisasi ASCII art untuk pesta musim dingin. Fungsi ini akan menggambarkan tamu-tamu pesta dalam bentuk karakter sederhana yang dikelilingi oleh kepingan salju, memberikan suasana pesta musim dingin yang meriah.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `guests` | Number | Jumlah tamu yang akan ditampilkan dalam scene (1-10 tamu) |
| `snowflakes` | Number | Jumlah kepingan salju yang akan ditampilkan di atas dan bawah scene |

## 🎨 Karakter yang Digunakan

| Karakter | Fungsi | Posisi |
|----------|--------|---------|
| `o` | Kepala tamu | Baris pertama tamu |
| `\|\|` | Badan tamu | Baris kedua tamu |
| `/ \` | Kaki tamu | Baris ketiga tamu |
| `*` | Kepingan salju | Atas dan bawah scene |
| `_` | Lantai/tanah | Tengah scene |

## 💻 Code Asli

```javascript
function winter_party_scene(guests, snowflakes) {
    const width = 30;
    let scene = [];
    
    // Header
    scene.push("Winter Party!".padStart((width + 13) / 2).padEnd(width));
    
    // Top snowflakes
    let snowflakeLine = "*".repeat(snowflakes).padEnd(width);
    scene.push(snowflakeLine);
    
    // Guests
    for (let i = 0; i < 3; i++) {
        let line = "";
        for (let j = 0; j < guests; j++) {
            if (i === 0) line += " o ";
            else if (i === 1) line += "||";
            else line += "/ \\";
            line += " ";
        }
        scene.push(line.trim().padStart((width + line.trim().length) / 2).padEnd(width));
    }
    
    // Floor
    scene.push("_".repeat(width));
    
    // Bottom snowflakes
    scene.push(snowflakeLine);
    
    return scene.join("\n");
}
```

## 🎯 Cara Kerja

1. **Inisialisasi**: Fungsi menentukan lebar scene (30 karakter) dan membuat array kosong untuk menyimpan baris-baris scene
2. **Header**: Menambahkan judul "Winter Party!" yang diposisikan di tengah
3. **Salju Atas**: Membuat baris kepingan salju di bagian atas
4. **Tamu-tamu**: Menggunakan loop untuk membuat 3 baris yang merepresentasikan tamu:
   - Baris 1: Kepala (o)
   - Baris 2: Badan (||)
   - Baris 3: Kaki (/ \)
5. **Lantai**: Menambahkan garis lantai menggunakan karakter underscore
6. **Salju Bawah**: Menambahkan kepingan salju di bagian bawah
7. **Output**: Menggabungkan semua baris menjadi satu string dengan newline

## 📊 Contoh Penggunaan & Output

### Contoh 1: 3 Tamu, 10 Kepingan Salju
```javascript
console.log(winter_party_scene(3, 10));
```

**Output:**
```
         Winter Party!        
**********                    
       o  o  o                
       |||||| 
      / \/ \/ \               
______________________________
**********                    
```

### Contoh 2: 1 Tamu, 5 Kepingan Salju
```javascript
console.log(winter_party_scene(1, 5));
```

**Output:**
```
         Winter Party!        
*****                         
            o                 
           ||                 
          / \                 
______________________________
*****                         
```

### Contoh 3: 5 Tamu, 15 Kepingan Salju
```javascript
console.log(winter_party_scene(5, 15));
```

**Output:**
```
         Winter Party!        
***************               
   o  o  o  o  o              
   ||||||||||||               
  / \/ \/ \/ \/ \             
______________________________
***************               
```

## 🚀 Tips Penggunaan

- **Jumlah Tamu Optimal**: Gunakan 1-5 tamu untuk hasil yang paling bagus dalam lebar 30 karakter
- **Kepingan Salju**: Jumlah 5-15 kepingan salju memberikan efek visual yang menarik
- **Responsive**: Scene akan otomatis menyesuaikan posisi tengah berdasarkan jumlah tamu

## ⚠️ Catatan Penting

- Lebar scene tetap 30 karakter
- Jika terlalu banyak tamu, visualisasi mungkin akan terpotong atau tidak seimbang
- Fungsi ini cocok untuk ditampilkan di console atau area text monospace

## 🎨 Contoh Kreatif

Anda bisa menggunakan fungsi ini untuk:
- Membuat greeting card digital
- Animasi sederhana di console
- Bagian dari game text-based
- Dekorasi untuk aplikasi musim dingin
