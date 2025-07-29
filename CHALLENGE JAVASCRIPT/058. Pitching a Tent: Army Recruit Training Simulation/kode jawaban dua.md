# 🏕️ Dokumentasi Fungsi `pitchTent`

## 📝 Deskripsi Fungsi

Fungsi `pitchTent` adalah simulasi untuk mendirikan tenda dengan sistem kesabaran dan percobaan. Fungsi ini akan memproses langkah-langkah mendirikan tenda, melewati langkah yang mudah, dan mengurangi kesabaran ketika menemui langkah yang sulit.

## 🎯 Cara Kerja

1. **Filter langkah mudah**: Semua langkah yang mengandung kata "easy" akan diabaikan
2. **Proses langkah sulit**: Setiap langkah yang mengandung "difficult" akan mengurangi kesabaran
3. **Sistem percobaan**: Jika kesabaran habis, akan menggunakan satu percobaan dan reset kesabaran
4. **Hasil akhir**: Berhasil jika semua langkah terfilter selesai, gagal jika percobaan habis

## 📊 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `steps` | Array | Daftar langkah-langkah untuk mendirikan tenda |
| `patience` | Number | Jumlah kesabaran awal (berapa kali bisa menghadapi langkah sulit) |
| `attempts` | Number | Jumlah percobaan yang tersedia |

## 🔄 Return Value

| Kondisi | Return Value |
|---------|--------------|
| Berhasil menyelesaikan semua langkah | `"Tent pitched successfully!"` |
| Gagal (percobaan habis) | `"Failed to pitch the tent!"` |

## 💻 Kode Fungsi

```javascript
function pitchTent(steps, patience, attempts) {
    let currentPatience = patience;
    let currentAttempts = attempts;
    
    // Pertama, filter semua langkah "mudah" (lewati sepenuhnya)
    let filteredSteps = [];
    for (let step of steps) {
        if (!step.includes("easy")) {
            filteredSteps.push(step);
        }
    }
    
    let i = 0;
    while (i < filteredSteps.length && currentPatience > 0 && currentAttempts > 0) {
        const step = filteredSteps[i];
        
        if (step.includes("difficult")) {
            currentPatience--;
            
            // Jika kesabaran mencapai 0, gunakan satu percobaan
            if (currentPatience <= 0) {
                currentAttempts--;
                
                // Berhenti jika tidak ada percobaan lagi
                if (currentAttempts <= 0) {
                    break;
                }
                
                // Reset kesabaran untuk percobaan berikutnya
                currentPatience = patience;
                
                // Lanjutkan dari langkah saat ini
                continue;
            }
        }
        
        i++;
    }
    
    // Berhasil jika kita menyelesaikan semua langkah yang difilter
    if (i >= filteredSteps.length) {
        return "Tent pitched successfully!";
    } else {
        return "Failed to pitch the tent!";
    }
}
```

## 📋 Contoh Penggunaan

### Contoh 1: Berhasil Mendirikan Tenda
```javascript
const steps1 = [
    "easy setup ground",
    "difficult insert poles", 
    "attach fabric",
    "easy stake corners"
];

const result1 = pitchTent(steps1, 2, 1);
console.log(result1); 
// Output: "Tent pitched successfully!"
```

**Penjelasan**: 
- Langkah "easy setup ground" dan "easy stake corners" diabaikan
- Langkah "difficult insert poles" mengurangi kesabaran menjadi 1
- Langkah "attach fabric" berhasil diselesaikan
- Semua langkah selesai = berhasil!

### Contoh 2: Gagal Mendirikan Tenda
```javascript
const steps2 = [
    "difficult prepare ground",
    "difficult insert poles",
    "difficult attach fabric", 
    "easy stake corners"
];

const result2 = pitchTent(steps2, 1, 1);
console.log(result2);
// Output: "Failed to pitch the tent!"
```

**Penjelasan**:
- Langkah "easy stake corners" diabaikan
- Langkah "difficult prepare ground" mengurangi kesabaran menjadi 0
- Kesabaran habis, gunakan 1 percobaan, reset kesabaran menjadi 1
- Langkah "difficult insert poles" mengurangi kesabaran menjadi 0 lagi
- Kesabaran habis lagi, tapi percobaan juga habis = gagal!

### Contoh 3: Semua Langkah Mudah
```javascript
const steps3 = [
    "easy setup ground",
    "easy attach fabric", 
    "easy stake corners"
];

const result3 = pitchTent(steps3, 1, 1);
console.log(result3);
// Output: "Tent pitched successfully!"
```

**Penjelasan**:
- Semua langkah mengandung "easy" sehingga diabaikan
- Tidak ada langkah yang perlu diproses = berhasil!

## 🧠 Tips Penggunaan

- **Kesabaran tinggi**: Cocok untuk langkah-langkah yang banyak mengandung "difficult"
- **Percobaan banyak**: Memberikan lebih banyak kesempatan jika kesabaran sering habis
- **Langkah mudah**: Akan selalu diabaikan, tidak mempengaruhi kesabaran atau percobaan
- **Strategi optimal**: Sesuaikan nilai `patience` dan `attempts` berdasarkan tingkat kesulitan langkah-langkah

## ⚠️ Catatan Penting

- Fungsi ini menggunakan metode `includes()` untuk mendeteksi kata "easy" dan "difficult"
- Jika sebuah langkah tidak mengandung "easy" atau "difficult", akan tetap diproses tapi tidak mengurangi kesabaran
- Kesabaran akan di-reset ke nilai awal setiap kali menggunakan percobaan baru
