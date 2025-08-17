# 🐑 Shepherd's Path Counter

## 📊 Overview Tantangan

| Tingkat Kesulitan | Level |
|-------------------|-------|
| **Easy** | ⭐ |

---

## 🎯 Tujuan

Buat function bernama `countShepherdMoves` yang menghitung jumlah pergerakan shepherd saat melewati field yang berisi sheep dan dusty spot.

## 📝 Deskripsi Masalah

Shepherd bergerak melalui field yang direpresentasikan sebagai string, dimana:
- Setiap `'s'` merepresentasikan **sheep** 🐑
- Setiap `'.'` merepresentasikan **dusty spot** 🌫️

Shepherd melakukan satu move setiap kali terjadi transisi antara:
- Sheep ke dusty spot (`'s'` → `'.'`)
- Dusty spot ke sheep (`'.'` → `'s'`)

## 🔧 Spesifikasi Function

```javascript
function countShepherdMoves(field) {
    // Implementasi Anda di sini
}
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `field` | `string` | String yang merepresentasikan field berisi sheep (`'s'`) dan dusty spot (`'.'`) |

### Return Value

- **Type**: `integer`
- **Deskripsi**: Total jumlah move yang dilakukan oleh shepherd

## 💡 Contoh

```javascript
// Contoh 1: Pola bergantian sederhana
countShepherdMoves("s.s.s") 
// Returns: 4 moves
// Transisi: s→. → .→s → s→. → .→s

// Contoh 2: Karakter berturut-turut yang sama
countShepherdMoves("sss...") 
// Returns: 1 move
// Transisi: s→.

// Contoh 3: Tidak ada transisi
countShepherdMoves("ssss") 
// Returns: 0 moves
// Tidak ada perubahan karakter
```

## 🔍 Poin Penting yang Harus Diingat

- ✅ Hitung transisi antara karakter adjacent yang berbeda
- ✅ Karakter berturut-turut yang sama tidak dihitung sebagai move
- ✅ String kosong harus return 0
- ✅ String dengan satu karakter harus return 0

## 🧠 Hints Pendekatan

1. **Iterasi melalui string** dengan membandingkan karakter adjacent
2. **Hitung perubahan** dari satu type karakter ke type lainnya
3. **Handle edge cases** seperti string kosong atau string dengan satu karakter

---

*Semoga berhasil dengan implementasi Anda! 🚀*
