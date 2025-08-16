# 💪 Challenge Gym Progress Tracker

## 🎯 Gambaran Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function yang membantu melacak progress workout Anda dengan membandingkan rutinitas exercise di hari yang berbeda. Challenge ini akan membantu Anda berlatih array comparison dan conditional logic dalam programming.

---

## 📋 Deskripsi Masalah

Tugas Anda adalah membuat function bernama `gymProgressTracker` yang menganalisis konsistensi workout antara dua sesi latihan. Function ini akan menentukan apakah Anda mengikuti rutinitas yang sama atau mengubah variasi latihan!

### 🔍 Cara Kerja

Function membandingkan dua sesi workout:
- **Rutinitas sama**: Exercise yang identik dalam urutan yang sama → Training konsisten
- **Rutinitas berbeda**: Ada variasi dalam exercise atau urutan → Pendekatan training yang bervariasi

---

## ⚙️ Spesifikasi Function

### Function Signature
```javascript
function gymProgressTracker(day1Exercises, day2Exercises)
```

### 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `day1Exercises` | `Array<string>` | Daftar exercise yang dilakukan pada Hari 1 |
| `day2Exercises` | `Array<string>` | Daftar exercise yang dilakukan pada Hari 2 |

### 📤 Return Value

| Kondisi | Return Value |
|---------|-------------|
| Array identik (exercise sama, urutan sama) | `"You did the same workout on both days!"` |
| Array memiliki perbedaan apapun | `"You mixed it up today!"` |

---

## 💡 Contoh Skenario

### Skenario 1: Workout yang Sama
```javascript
day1Exercises = ["push-ups", "squats", "planks"]
day2Exercises = ["push-ups", "squats", "planks"]
// Expected output: "You did the same workout on both days!"
```

### Skenario 2: Urutan Berbeda
```javascript
day1Exercises = ["push-ups", "squats", "planks"]
day2Exercises = ["squats", "push-ups", "planks"]
// Expected output: "You mixed it up today!"
```

### Skenario 3: Exercise Berbeda
```javascript
day1Exercises = ["push-ups", "squats"]
day2Exercises = ["push-ups", "burpees"]
// Expected output: "You mixed it up today!"
```

---

## 🎯 Requirement Utama

- ✅ Membandingkan dua array berisi string exercise
- ✅ Memeriksa exact match (exercise sama dalam urutan sama)
- ✅ Return pesan feedback yang sesuai
- ✅ Menangani array dengan panjang berapapun
- ✅ Comparison nama exercise yang case-sensitive

---

## 🧠 Hints & Tips

> **💡 Pikirkan Tentang:**
> - Cara membandingkan array element per element
> - Apa yang dimaksud dengan array "identik"
> - Edge case seperti array kosong atau panjang berbeda

> **🔧 Konsep yang Berguna:**
> - Teknik array comparison
> - Conditional statement
> - String comparison

---

## 🚀 Siap untuk Coding?

Sekarang saatnya mengimplementasikan function `gymProgressTracker` Anda! Ingat untuk mengujinya dengan berbagai kombinasi workout untuk memastikan berfungsi dengan benar.

**Selamat berlatih coding workout! 💪**
