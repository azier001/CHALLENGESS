# Arrange Flowerbed

## Challenge

**Difficulty:** Easy

## Description

Create a function named `arrangeFlowerbed` that receives `flowerbed` and `newPlants` as parameters.

This function arranges new plants in the flowerbed ensuring **no two plants are adjacent**.

The `flowerbed` array represents a row where:

- `0` is an empty slot
- `1` is a slot with a plant

You need to **modify the flowerbed array** by planting the given number of `newPlants` in empty slots (changing `0` to `1`) while ensuring no two plants are next to each other.

Start planting from the beginning of the `flowerbed` array.  
If there are not enough empty slots to accommodate all `newPlants` while maintaining the **non-adjacency rule**, stop planting and return the modified `flowerbed` array.

## Parameters

- `flowerbed` (`integer[]`): An array representing the flowerbed, where `0` indicates an empty slot and `1` indicates a slot with a plant.
- `newPlants` (`integer`): The number of new plants to be planted in the flowerbed.

## Returns
      
- (`integer[]`): The modified flowerbed array after planting the new plants while ensuring no adjacent plants.

## Example

```python
arrangeFlowerbed([1, 0, 0, 0, 1], 1)
# Output: [1, 0, 1, 0, 1]

arrangeFlowerbed([1, 0, 0, 0, 1], 2)
# Output: [1, 0, 1, 0, 1]  # Cannot plant the second one due to adjacency rule
