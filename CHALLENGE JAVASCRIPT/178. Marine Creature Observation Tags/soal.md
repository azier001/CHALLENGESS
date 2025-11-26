# 🐠 Marine Creature Observation Tags

## Gambaran Challenge

**Tingkat Kesulitan:** `Easy` 🟢

---

## 📋 Pernyataan Masalah

Tulis sebuah function bernama `createObservationTags` yang memproses array dari nama-nama makhluk laut dan menghasilkan tag observasi lapangan yang terstandarisasi untuk keperluan penelitian.

### Cara Kerja

Function ini harus:
- Mengambil **4 karakter pertama** dari setiap nama makhluk laut
- Mengubah karakter tersebut menjadi **UPPERCASE**
- Mengembalikan array dari tag observasi yang telah diformat

---

## 🔧 Spesifikasi Function

### Function Signature

```javascript
createObservationTags(creatures)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `creatures` | `Array<string>` | Sebuah array yang berisi nama-nama makhluk laut sebagai string |

### Returns

- **Type:** `Array<string>`
- **Format:** Sebuah array dari tag observasi uppercase, masing-masing berisi 4 karakter pertama dari nama makhluk

---

## 💡 Contoh

### Input
```javascript
["Brittle Star", "Starfish", "Jellyfish"]
```

### Output
```javascript
["BRIT", "STAR", "JELL"]
```

---

## 🎯 Perilaku yang Diharapkan

1. Ambil setiap nama makhluk dari input array
2. Ekstrak hanya 4 karakter pertama
3. Ubah karakter tersebut menjadi uppercase
4. Kumpulkan semua tag ke dalam array baru
5. Return array hasil tersebut

---

## 📝 Catatan

- Pastikan penanganan nama makhluk yang tepat
- Tag observasi harus selalu sepanjang 4 karakter (jika memungkinkan)
- Semua output harus dalam format uppercase
- Pertahankan urutan yang sama dengan input array

---

> **Tip:** Pikirkan tentang metode manipulasi string yang dapat membantu Anda mengekstrak substring dan mengubah case-nya!
