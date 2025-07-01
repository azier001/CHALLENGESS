# Arrange Flowerbed

## Challenge

**Difficulty:** Easy  
**Kesulitan:** Mudah

## Description

Create a function named `arrangeFlowerbed` that receives `flowerbed` and `newPlants` as parameters.  
**Buatlah sebuah fungsi bernama `arrangeFlowerbed` yang menerima parameter `flowerbed` dan `newPlants`.**

This function arranges new plants in the flowerbed ensuring **no two plants are adjacent**.  
**Fungsi ini menanam tanaman baru di flowerbed dengan memastikan bahwa **tidak ada dua tanaman yang bersebelahan**.**

The `flowerbed` array represents a row where:  
**Array `flowerbed` merepresentasikan barisan tempat tanam di mana:**

- `0` is an empty slot  
  **`0` adalah slot kosong**
- `1` is a slot with a plant  
  **`1` adalah slot yang sudah berisi tanaman**

You need to **modify the flowerbed array** by planting the given number of `newPlants` in empty slots (changing `0` to `1`) while ensuring no two plants are next to each other.  
**Anda harus **memodifikasi array flowerbed** dengan menanam sejumlah `newPlants` di slot kosong (mengubah `0` menjadi `1`) sambil memastikan tidak ada dua tanaman yang berdekatan.**

Start planting from the beginning of the `flowerbed` array.  
**Mulailah menanam dari awal array `flowerbed`.**

If there are not enough empty slots to accommodate all `newPlants` while maintaining the **non-adjacency rule**, stop planting and return the modified `flowerbed` array.  
**Jika tidak cukup slot kosong untuk menanam semua `newPlants` tanpa melanggar aturan tidak bersebelahan, hentikan penanaman dan kembalikan array `flowerbed` yang telah dimodifikasi.**

## Parameters

- `flowerbed` (`integer[]`): An array representing the flowerbed, where `0` indicates an empty slot and `1` indicates a slot with a plant.  
  **Array `flowerbed` (`integer[]`): Array yang merepresentasikan flowerbed, di mana `0` adalah slot kosong dan `1` adalah slot berisi tanaman.**

- `newPlants` (`integer`): The number of new plants to be planted in the flowerbed.  
  **`newPlants` (`integer`): Jumlah tanaman baru yang akan ditanam di flowerbed.**

## Returns

- (`integer[]`): The modified flowerbed array after planting the new plants while ensuring no adjacent plants.  
  **(`integer[]`): Array flowerbed yang telah dimodifikasi setelah menanam tanaman baru sambil memastikan tidak ada tanaman yang bersebelahan.**

## Example

```python
arrangeFlowerbed([1, 0, 0, 0, 1], 1)
# Output: [1, 0, 1, 0, 1]

arrangeFlowerbed([1, 0, 0, 0, 1], 2)
# Output: [1, 0, 1, 0, 1]  # Cannot plant the second one due to adjacency rule
# Tidak bisa menanam tanaman kedua karena melanggar aturan tanaman tidak boleh bersebelahan
