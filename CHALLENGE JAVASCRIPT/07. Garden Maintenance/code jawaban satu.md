# 🌱 Garden Maintenance - Pemeliharaan Kebun

## 📋 **Deskripsi Masalah**

Kita diminta untuk membuat fungsi `maintainGarden` yang mensimulasikan pemeliharaan kebun dengan dua aktivitas utama:
- 💧 **Menyiram tanaman** di bedeng kebun
- ✂️ **Memangkas pagar tanaman** (hedge)

---

## 🎯 **Parameter Input**

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `gardenBed` | string | `'w'` = tanaman sudah disiram<br>`'d'` = tanaman masih kering | `"wwdwddd"` |
| `hedge` | string | `'g'` = bagian sudah dipangkas<br>`'u'` = bagian belum dipangkas | `"gguuugg"` |

---

## 🔄 **Proses Pemeliharaan**

### 1️⃣ **Menyiram Bedeng Kebun**
```
Input:  "wwdwddd"
Proses: Ganti semua 'd' menjadi 'w'
Output: "wwwwwww"
```

### 2️⃣ **Memangkas Pagar Tanaman**
```
Input:  "gguuugg"
Proses: Balik urutan semua substring 'u' yang berurutan
        "gg[uuu]gg" → "gg[uuu]gg" (uuu dibalik = uuu)
Output: "gguuugg"
```

**Contoh lebih jelas:**
```
Input:  "gguugguuuugg"
Proses: "gg[uu]gg[uuuu]gg"
        - "uu" dibalik = "uu"
        - "uuuu" dibalik = "uuuu"
Output: "gguugguuuugg"
```

---

## 💻 **Implementasi Kode**

```javascript
function maintainGarden(gardenBed, hedge) {
    // 1. Siram semua tanaman kering (d → w)
    const wateredBed = gardenBed.replace(/d/g, 'w');
    
    // 2. Pangkas pagar dengan membalik substring 'u'
    let trimmedHedge = '';
    let i = 0;
    
    while (i < hedge.length) {
        if (hedge[i] === 'g') {
            // Jika 'g', langsung tambahkan
            trimmedHedge += 'g';
            i++;
        } else {
            // Jika 'u', kumpulkan semua 'u' berurutan
            let uString = '';
            let j = i;
            while (j < hedge.length && hedge[j] === 'u') {
                uString += 'u';
                j++;
            }
            // Balik urutan substring 'u' dan tambahkan
            trimmedHedge += uString.split('').reverse().join('');
            i = j;
        }
    }
    
    return [wateredBed, trimmedHedge];
}
```

---

## 🧪 **Contoh Penggunaan**

```javascript
// Test Case 1
console.log(maintainGarden("dwdw", "gugu"));
// Output: ["wwww", "gugu"]

// Test Case 2  
console.log(maintainGarden("wwddd", "gguuugg"));
// Output: ["wwwww", "gguuugg"]

// Test Case 3
console.log(maintainGarden("dddwww", "uugguu"));
// Output: ["wwwwww", "uugguuu"]
```

---

## 🔍 **Penjelasan Langkah Demi Langkah**

### **Langkah 1: Menyiram Bedeng**
- Gunakan `replace(/d/g, 'w')` untuk mengganti semua karakter 'd' dengan 'w'
- `/d/g` adalah regex yang mencari semua kemunculan huruf 'd'

### **Langkah 2: Memangkas Pagar**
1. **Iterasi** melalui setiap karakter di string `hedge`
2. Jika karakter adalah **'g'**, langsung tambahkan ke hasil
3. Jika karakter adalah **'u'**:
   - Kumpulkan semua 'u' yang berurutan
   - Balik urutan substring tersebut
   - Tambahkan ke hasil

### **Langkah 3: Return Array**
- Kembalikan array dengan 2 elemen: `[bedengTersiram, pagarTerpangkas]`

---

## ⚡ **Tips Optimasi**

```javascript
// Versi lebih singkat untuk membalik substring 'u'
function maintainGarden(gardenBed, hedge) {
    const wateredBed = gardenBed.replace(/d/g, 'w');
    const trimmedHedge = hedge.replace(/u+/g, match => 
        match.split('').reverse().join('')
    );
    
    return [wateredBed, trimmedHedge];
}
```

**Penjelasan regex `u+`:**
- `u+` = mencari satu atau lebih huruf 'u' berurutan
- `match` = substring yang ditemukan (misal: "uuu")
- Fungsi callback membalik urutan match tersebut

---

## 🎉 **Kesimpulan**

Fungsi `maintainGarden` mensimulasikan pemeliharaan kebun dengan:
1. 💧 **Menyiram** semua tanaman kering
2. ✂️ **Memangkas** pagar dengan teknik pembalikan substring

Fungsi ini mengembalikan array berisi bedeng yang sudah disiram dan pagar yang sudah dipangkas rapi!
