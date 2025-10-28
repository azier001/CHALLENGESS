# 🚣 Counting River Obstacles

## 📊 Level Challenge
**Easy**

---

## 🎯 Gambaran Umum

Bayangkan sebuah perahu tua yang perlahan mengapung di sepanjang sungai yang tenang. Tugas Anda adalah menghitung jumlah rintangan yang dihadapi perahu selama perjalanannya.

Sungai direpresentasikan sebagai array di mana setiap elemen adalah **jalur yang bersih** (`0`) atau **rintangan** (`1`). Perahu dimulai dari awal array dan bergerak maju, menemui setiap elemen satu per satu.

---

## 📝 Deskripsi Masalah

Buatlah sebuah function bernama `countRiverObstacles` yang menerima `river` sebagai parameter dan menghitung total jumlah rintangan di sungai.

---

## 🔧 Function Signature

```javascript
function countRiverObstacles(river)
```

---

## 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `river` | Array | Sebuah array berisi angka yang merepresentasikan sungai. Setiap elemen adalah `0` (jalur bersih) atau `1` (rintangan) |

---

## 📤 Return Value

- **Type**: `Integer`
- **Deskripsi**: Total jumlah rintangan yang ditemui di sungai

---

## 💡 Pendekatan

Berikut adalah pendekatan yang direkomendasikan untuk menyelesaikan masalah ini:

1. **Inisialisasi** variabel counter untuk melacak rintangan
2. **Iterasi** melalui setiap elemen dalam array sungai
3. **Periksa** apakah elemen bernilai `1` (rintangan)
4. **Increment** counter ketika rintangan ditemukan
5. **Return** jumlah akhir setelah memeriksa semua elemen

---

## 🔑 Konsep Kunci

- Iterasi array dasar
- Statement kondisional
- Operator increment
- Teknik pencarian array

---

## 📚 Contoh

### Input:
```javascript
river = [0, 1, 0, 1, 1, 0, 1, 0]
```

### Proses:
- Posisi 0: `0` → Jalur bersih
- Posisi 1: `1` → **Rintangan** (count: 1)
- Posisi 2: `0` → Jalur bersih
- Posisi 3: `1` → **Rintangan** (count: 2)
- Posisi 4: `1` → **Rintangan** (count: 3)
- Posisi 5: `0` → Jalur bersih
- Posisi 6: `1` → **Rintangan** (count: 4)
- Posisi 7: `0` → Jalur bersih

### Output:
```javascript
4
```

---

## ✅ Requirements

- Gunakan teknik pencarian array dasar
- Implementasikan operator increment
- Tangani array dengan panjang berapapun
- Hitung hanya elemen dengan nilai `1`

---

## 🎓 Tujuan Pembelajaran

Dengan menyelesaikan challenge ini, Anda akan berlatih:

- ✓ Traversal dan iterasi array
- ✓ Implementasi logika kondisional
- ✓ Inisialisasi dan manipulasi variabel
- ✓ Problem-solving dengan struktur data dasar

---

**Selamat mengerjakan challenge! 🚀**
