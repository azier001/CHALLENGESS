# 🌱 Community Garden Inventory

> **Difficulty Level:** `Easy`

---

## 📋 Challenge Description

Create a function named `gardenInventory` that helps a weathered peacekeeper manage the community garden's inventory by comparing plant names and organizing them into different sections.

The function compares existing plants with newly arriving plants, identifying duplicates and organizing the inventory efficiently.

---

## 🔧 Function Specification

### Function Name
```javascript
gardenInventory(currentPlants, newPlants)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `currentPlants` | `array` | An array of strings representing the names of plants currently in the garden |
| `newPlants` | `array` | An array of strings representing the names of new plants to be added |

### Return Value

The function returns an **object** with the following structure:

```javascript
{
  existingPlants: [...],  // Array of strings
  newPlants: [...],       // Array of strings
  totalPlants: 0          // Integer
}
```

#### Return Object Keys

- **`existingPlants`**: An array of strings containing plant names that are already in the garden (duplicates from the new plants list)

- **`newPlants`**: An array of strings containing plant names that are new and will be added to the garden

- **`totalPlants`**: An integer representing the total number of unique plants after adding the new ones

---

## 💡 Implementation Tips

- Use **string comparison** to check if a plant already exists in the garden
- Use **arrays** to organize and store the plant information
- Consider case sensitivity when comparing plant names
- Ensure no duplicate entries in the final count

---

## 📝 Example Usage

```javascript
const current = ['Rose', 'Tulip', 'Daisy'];
const incoming = ['Tulip', 'Sunflower', 'Rose', 'Lily'];

const result = gardenInventory(current, incoming);

console.log(result);
// Expected output:
// {
//   existingPlants: ['Tulip', 'Rose'],
//   newPlants: ['Sunflower', 'Lily'],
//   totalPlants: 5
// }
```

---

## 🎯 Key Concepts

- Array manipulation
- String comparison
- Object creation and property assignment
- Set operations (union, intersection)
- Data organization and categorization

---

**Good luck with your implementation! 🌻**
