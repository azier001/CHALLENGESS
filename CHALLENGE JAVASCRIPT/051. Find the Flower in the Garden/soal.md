# 🌸 Menemukan Bunga di Taman

## 📋 Gambaran Challenge

**Level Kesulitan:** `Easy` 🟢

Buat function yang mencari melalui array taman untuk menemukan bunga tertentu dan mengembalikan posisinya.

---

## 🎯 Tujuan

Implementasikan function bernama `findFlower` yang:

- **Menerima:** Array string (`garden`) dan target string (`flower`)
- **Mengembalikan:** Index dari kemunculan pertama bunga tersebut
- **Fallback:** Mengembalikan `-1` jika bunga tidak ditemukan

---

## 📝 Spesifikasi Function

### Function Signature
```javascript
function findFlower(garden, flower)
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `garden` | `Array<string>` | Array yang berisi nama-nama bunga |
| `flower` | `string` | Bunga yang ingin dicari |

### Return Value
| Type | Deskripsi |
|------|-----------|
| `number` | Index bunga (berbasis 0) atau `-1` jika tidak ditemukan |

---

## 💡 Contoh

### Sample Garden
```javascript
const garden = [
  'roses', 
  'tulips', 
  'dandelions', 
  'sunflowers', 
  'violets', 
  'daisies', 
  'daffodils', 
  'lilies', 
  'orchids'
];
```

### Test Cases
```javascript
// ✅ Ditemukan di index 5
findFlower(garden, 'daisies');  // → 5

// ✅ Ditemukan di index 7
findFlower(garden, 'lilies');   // → 7

// ❌ Tidak ditemukan
findFlower(garden, 'peonies');  // → -1
```

---

## 🔍 Perilaku yang Diharapkan

- **Case Sensitive:** Pencarian harus exact match
- **Kemunculan Pertama:** Mengembalikan index dari match pertama saja
- **Zero-based Indexing:** Index array dimulai dari 0
- **Tidak Ditemukan:** Mengembalikan `-1` ketika bunga tidak ada di garden

---

## 🌟 Tips

- Pertimbangkan menggunakan built-in array methods untuk pencarian yang efisien
- Ingat untuk menangani edge cases (array kosong, null values)
- Test dengan berbagai nama bunga untuk memastikan akurasi

---

*Happy coding! 🚀*
