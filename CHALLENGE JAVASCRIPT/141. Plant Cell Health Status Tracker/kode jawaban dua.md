# 🌱 Dokumentasi Fungsi `checkPlantCellHealth`

## 📋 Deskripsi

Fungsi `checkPlantCellHealth` digunakan untuk **memeriksa dan menentukan status kesehatan sel-sel tanaman** berdasarkan tingkat integritas sel (`cellIntegrity`) dan keberadaan hama (`pestPresence`). Fungsi ini akan **menganalisis setiap sel** dan memberikan label status kesehatan yang sesuai: `Healthy`, `At Risk`, atau `Unhealthy`.

---

## 🔧 Sintaks

```javascript
checkPlantCellHealth(cellIntegrity, pestPresence)
```

---

## 📊 Parameter

| Parameter       | Tipe Data       | Deskripsi                                                                                                                 |
| --------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `cellIntegrity` | Array (Number)  | Array berisi nilai integritas setiap sel tanaman (0–100). Nilai yang lebih tinggi menandakan kondisi sel yang lebih baik. |
| `pestPresence`  | Array (Boolean) | Array berisi status keberadaan hama. `true` berarti ada hama, `false` berarti tidak ada hama.                             |

> ⚠️ **Catatan:** Kedua array harus memiliki panjang yang sama karena setiap indeks mewakili sel yang sama.

---

## 📈 Nilai Kembalian

**Tipe:** `Array (String)`

Fungsi ini mengembalikan array berisi status kesehatan untuk setiap sel dengan kemungkinan nilai:

| Status        | Kondisi                            | Deskripsi                      |
| ------------- | ---------------------------------- | ------------------------------ |
| `"Healthy"`   | Integritas > 75 dan tidak ada hama | Sel dalam kondisi sehat.       |
| `"At Risk"`   | Ada hama **atau** integritas 50–75 | Sel berisiko atau terancam.    |
| `"Unhealthy"` | Integritas < 50 dan tidak ada hama | Sel dalam kondisi tidak sehat. |

---

## 🎯 Cara Kerja

Fungsi ini menggunakan **logika kondisional** untuk menentukan status kesehatan:

1. **Prioritas Pertama - At Risk:** Jika ada hama atau integritas sel di rentang 50–75.
2. **Prioritas Kedua - Healthy:** Jika integritas sel lebih dari 75.
3. **Prioritas Ketiga - Unhealthy:** Jika integritas sel kurang dari 50.

---

## 💻 Kode Fungsi

```javascript
function checkPlantCellHealth(cellIntegrity, pestPresence) {
  // Array untuk menyimpan status kesehatan setiap sel
  const healthStatus = [];
  
  // Iterasi melalui setiap sel tanaman
  for (let i = 0; i < cellIntegrity.length; i++) {

    // Cek jika ada hama ATAU integritas sel berada di rentang 50-75
    if (pestPresence[i] || (cellIntegrity[i] >= 50 && cellIntegrity[i] <= 75)) {
      healthStatus.push("At Risk");
    }
    // Cek jika integritas sel lebih dari 75 (kondisi sehat)
    else if (cellIntegrity[i] > 75) {
      healthStatus.push("Healthy");
    }
    // Jika tidak memenuhi kondisi di atas (integritas < 50)
    else {
      healthStatus.push("Unhealthy");
    }
  }
  
  // Kembalikan array berisi status kesehatan semua sel
  return healthStatus;
}
```

---

## 🧪 Contoh Penggunaan

### Contoh 1: Kasus Umum

```javascript
const integritas = [85, 60, 45, 90, 55];
const hama = [false, false, false, true, false];

const hasil = checkPlantCellHealth(integritas, hama);
console.log(hasil);
```

**Output:**

```javascript
["Healthy", "At Risk", "Unhealthy", "At Risk", "At Risk"]
```

**Penjelasan:**

* Sel 1 (85): Integritas > 75 dan tidak ada hama → **Healthy**
* Sel 2 (60): Integritas di rentang 50–75 → **At Risk**
* Sel 3 (45): Integritas < 50 dan tidak ada hama → **Unhealthy**
* Sel 4 (90): Ada hama meski integritas tinggi → **At Risk**
* Sel 5 (55): Integritas 50–75 → **At Risk**

---

### Contoh 2: Semua Sel Sehat

```javascript
const integritas = [80, 90, 100, 85];
const hama = [false, false, false, false];

const hasil = checkPlantCellHealth(integritas, hama);
console.log(hasil);
```

**Output:**

```javascript
["Healthy", "Healthy", "Healthy", "Healthy"]
```

---

### Contoh 3: Semua Sel Terserang Hama

```javascript
const integritas = [95, 80, 70];
const hama = [true, true, true];

const hasil = checkPlantCellHealth(integritas, hama);
console.log(hasil);
```

**Output:**

```javascript
["At Risk", "At Risk", "At Risk"]
```

> Catatan: Keberadaan hama menyebabkan semua sel berstatus **"At Risk"** meskipun integritasnya tinggi.

---

## ⚠️ Catatan Penting

* Panjang array `cellIntegrity` dan `pestPresence` **harus sama**.
* Nilai integritas sel sebaiknya berada pada rentang **0–100**.
* Keberadaan hama **selalu menghasilkan status "At Risk"**.
* Rentang **50–75** dianggap zona kritis.

---

## 🎓 Tips untuk Pemula

* Fungsi ini menggunakan **loop `for`** untuk memeriksa setiap sel satu per satu.
* Gunakan **kondisi `if-else`** untuk menentukan kategori kesehatan.
* Array `healthStatus` digunakan untuk menyimpan hasil dengan method `.push()`.
* Indeks `[i]` digunakan untuk mencocokkan data integritas dengan keberadaan hama pada sel yang sama.

---

## 📚 Referensi Terkait

* [Array di JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
* [Loop For di JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [Conditional Statements](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)

---

Dibuat dengan ❤️ untuk pembelajaran JavaScript.
