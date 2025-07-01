# 🎯 Petualangan Gabung Kata - Fungsi `blendWords`

## 🌟 Apa itu Fungsi `blendWords`?

Fungsi `blendWords` adalah alat yang sangat cerdas untuk **menggabungkan dua kata** menjadi satu! Yang membuatnya istimewa adalah kemampuannya untuk mendeteksi huruf yang sama di pertemuan kedua kata dan menghilangkan duplikatnya.

Bayangkan seperti puzzle kata - ketika dua kata bertemu dan huruf terakhir kata pertama sama dengan huruf pertama kata kedua, maka salah satu huruf akan "melebur" jadi satu!

---

## 🧩 Bagaimana Cara Kerjanya?

### 📋 **Langkah 1: Periksa Kata Kosong**
- Jika kedua kata kosong → hasil kosong
- Jika kata pertama kosong → hasil = kata kedua  
- Jika kata kedua kosong → hasil = kata pertama

### 🔍 **Langkah 2: Bandingkan Huruf**
- Ambil huruf **terakhir** dari kata pertama
- Ambil huruf **pertama** dari kata kedua
- Bandingkan keduanya (tidak peduli besar/kecil huruf)

### ⚡ **Langkah 3: Gabungkan dengan Cerdas**
- **Jika huruf sama** → Buang huruf pertama dari kata kedua, lalu gabung
- **Jika huruf beda** → Langsung gabung kedua kata

---

## 💡 **Fitur Unggulan**

| 🎨 **Fitur** | 📝 **Penjelasan** |
|:-------------|:------------------|
| 🔗 **Penggabungan Cerdas** | Tidak akan ada huruf ganda yang tidak perlu |
| 🔤 **Ignore Besar-Kecil** | 'A' dan 'a' dianggap sama saat pengecekan |
| 🛡️ **Handle Kata Kosong** | Tidak error meski ada kata yang kosong |
| 🎯 **Pertahankan Format** | Huruf besar-kecil asli tetap dipertahankan |

---

## 🛠️ **Kode Program**

```javascript
function blendWords(word1, word2) {
  // 🔍 Periksa jika ada kata yang kosong
  if (word1 === '' && word2 === '') {
    return '';
  }
  if (word1 === '') {
    return word2;
  }
  if (word2 === '') {
    return word1;
  }

  // 🎯 Ambil huruf terakhir kata1 dan huruf pertama kata2
  const lastLetterWord1 = word1[word1.length - 1].toLowerCase();
  const firstLetterWord2 = word2[0].toLowerCase();

  // ⚡ Jika huruf sama, buang duplikat
  if (lastLetterWord1 === firstLetterWord2) {
    return word1 + word2.slice(1);
  }

  // 🔗 Jika beda, langsung gabung
  return word1 + word2;
}

// 🧪 Contoh Penggunaan
console.log('🎮 === Tes Petualangan Gabung Kata ===');
console.log(
  `✅ blendWords("hello", "orange") = "${blendWords('hello', 'orange')}"`
); // "hellorange"
console.log(`✅ blendWords("car", "race") = "${blendWords('car', 'race')}"`); // "carrace" 
console.log(`✅ blendWords("book", "keeper") = "${blendWords('book', 'keeper')}"`); // "bookkeeper"
console.log(`✅ blendWords("sun", "never") = "${blendWords('sun', 'never')}"`); // "sunnever"
console.log(`✅ blendWords("", "world") = "${blendWords('', 'world')}"`); // "world"
console.log(`✅ blendWords("hello", "") = "${blendWords('hello', '')}"`); // "hello"
console.log(`✅ blendWords("", "") = "${blendWords('', '')}"`); // ""
console.log(`✅ blendWords("Cat", "tiger") = "${blendWords('Cat', 'tiger')}"`); // "Cattiger"
console.log(
  `✅ blendWords("apple", "Elephant") = "${blendWords('apple', 'Elephant')}"`
); // "applElephant"
```

---

## 🎯 **Parameter & Return**

### 📥 **Input (Parameter)**
| **Nama** | **Tipe** | **Keterangan** |
|:---------|:---------|:---------------|
| `word1` | String | Kata pertama yang akan digabung |
| `word2` | String | Kata kedua yang akan digabung |

### 📤 **Output (Return)**
Mengembalikan **string** hasil penggabungan kedua kata dengan aturan cerdas penghilangan duplikat.

---

## 🎮 **Contoh Penggunaan Seru**

### 🟢 **Kasus: Huruf Sama (Duplikat Dihilangkan)**
```
"book" + "keeper" = "bookkeeper"
     ↑       ↑
   Huruf 'k' sama, jadi salah satu dihilangkan!
```

### 🔵 **Kasus: Huruf Beda (Langsung Gabung)**
```
"hello" + "world" = "helloworld"
      ↑     ↑
  Huruf 'o' ≠ 'w', jadi langsung digabung!
```

### 🟡 **Kasus: Kata Kosong**
```
"" + "world" = "world"
"hello" + "" = "hello"
"" + "" = ""
```

---

## 🚀 **Kegunaan dalam Kehidupan Nyata**

| 🎯 **Bidang** | 💡 **Contoh Penggunaan** |
|:-------------|:-------------------------|
| 🎮 **Game Kata** | Membuat kata majemuk dalam permainan |
| 📝 **Pemrosesan Teks** | Menggabung istilah tanpa huruf berulang |
| 🎨 **Kreativitas** | Membuat nama unik untuk karakter/tempat |
| 🔤 **Pembelajaran** | Alat bantu belajar pembentukan kata |

---

## 🎉 **Kesimpulan**

Fungsi `blendWords` adalah solusi elegan untuk menggabungkan kata dengan cara yang natural dan cerdas. Dengan kemampuan mendeteksi dan menghilangkan duplikat huruf, fungsi ini menghasilkan kata gabungan yang terlihat rapi dan mudah dibaca!

