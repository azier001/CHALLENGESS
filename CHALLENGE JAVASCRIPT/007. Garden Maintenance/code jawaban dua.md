# 🌱 Garden Maintenance - Solusi Alternatif Ringkas

## 💻 **Kode Solusi**

```javascript
function maintainGarden(gardenBed, hedge) {
  const wateredGardenBed = gardenBed.replace(/d/g, 'w');
  
  const trimmedHedge = hedge.replace(/u+/g, match => match.split('').reverse().join(''));
  
  return [wateredGardenBed, trimmedHedge];
}
```

---

## 🔬 **Analisis Kode Baris per Baris**

### **Baris 1: Deklarasi Fungsi**
```javascript
function maintainGarden(gardenBed, hedge) {
```
- Membuat fungsi dengan nama `maintainGarden`
- Menerima 2 parameter: `gardenBed` (string) dan `hedge` (string)

### **Baris 2: Menyiram Bedeng Kebun**
```javascript
const wateredGardenBed = gardenBed.replace(/d/g, 'w');
```

| Komponen | Penjelasan | Contoh |
|----------|------------|---------|
| `replace()` | Method untuk mengganti karakter | `"hello".replace('l', 'x')` |
| `/d/g` | Regex pattern mencari semua 'd' | `/d/g` = semua huruf 'd' |
| `'w'` | Karakter pengganti | 'd' diganti dengan 'w' |

**Proses:**
```
Input:  "dwdwdd"
Regex:  /d/g mencari semua 'd'
        d w d w d d
        ↓   ↓   ↓ ↓
        w w w w w w
Output: "wwwwww"
```

### **Baris 3: Memangkas Pagar Tanaman**
```javascript
const trimmedHedge = hedge.replace(/u+/g, match => match.split('').reverse().join(''));
```

**Breakdown komponen:**

| Bagian | Fungsi | Contoh |
|--------|--------|---------|
| `/u+/g` | Cari grup 'u' berurutan | "uuu", "uu", "u" |
| `match =>` | Arrow function callback | `match` = grup yang ditemukan |
| `split('')` | Ubah string jadi array | "uuu" → ['u','u','u'] |
| `reverse()` | Balik urutan array | ['u','u','u'] → ['u','u','u'] |
| `join('')` | Gabung array jadi string | ['u','u','u'] → "uuu" |

---

## 🎯 **Visualisasi Proses Regex `/u+/g`**

### **Cara Kerja Pattern `/u+/g`:**

```javascript
/u+/g
│││ │
│││ └── g = global (cari semua kemunculan)
││└──── + = satu atau lebih karakter 'u'
│└───── u = huruf 'u'
└────── / = pembatas regex pattern
```

### **Proses Step-by-Step:**

```
Input hedge: "g g u u u g g u u g"
             │ │ └─┬─┘ │ │ └─┬┘ │
             │ │   │   │ │   │  │
Step 1:      │ │  "uuu" │ │  "uu" │  ← Regex menemukan grup 'u'
             │ │   │   │ │   │  │
Step 2:      │ │ ['u','u','u'] │ ['u','u'] ← split('')
             │ │   │   │ │   │  │
Step 3:      │ │ ['u','u','u'] │ ['u','u'] ← reverse() (sama karena palindrom)
             │ │   │   │ │   │  │
Step 4:      │ │  "uuu" │ │  "uu" │  ← join('')
             │ │   │   │ │   │  │
Result:     "g g u u u g g u u g"
```

---

## 🧪 **Contoh Eksekusi Detail**

### **Test Case 1:**
```javascript
maintainGarden("dwdw", "gugu");

// Proses gardenBed:
"dwdw".replace(/d/g, 'w') → "wwww"

// Proses hedge:
"gugu".replace(/u+/g, match => {
    // Iterasi 1: match = "u"
    return "u".split('').reverse().join('') // "u"
    // Iterasi 2: match = "u" 
    return "u".split('').reverse().join('') // "u"
}) → "gugu"

// Result: ["wwww", "gugu"]
```

### **Test Case 2:**
```javascript
maintainGarden("wwddd", "gguuugg");

// Proses gardenBed:
"wwddd".replace(/d/g, 'w') → "wwwww"

// Proses hedge:
"gguuugg".replace(/u+/g, match => {
    // Hanya 1 iterasi: match = "uuu"
    return "uuu".split('').reverse().join('') // "uuu"
}) → "gguuugg"

// Result: ["wwwww", "gguuugg"]
```

### **Test Case 3 (Lebih Kompleks):**
```javascript
maintainGarden("dddwww", "uuggguuuu");

// Proses gardenBed:
"dddwww".replace(/d/g, 'w') → "wwwwww"

// Proses hedge:
"uuggguuuu".replace(/u+/g, match => {
    // Iterasi 1: match = "uu"
    // "uu".split('') → ['u','u']
    // ['u','u'].reverse() → ['u','u'] 
    // ['u','u'].join('') → "uu"
    
    // Iterasi 2: match = "uuuu"  
    // "uuuu".split('') → ['u','u','u','u']
    // ['u','u','u','u'].reverse() → ['u','u','u','u']
    // ['u','u','u','u'].join('') → "uuuu"
}) → "uuggguuuu"

// Result: ["wwwwww", "uuggguuuu"]
```

---

## 🔍 **Mengapa Solusi Ini Elegant?**

### ✅ **Keunggulan:**

1. **Ringkas**: Hanya 3 baris kode inti
2. **Readable**: Setiap baris punya tujuan yang jelas
3. **Powerful**: Memanfaatkan kekuatan regex dan functional programming
4. **Efficient**: Regex engine sudah dioptimasi untuk pattern matching
5. **Maintainable**: Mudah dimodifikasi dan dipahami

### 🎯 **Teknik yang Digunakan:**

- **Regex Pattern Matching**: `/d/g` dan `/u+/g`
- **Arrow Function**: `match => ...`
- **Method Chaining**: `split('').reverse().join('')`
- **Functional Programming**: Callback function dalam `replace()`

---

## 🧠 **Konsep Penting untuk Dipahami**

### **1. Global Flag (`g`) dalam Regex**
```javascript
// Tanpa 'g' - hanya ganti yang pertama
"hello".replace(/l/, 'x') → "hexlo"

// Dengan 'g' - ganti semua
"hello".replace(/l/g, 'x') → "hexxo"
```

### **2. Quantifier `+` dalam Regex**
```javascript
/u/    → mencari tepat 1 huruf 'u'
/u+/   → mencari 1 atau lebih huruf 'u' berurutan
/u*/   → mencari 0 atau lebih huruf 'u' berurutan
```

### **3. Callback Function dalam replace()**
```javascript
string.replace(pattern, (match, index, fullString) => {
    // match = substring yang cocok dengan pattern
    // index = posisi match dalam string
    // fullString = string asli
    return "replacement";
});
```

---

## 🎉 **Kesimpulan**

Solusi alternatif ini menunjukkan kekuatan JavaScript modern dengan menggabungkan:
- **Regex** untuk pattern matching yang efisien
- **Functional programming** dengan arrow function
- **Method chaining** untuk transformasi data yang elegant

Kode ini tidak hanya berfungsi dengan baik, tetapi juga mudah dibaca dan dipelihara!
