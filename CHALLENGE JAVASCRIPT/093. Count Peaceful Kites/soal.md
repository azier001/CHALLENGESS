# 🪁 Count Peaceful Kites

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mengidentifikasi dan menghitung peaceful kites dalam deskripsi scene berdasarkan warna mereka.

---

## 🎯 Problem Statement

Tugas Anda adalah mengimplementasikan function bernama `countPeacefulKites` yang menganalisis deskripsi scene dan menghitung berapa banyak kites yang dianggap "peaceful" berdasarkan warnanya.

### Apa yang membuat kite peaceful?
Sebuah kite dianggap **peaceful** jika didahului oleh salah satu warna spesifik berikut:
- 🔴 Red
- 🔵 Blue  
- 🟢 Green
- 🟡 Yellow
- 🟣 Purple

---

## 📝 Spesifikasi Function

### Function Signature
```javascript
function countPeacefulKites(sceneDescription)
```

### Parameters
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `sceneDescription` | `string` | Deskripsi scene yang berisi penyebutan kites dan warna mereka |

### Return Value
- **Type:** `number` (integer)
- **Deskripsi:** Total jumlah peaceful kites yang ditemukan dalam scene

---

## 🔧 Requirements Implementasi

Ikuti langkah-langkah berikut untuk menyelesaikan challenge ini:

1. **🔤 Normalisasi Input**
   - Convert string input ke lowercase untuk matching yang case-insensitive

2. **🎨 Define Peaceful Colors**
   - Buat array yang berisi peaceful colors: `red`, `blue`, `green`, `yellow`, `purple`

3. **🔍 Search dan Count**
   - Iterate melalui setiap peaceful color
   - Hitung occurrences dari pattern `"[color] kite"` dalam string
   - Akumulasi total count

4. **📊 Return Result**
   - Return count final dari peaceful kites

---

## 💡 Contoh Penggunaan

```javascript
// Contoh deskripsi scene
const scene1 = "I saw a red kite flying high and a blue kite nearby";
const scene2 = "The black kite was aggressive, but the green kite was calm";
const scene3 = "Purple kite, yellow kite, and orange kite in the sky";

// Expected results
countPeacefulKites(scene1); // Returns: 2 (red kite + blue kite)
countPeacefulKites(scene2); // Returns: 1 (green kite only)
countPeacefulKites(scene3); // Returns: 2 (purple kite + yellow kite)
```

---

## 🎨 Pattern Matching

Function harus match dengan pattern yang tepat:
```
[peaceful_color] + space + "kite"
```

**Valid matches:**
- ✅ "red kite"
- ✅ "Blue Kite" (case-insensitive)
- ✅ "GREEN kite"

**Invalid matches:**
- ❌ "redkite" (tidak ada space)
- ❌ "red kites" (bentuk plural)
- ❌ "dark red kite" (ada descriptor tambahan)

---

## 🏷️ Tags
`String Processing` • `Pattern Matching` • `Array Iteration` • `Case Insensitive` • `Easy`
