## Implementation: arrangeFlowerbed

```javascript
function arrangeFlowerbed(flowerbed, newPlants) {
  let i = 0;

  while (i < flowerbed.length && newPlants > 0) {
    // Jika slot saat ini kosong
    if (flowerbed[i] === 0) {
      // Periksa apakah slot sebelumnya kosong atau di awal array
      const prevEmpty = i === 0 || flowerbed[i - 1] === 0;

      // Periksa apakah slot setelahnya kosong atau di akhir array
      const nextEmpty = i === flowerbed.length - 1 || flowerbed[i + 1] === 0;

      // Jika slot sebelum dan sesudah juga kosong, maka aman untuk menanam
      if (prevEmpty && nextEmpty) {
        flowerbed[i] = 1; // Tanam di slot ini
        newPlants--;      // Kurangi jumlah tanaman yang perlu ditanam
        i++;              // Lewati satu slot untuk menjaga tidak bersebelahan
      }
    }
    i++; // Lanjut ke slot berikutnya
  }

  return flowerbed; // Kembalikan array flowerbed yang telah dimodifikasi
}
