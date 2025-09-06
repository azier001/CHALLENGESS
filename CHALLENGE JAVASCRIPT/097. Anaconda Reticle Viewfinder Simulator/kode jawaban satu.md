# 🐍 Dokumentasi Fungsi `anacondaReticle`

## 📝 Deskripsi

Fungsi `anacondaReticle` adalah sebuah fungsi JavaScript yang digunakan untuk membuat tampilan interface reticle (bidik) pengamatan untuk subjek anaconda. Fungsi ini menghasilkan output berupa string yang mensimulasikan sistem observasi atau perekaman anaconda dengan format yang terstruktur dan mudah dibaca.

## 🔧 Sintaks

```javascript
anacondaReticle(name, length, color, action)
```

## 📊 Parameter

| Parameter | Tipe   | Deskripsi                                    | Contoh          |
|-----------|--------|----------------------------------------------|-----------------|
| `name`    | String | Nama atau identifikasi anaconda             | "Alpha-7"       |
| `length`  | Number | Panjang anaconda dalam satuan meter         | 8.5             |
| `color`   | String | Warna dominan anaconda yang diamati         | "hijau gelap"   |
| `action`  | String | Aktivitas atau perilaku anaconda saat ini   | "berburu"       |

## 💻 Kode Fungsi

```javascript
function anacondaReticle(name, length, color, action) {
  // Mengembalikan string yang berisi informasi reticle anaconda
  // dalam format yang terstruktur untuk sistem observasi
  return "[RETICLE ACTIVE]\nSubject: Anaconda\nName: " + name + 
         "\nLength: " + length + " meters\nColor: " + color + 
         "\nActivity: " + action + "\n[RECORDING]";
}
```

## 🎯 Contoh Penggunaan

### Contoh 1: Pengamatan Anaconda Dewasa
```javascript
console.log(anacondaReticle("Titan-12", 9.2, "coklat kehitaman", "berenang"));
```

**Output:**
```
[RETICLE ACTIVE]
Subject: Anaconda
Name: Titan-12
Length: 9.2 meters
Color: coklat kehitaman
Activity: berenang
[RECORDING]
```

### Contoh 2: Pengamatan Anaconda Muda
```javascript
console.log(anacondaReticle("Junior-3", 4.8, "hijau muda", "berjemur"));
```

**Output:**
```
[RETICLE ACTIVE]
Subject: Anaconda
Name: Junior-3
Length: 4.8 meters
Color: hijau muda
Activity: berjemur
[RECORDING]
```

### Contoh 3: Pengamatan Anaconda dalam Mode Berburu
```javascript
console.log(anacondaReticle("Predator-X", 11.5, "hijau gelap dengan bercak", "mengintai mangsa"));
```

**Output:**
```
[RETICLE ACTIVE]
Subject: Anaconda
Name: Predator-X
Length: 11.5 meters
Color: hijau gelap dengan bercak
Activity: mengintai mangsa
[RECORDING]
```

## 🌟 Fitur Utama

- ✅ **Format Terstruktur**: Output diformat dengan jelas menggunakan label yang mudah dipahami
- ✅ **Fleksibel**: Dapat menerima berbagai jenis input untuk parameter
- ✅ **Simulasi Realistis**: Meniru tampilan sistem observasi profesional
- ✅ **Status Indikator**: Menampilkan status "[RETICLE ACTIVE]" dan "[RECORDING]"

## 📋 Catatan Penting

- Fungsi ini tidak melakukan validasi input, pastikan parameter yang diberikan sesuai dengan tipe data yang diharapkan
- Parameter `length` sebaiknya berupa angka positif yang masuk akal untuk ukuran anaconda (biasanya 3-12 meter)
- Semua parameter bersifat wajib untuk menghasilkan output yang lengkap

## 🚀 Pengembangan Selanjutnya

Beberapa ide pengembangan untuk fungsi ini:
- Tambahkan validasi input untuk memastikan data yang masuk sesuai
- Tambahkan parameter opsional seperti lokasi pengamatan atau timestamp
- Implementasikan format output yang berbeda (JSON, XML, dll.)
- Tambahkan sistem logging untuk menyimpan data pengamatan
