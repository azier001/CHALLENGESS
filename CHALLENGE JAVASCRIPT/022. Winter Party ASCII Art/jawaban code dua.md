# 🎉 `winter_party_scene(guests, snowflakes)`

Membuat tampilan seni ASCII (ASCII Art) pesta musim dingin yang menyenangkan dengan tamu berbentuk stick figure dan hiasan kepingan salju.

---

## 🧾 Deskripsi

Fungsi `winter_party_scene` menghasilkan sebuah string yang menggambarkan adegan pesta musim dingin menggunakan karakter-karakter ASCII. Fungsi ini dirancang untuk menampilkan:

* Judul pesta yang terpusat
* Baris kepingan salju di atas dan bawah
* Tamu dalam bentuk stick figure
* Lantai menggunakan garis bawah (`_`)

---

## 🔧 Parameter

| Nama         | Tipe   | Deskripsi                                      |
| ------------ | ------ | ---------------------------------------------- |
| `guests`     | Number | Jumlah tamu dalam pesta (antara 1 hingga 10)   |
| `snowflakes` | Number | Jumlah kepingan salju di atas dan bawah (0–20) |

---

## 🎭 Karakter yang Digunakan

| Karakter | Arti           |    |            |
| -------- | -------------- | -- | ---------- |
| `*`      | Kepingan salju |    |            |
| `o`      | Kepala tamu    |    |            |
| \`       |                | \` | Badan tamu |
| `/ \`    | Kaki tamu      |    |            |
| `_`      | Lantai         |    |            |

---

## 🔍 Contoh Output

Jika dipanggil dengan `winter_party_scene(5, 20)`, hasilnya:

```
        Winter Party!        
********************        
   o   o   o   o   o        
  ||  ||  ||  ||  ||        
 / \ / \ / \ / \ / \        
____________________________
********************        
```

---

## 🧠 Penjelasan untuk Pemula

Fungsi ini bekerja langkah demi langkah sebagai berikut:

1. **Membuat judul** yang ditengah menggunakan `padStart` dan `padEnd`.
2. **Membuat baris salju** sebanyak `snowflakes`, lalu dilengkapi hingga panjang tetap dengan `padEnd`.
3. **Membuat 3 baris figur tamu**:

   * Baris pertama adalah kepala (`o`)
   * Baris kedua adalah badan (`||`)
   * Baris ketiga adalah kaki (`/ \`)
4. **Menambahkan lantai** dengan karakter `_` sebanyak lebar tertentu.
5. **Menambahkan kembali baris salju** di bagian bawah.
6. Semua bagian digabungkan menjadi satu string dengan pemisah baris (`\n`).

Fungsi ini cocok untuk belajar dasar:

* Pengulangan (looping)
* Pemrosesan string
* Tata letak dengan pemformatan

---

## 💻 Kode Asli

```javascript
function winter_party_scene(guests, snowflakes) {
  const width = 30;
  let scene = [];

  // Header
  scene.push("Winter Party!".padStart((width + 13) / 2).padEnd(width));

  // Top snowflakes
  let snowflakeLine = "*".repeat(snowflakes).padEnd(width);
  scene.push(snowflakeLine);

  // Guests
  for (let i = 0; i < 3; i++) {
    let line = "";
    for (let j = 0; j < guests; j++) {
      if (i === 0) line += " o ";
      else if (i === 1) line += "||"; 
      else line += "/ \\\";
      line += " ";
    }
    scene.push(line.trim().padStart((width + line.trim().length) / 2).padEnd(width));
  }

  // Floor
  scene.push("_".repeat(width));

  // Bottom snowflakes
  scene.push(snowflakeLine);

  return scene.join("\n");
}
```
