# 🍫 Dokumentasi Fungsi Chocolate Tasting

## Ringkasan
Fungsi `chocolateTasting` digunakan untuk membuat pengalaman mencicipi cokelat berdasarkan daftar rasa yang tersedia dan rasa favorit pengguna. Fungsi ini akan menghasilkan kalimat yang menjelaskan rasa apa saja yang dicicipi, dimulai dari rasa favorit tersebut (jika ada).

---

## 📌 Definisi Fungsi
```javascript
function chocolateTasting(flavors, favorite) {
    // Cari posisi (index) dari rasa favorit dalam daftar
    const favoriteIndex = flavors.indexOf(favorite);
    
    // Buat array baru berisi rasa dari rasa favorit sampai akhir
    let tastingArray;

    if (favoriteIndex === -1 || favoriteIndex === flavors.length - 1) {
        // Jika rasa favorit tidak ditemukan atau berada di posisi terakhir,
        // maka tampilkan semua rasa
        tastingArray = flavors;
    } else {
        // Jika ditemukan, ambil dari rasa favorit sampai akhir
        tastingArray = flavors.slice(favoriteIndex);
    }

    // Gabungkan semua rasa dengan " dan " sebagai penghubung
    const tastedFlavors = tastingArray.join(' and ');

    // Kembalikan kalimat hasil mencicipi
    return `Starting with your favorite ${favorite}, you tasted: ${tastedFlavors}`;
}
```

---

## 📥 Parameter
| Nama       | Tipe     | Penjelasan                                    |
|------------|----------|-----------------------------------------------|
| `flavors`  | `Array`  | Daftar semua rasa cokelat yang tersedia       |
| `favorite` | `String` | Rasa cokelat favorit dari pengguna            |

---

## ✅ Nilai Balikan
Fungsi ini mengembalikan teks (string) yang menjelaskan rasa-rasa yang dicicipi mulai dari rasa favorit pengguna.

---

## 🔍 Contoh Penggunaan
```javascript
console.log(chocolateTasting(['milk', 'dark', 'white', 'caramel'], 'dark'));
// Output: "Starting with your favorite dark, you tasted: dark and white and caramel"

console.log(chocolateTasting(['vanilla', 'strawberry', 'mint'], 'vanilla'));
// Output: "Starting with your favorite vanilla, you tasted: vanilla and strawberry and mint"

console.log(chocolateTasting(['cookies', 'cream', 'fudge'], 'fudge'));
// Output: "Starting with your favorite fudge, you tasted: cookies and cream and fudge"

console.log(chocolateTasting(['hazelnut', 'almond', 'coconut'], 'pistachio'));
// Output: "Starting with your favorite pistachio, you tasted: hazelnut and almond and coconut"
```

---

## 💡 Catatan Tambahan
- Jika rasa favorit tidak ada dalam daftar atau berada di posisi terakhir, maka fungsi akan mencicipi semua rasa yang ada.
- Cocok digunakan untuk membuat narasi menarik dalam aplikasi pencicipan atau pemilihan rasa.

---

## 🎯 Kegunaan
Fungsi ini cocok untuk digunakan dalam aplikasi edukatif atau hiburan yang ingin menampilkan pengalaman pengguna dalam bentuk cerita dari daftar yang mereka pilih.
