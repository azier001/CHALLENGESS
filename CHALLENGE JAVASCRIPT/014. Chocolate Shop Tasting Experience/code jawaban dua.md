# 🍫 Dokumentasi Fungsi `chocolateTasting`

## 📌 Deskripsi Singkat
Fungsi `chocolateTasting` digunakan untuk membuat pengalaman mencicipi cokelat berdasarkan daftar rasa yang tersedia dan rasa favorit pengguna. Fungsi ini akan mengembalikan teks deskriptif yang menyebutkan rasa-rasa cokelat yang dicicipi, dimulai dari rasa favorit pengguna jika ada.

---

## 🧠 Cara Kerja Fungsi
```javascript
function chocolateTasting(flavors, favorite) {
  const favoriteIndex = flavors.indexOf(favorite);
  let tastedFlavors;

  if (favoriteIndex === -1 || favoriteIndex === flavors.length - 1) {
    tastedFlavors = flavors;
  } else {
    tastedFlavors = flavors.slice(favoriteIndex);
  }

  const tastedFlavorsString = tastedFlavors.join(' and ');

  return `Starting with ${favorite}, you tasted: ${tastedFlavorsString}`;
}
```

---

## 📥 Parameter
| Nama         | Tipe     | Deskripsi                                          |
|--------------|----------|----------------------------------------------------|
| `flavors`    | Array    | Daftar rasa cokelat yang tersedia                  |
| `favorite`   | String   | Rasa cokelat favorit yang dipilih oleh pengguna   |

---

## 🔁 Proses Logika
1. Mencari indeks dari rasa favorit dalam array `flavors`.
2. Jika rasa favorit tidak ditemukan atau berada di urutan terakhir:
   - Semua rasa dalam `flavors` akan digunakan.
3. Jika ditemukan dan bukan yang terakhir:
   - Daftar rasa dimulai dari rasa favorit hingga akhir.
4. Rasa-rasa tersebut digabung menjadi satu string dipisahkan dengan "and".
5. Mengembalikan kalimat deskriptif tentang rasa-rasa yang dicicipi.

---

## ✅ Hasil Keluaran
Fungsi akan mengembalikan kalimat string seperti:
```
Starting with [favorite], you tasted: [daftar rasa yang dicicipi]
```

---

## 🔍 Contoh Penggunaan
```javascript
console.log(chocolateTasting(['milk', 'dark', 'white', 'caramel'], 'dark'));
// Output: "Starting with dark, you tasted: dark and white and caramel"

console.log(chocolateTasting(['vanilla', 'strawberry', 'mint'], 'vanilla'));
// Output: "Starting with vanilla, you tasted: vanilla and strawberry and mint"

console.log(chocolateTasting(['hazelnut', 'almond', 'coconut'], 'pistachio'));
// Output: "Starting with pistachio, you tasted: hazelnut and almond and coconut"
```

---

## 💡 Catatan
- Fungsi ini tetap memberikan pengalaman mencicipi lengkap jika rasa favorit tidak ditemukan.
- Cocok untuk digunakan dalam aplikasi belajar interaktif, pemilihan rasa, atau simulasi cerita pengguna.

---

## 🎯 Kegunaan
Dengan tampilan narasi yang menarik, fungsi ini dapat digunakan untuk memperkaya pengalaman pengguna dalam memilih preferensi dari sebuah daftar.
