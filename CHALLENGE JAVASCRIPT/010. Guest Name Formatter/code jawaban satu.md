
# 🎉 Guest Name Formatter in JavaScript

## 📝 Penjelasan Singkat 

Fungsi `formatGuestNames` digunakan untuk memformat daftar nama tamu agar terlihat lebih natural saat ditampilkan.

### Cara kerja:
- Jika hanya ada **1 nama**, tampilkan langsung.
- Jika ada **2 nama**, hubungkan dengan kata _"and"_ (contoh: `Alice and Bob`).
- Jika ada **lebih dari 2 nama**, gabungkan semua nama dengan koma dan tambahkan _"and"_ sebelum nama terakhir (contoh: `Alice, Bob, and Charlie`).

Fungsi ini sangat berguna untuk menampilkan daftar nama dengan cara yang mudah dibaca, seperti saat mencetak undangan, daftar peserta, atau notifikasi.

---

## 📌 Function Code

```javascript
function formatGuestNames(guestNames) {
  const splitNames = guestNames.split(',');

  if (splitNames.length === 1) {
    return guestNames;
  } else if (splitNames.length === 2) {
    return splitNames.join(' and ');
  } else {
    const excludeLastNames = splitNames.slice(0, -1).join(', ');

    const lastName = splitNames.slice(-1);

    return excludeLastNames + ', and ' + lastName;
  }
}

const hasil = formatGuestNames('Alice');
const hasil2 = formatGuestNames('Alice,Bob');
const hasil3 = formatGuestNames('Alice,Bob,Charlie');
const hasil4 = formatGuestNames('Alice,Bob,Charlie,David');
const hasil5 = formatGuestNames('Alice,Bob,Charlie,David,Eve,Frank');

console.log(hasil);
console.log(hasil2);
console.log(hasil3);
console.log(hasil4);
console.log(hasil5);
```

## ✅ Sample Output

```bash
Alice
Alice and Bob
Alice, Bob, and Charlie
Alice, Bob, Charlie, and David
Alice, Bob, Charlie, David, Eve, and Frank
```


