## Implementation: arrangeFlowerbed

```javascript
function arrangeFlowerbed(flowerbed, newPlants) {
  let count = 0;

  for (let i = 0; i < flowerbed.length && count < newPlants; i++) {
    // Cek apakah slot saat ini kosong, slot sebelumnya juga kosong (atau tidak ada),
    // dan slot setelahnya juga kosong (atau tidak ada)
    if (
      flowerbed[i] === 0 &&
      (i === 0 || flowerbed[i - 1] === 0) &&
      (i === flowerbed.length - 1 || flowerbed[i + 1] === 0)
    ) {
      flowerbed[i] = 1; // Tanam tanaman
      count++;          // Tambahkan ke jumlah tanaman yang berhasil ditanam
    }
  }

  return flowerbed; // Kembalikan flowerbed yang telah dimodifikasi
}
