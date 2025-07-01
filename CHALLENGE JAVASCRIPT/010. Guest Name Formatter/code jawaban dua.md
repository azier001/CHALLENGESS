
# Penjelasan Fungsi `formatGuestNames`

Fungsi `formatGuestNames` digunakan untuk memformat daftar nama tamu menjadi bentuk kalimat yang lebih enak dibaca.

## Kode Fungsi

```javascript
function formatGuestNames(guestNames) {
  const names = guestNames.split(',');
  const length = names.length;

  if (length === 1) {
    return names[0];
  } else if (length === 2) {
    return names.join(' and ');
  } else {
    const allButLast = names.slice(0, -1).join(', ');

    const last = names[length - 1];

    return `${allButLast}, and ${last}`;
  }
}
```

## Penjelasan

Fungsi ini menerima satu parameter berupa **string nama-nama tamu yang dipisahkan dengan koma**, lalu memformatnya sebagai berikut:

1. **Jika hanya ada satu nama:**
   - Langsung dikembalikan tanpa perubahan.
   - Contoh: `"Ali"` → `"Ali"`

2. **Jika ada dua nama:**
   - Digabungkan dengan kata **"and"**.
   - Contoh: `"Ali,Budi"` → `"Ali and Budi"`

3. **Jika ada lebih dari dua nama:**
   - Semua nama kecuali yang terakhir digabungkan dengan tanda koma `,`.
   - Nama terakhir ditambahkan dengan kata **"and"** di depannya.
   - Contoh: `"Ali,Budi,Citra"` → `"Ali, Budi, and Citra"`

## Contoh Penggunaan

```javascript
formatGuestNames("Ali");                // "Ali"
formatGuestNames("Ali,Budi");           // "Ali and Budi"
formatGuestNames("Ali,Budi,Citra");     // "Ali, Budi, and Citra"
```

## Kesimpulan

Fungsi ini sangat berguna untuk menampilkan daftar nama tamu dalam format kalimat yang lebih natural dan mudah dibaca.
