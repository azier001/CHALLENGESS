# 🌱 Dokumentasi Fungsi `checkPlantCellHealth`

## 📋 Deskripsi

Fungsi `checkPlantCellHealth` digunakan untuk **mengevaluasi kesehatan sel-sel tanaman** berdasarkan dua faktor utama: **tingkat integritas sel (`cellIntegrity`)** dan **keberadaan hama (`pestPresence`)**. Fungsi ini akan menilai setiap sel tanaman dan mengembalikan status kesehatannya dalam bentuk teks: `Healthy`, `At Risk`, atau `Unhealthy`.

---

## 🔧 Sintaks

```javascript
checkPlantCellHealth(cellIntegrity, pestPresence)
```

---

## 📊 Parameter

| Parameter       | Tipe Data       | Deskripsi                                                                                                                  |
| --------------- | --------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `cellIntegrity` | Array (Number)  | Array yang berisi nilai integritas setiap sel tanaman (0–100). Nilai lebih tinggi menunjukkan kondisi sel yang lebih baik. |
| `pestPresence`  | Array (Boolean) | Array yang berisi status keberadaan hama. `true` berarti ada hama, `false` berarti tidak ada hama.                         |

> ⚠️ **Catatan:** Kedua array harus memiliki panjang yang sama karena setiap indeks mewakili satu sel tanaman yang sama.

---

## 📈 Nilai Kembalian

**Tipe:** `Array (String)`

Fungsi ini mengembalikan array berisi status kesehatan untuk setiap sel dengan kemungkinan nilai berikut:

| Status        | Kondisi                                   | Deskripsi                                 |
| ------------- | ----------------------------------------- | ----------------------------------------- |
| `"Healthy"`   | Integritas > 75 dan tidak ada hama        | Sel dalam kondisi sehat dan stabil.       |
| `"At Risk"`   | Integritas antara 50–75 **atau** ada hama | Sel dalam kondisi berisiko atau terancam. |
| `"Unhealthy"` | Integritas < 50                           | Sel dalam kondisi buruk.                  |

---

## 🎯 Cara Kerja

1. Fungsi membuat array kosong `healthStatus` untuk menampung hasil.
2. Melakukan iterasi pada setiap elemen array `cellIntegrity`.
3. Pada setiap iterasi, fungsi memeriksa dua faktor: **nilai integritas** dan **keberadaan hama**.
4. Berdasarkan kondisi tersebut, fungsi menentukan status kesehatan:

   * **Healthy:** Integritas > 75 dan tidak ada hama.
   * **At Risk:** Integritas 50–75 atau ada hama.
   * **Unhealthy:** Integritas < 50.
5. Status yang dihasilkan dimasukkan ke dalam array `healthStatus` dan dikembalikan setelah iterasi selesai.

---

## 💻 Kode Fungsi

```javascript
function checkPlantCellHealth(cellIntegrity, pestPresence) {
  // Array untuk menyimpan status kesehatan setiap sel
  const healthStatus = [];

  // Iterasi melalui setiap sel tanaman
  for (let i = 0; i < cellIntegrity.length; i++) {
    const integrity = cellIntegrity[i];      // Nilai integritas sel
    const hasPest = pestPresence[i];         // Status keberadaan hama

    // Jika integritas > 75 dan tidak ada hama
    if (integrity > 75 && !hasPest) {
      healthStatus.push("Healthy");
    } 
    // Jika integritas 50–75 atau ada hama
    else if ((integrity >= 50 && integrity <= 75) || hasPest) {
      healthStatus.push("At Risk");
    } 
    // Jika integritas < 50
    else if (integrity < 50) {
      healthStatus.push("Unhealthy");
    }
  }

  // Kembalikan array berisi status kesehatan semua sel
  return healthStatus;
}
```

---

## 🧪 Contoh Penggunaan

### Contoh 1: Kasus Campuran

```javascript
const integritas = [90, 70, 40, 80, 55];
const hama = [false, false, false, true, false];

const hasil = checkPlantCellHealth(integritas, hama);
console.log(hasil);
```

**Output:**

```javascript
["Healthy", "At Risk", "Unhealthy", "At Risk", "At Risk"]
```

**Penjelasan:**

* Sel 1 (90, tanpa hama): Healthy
* Sel 2 (70, tanpa hama): At Risk
* Sel 3 (40, tanpa hama): Unhealthy
* Sel 4 (80, ada hama): At Risk
* Sel 5 (55, tanpa hama): At Risk

---

### Contoh 2: Semua Sel Sehat

```javascript
const integritas = [80, 85, 95];
const hama = [false, false, false];

const hasil = checkPlantCellHealth(integritas, hama);
console.log(hasil);
```

**Output:**

```javascript
["Healthy", "Healthy", "Healthy"]
```

---

### Contoh 3: Semua Sel Terinfeksi Hama

```javascript
const integritas = [95, 70, 45];
const hama = [true, true, true];

const hasil = checkPlantCellHealth(integritas, hama);
console.log(hasil);
```

**Output:**

```javascript
["At Risk", "At Risk", "At Risk"]
```

> Catatan: Keberadaan hama membuat semua sel berstatus **"At Risk"**, meskipun integritasnya tinggi.

---

## ⚠️ Catatan Penting

* Pastikan `cellIntegrity` dan `pestPresence` memiliki panjang yang sama.
* Nilai integritas sel sebaiknya dalam rentang **0–100**.
* Keberadaan hama akan **selalu membuat status menjadi "At Risk"**.
* Rentang **50–75** dianggap sebagai zona risiko.

---

## 🎓 Tips untuk Pemula

* Gunakan **loop for** untuk memeriksa setiap elemen array.
* Gunakan **if-else** untuk logika percabangan sederhana.
* Gunakan `.push()` untuk menambahkan hasil ke dalam array.
* Gunakan indeks `[i]` untuk mengakses data dari dua array yang saling berhubungan.

---

## 📚 Referensi Terkait

* [Array di JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
* [Loop For di JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [Conditional Statements](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)

---

Dibuat dengan ❤️ untuk pembelajaran JavaScript.
