# 🐚 Tantangan Katalog Kerang Paleontolog

## 📋 Ringkasan Challenge

**Level Kesulitan:** `Easy`

Buat sebuah function yang membantu paleontolog mengorganisir penemuan kerang mereka menjadi sistem katalog yang komprehensif.

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `processSeashells` yang mensimulasikan pemeriksaan paleontolog terhadap kerang kuno yang ditemukan di pantai. Function tersebut harus memproses data kerang dengan membalik urutan, menggabungkan, dan mengkatalog temuan.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function processSeashells(seashells, keyword)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `seashells` | `Array<string>` | Sebuah array string, dimana setiap string merepresentasikan nama kerang unik yang ditemukan paleontolog |
| `keyword` | `string` | Sebuah string yang merepresentasikan term yang menarik bagi paleontolog |

---

## 📝 Persyaratan

Function harus melakukan operasi berikut **secara berurutan**:

1. **🔄 Membalik** urutan nama kerang dalam array
2. **🔗 Menggabungkan** semua nama kerang menjadi single string
   - Gunakan tanda hubung (`-`) sebagai separator antara setiap nama
3. **➕ Menambahkan** `keyword` di akhir string yang sudah digabungkan
   - Gunakan underscore (`_`) untuk memisahkan keyword dari nama-nama yang digabungkan

---

## 📤 Return Value

- **Tipe:** `string`
- **Deskripsi:** Katalog kerang yang telah diproses dengan keyword yang ditambahkan

---

## 💡 Contoh

### Input:
```javascript
const seashells = ["Conch", "Scallop", "Whelk", "Oyster"];
const keyword = "Atlantic";
```

### Langkah-langkah Proses:
1. **Reverse:** `["Oyster", "Whelk", "Scallop", "Conch"]`
2. **Concatenate:** `"Oyster-Whelk-Scallop-Conch"`
3. **Append keyword:** `"Oyster-Whelk-Scallop-Conch_Atlantic"`

### Expected Output:
```javascript
"Oyster-Whelk-Scallop-Conch_Atlantic"
```

---

## 🔍 Poin Penting yang Perlu Diingat

- ✅ Urutan operasi sangat penting
- ✅ Gunakan separator khusus: `-` untuk kerang, `_` untuk keyword
- ✅ Tangani edge case (array kosong, string kosong)
- ✅ Pastikan function mengembalikan string

---

## 🏷️ Tags

`Array Manipulation` • `String Processing` • `Data Organization` • `Algorithm Practice`
