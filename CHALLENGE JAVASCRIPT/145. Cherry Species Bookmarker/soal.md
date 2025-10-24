# 🍒 Cherry Species Bookmarker

## Gambaran Umum Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mengorganisir koleksi nama spesies cherry dan menambahkan indikator bookmark ke spesies tertentu.

---

## 📋 Spesifikasi Function

### Nama Function
```javascript
cherryBookmarker(cherrySpecies, bookmarkSpecies)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `cherrySpecies` | `Array<string>` | Array yang berisi string nama-nama spesies cherry |
| `bookmarkSpecies` | `String` | String yang merepresentasikan spesies yang akan di-bookmark |

### Return Value

- **Tipe:** `Array<string>`
- **Deskripsi:** Array baru yang berisi spesies cherry yang terorganisir dengan indikator bookmark

---

## 🎯 Persyaratan Tugas

Function Anda harus melakukan operasi berikut:

1. **Inisialisasi** array kosong baru untuk menyimpan hasil
2. **Iterasi** melalui array `cherrySpecies`
3. **Tambahkan** setiap nama spesies ke array baru
4. **Periksa** apakah spesies saat ini cocok dengan `bookmarkSpecies`
   - Jika cocok, gabungkan `" (Bookmarked)"` ke nama spesies tersebut
5. **Berhenti** menambahkan spesies setelah spesies yang di-bookmark (gunakan statement `break`)
6. **Return** array baru dengan spesies yang terorganisir dan ter-bookmark

---

## 💡 Poin Penting

- ✅ Hanya sertakan spesies hingga dan termasuk spesies yang di-bookmark
- ✅ Tambahkan suffix `" (Bookmarked)"` ke spesies yang cocok
- ✅ Gunakan statement `break` untuk menghentikan iterasi setelah menemukan bookmark
- ✅ Return array baru (jangan modifikasi array original)

---

## 📝 Contoh

```javascript
// Input
const species = ["Bing", "Rainier", "Montmorency", "Sweetheart", "Lapins"];
const bookmark = "Montmorency";

// Pemanggilan function
cherryBookmarker(species, bookmark);

// Output yang diharapkan
["Bing", "Rainier", "Montmorency (Bookmarked)"]
```

---

## 🔍 Langkah-Langkah Implementasi

1. Buat array result yang kosong
2. Loop melalui setiap spesies dalam array input
3. Tambahkan spesies saat ini ke array result
4. Periksa apakah cocok dengan spesies bookmark
5. Jika ya, tambahkan `" (Bookmarked)"` dan break
6. Return array result

---

**Semoga berhasil dengan implementasi Anda! 🚀**
