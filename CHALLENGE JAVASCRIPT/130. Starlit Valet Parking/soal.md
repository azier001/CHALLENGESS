# 🌟 Starlit Valet Parking

## Level Challenge
**Easy** ⭐

---

## 📖 Cerita

Sebagai valet di sebuah penginapan pedesaan yang tenang di malam berbintang, Anda perlu mengatur mobil-mobil yang datang di area parkir. Tugas Anda adalah membuat **pola zigzag** yang meniru kelap-kelip bintang di langit malam.

---

## 🎯 Tujuan

Buat sebuah function bernama `parkingValet` yang mengatur mobil dalam baris, dengan pola bergantian antara urutan **maju** dan **mundur** untuk setiap baris. Jika tidak ada cukup mobil untuk mengisi satu baris, gunakan tanda hubung (`'-'`) untuk merepresentasikan spot kosong.

---

## 📋 Spesifikasi Function

### Nama Function
```
parkingValet
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `licensePlates` | `string` | String berisi huruf kapital, masing-masing merepresentasikan plat nomor mobil |
| `spotsPerRow` | `number` | Jumlah spot parkir di setiap baris |

### Return Value

- **Type:** `Array<Array<string>>`
- **Deskripsi:** Array 2D berisi string, di mana setiap inner array merepresentasikan satu baris di area parkir

---

## 🔍 Persyaratan

1. ✅ Atur mobil dalam baris berdasarkan `spotsPerRow`
2. ✅ Pola bergantian antara urutan maju dan mundur untuk setiap baris (pola zigzag)
3. ✅ Isi baris yang tidak lengkap dengan tanda hubung (`'-'`)
4. ✅ Setiap plat nomor direpresentasikan oleh satu huruf kapital

---

## 💡 Contoh

```javascript
// Input
licensePlates: "ABCDEFGH"
spotsPerRow: 3

// Output
[
  ['A', 'B', 'C'],
  ['F', 'E', 'D'],
  ['G', 'H', '-']
]
```

### Representasi Visual

```
Baris 1 (Maju):    A → B → C
Baris 2 (Mundur):  F ← E ← D
Baris 3 (Maju):    G → H → -
```

Pola ini menciptakan efek zigzag seperti bintang yang berkelap-kelip di langit malam! ✨

---

## 🎨 Penjelasan Pola

- **Baris 1:** Urutan maju (kiri ke kanan)
- **Baris 2:** Urutan mundur (kanan ke kiri)
- **Baris 3:** Urutan maju (kiri ke kanan)
- **Baris 4:** Urutan mundur (kanan ke kiri)
- Dan seterusnya...

---

## 📝 Catatan

- Spot kosong harus direpresentasikan dengan karakter tanda hubung: `'-'`
- Setiap plat nomor adalah satu huruf kapital
- Pola zigzag bergantian di setiap baris baru

---

**Selamat Coding!** 🚗💨
