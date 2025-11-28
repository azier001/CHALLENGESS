# 🏖️ Beach Bag Packing Challenge

<div align="center">

**Difficulty Level:** `Medium` 🌊

</div>

---

## 📋 Challenge Description

Create a function named `packBeachBag` that intelligently manages your beach trip packing list by merging item recommendations, removing duplicates, and adapting to weather conditions.

---

## 🎯 Function Signature

```javascript
packBeachBag(initialItems, friendRecommendations, weatherCondition)
```

---

## 📝 Implementation Steps

### Step 1️⃣: Merge Item Lists
Combine `initialItems` and `friendRecommendations` into a single array.

### Step 2️⃣: Remove Duplicates
Filter out duplicate items, keeping only unique entries.

### Step 3️⃣: Apply Weather-Based Logic
Adjust the packing list based on the `weatherCondition`:

#### ☀️ **Sunny Weather**
- Add `"sunscreen"` if not already included

#### 💨 **Windy Weather**
- Ensure `"hat"` is included in the list

#### 🌧️ **Rainy Weather**
- Add `"umbrella"` to the list
- Remove non-waterproof items:
  - `"camera"`
  - `"book"`

### Step 4️⃣: Sort Alphabetically
Arrange all items in alphabetical order (A-Z).

### Step 5️⃣: Return the Final List
Return the processed and sorted array.

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `initialItems` | `array` | Items initially planned to pack |
| `friendRecommendations` | `array` | Items recommended by a friend |
| `weatherCondition` | `string` | Weather condition: `"sunny"`, `"windy"`, or `"rainy"` |

---

## 📤 Return Value

**Type:** `array`

Returns a sorted array of strings representing the final list of items to pack, arranged alphabetically.

---

## 💡 Example Usage

```javascript
const initial = ["towel", "sunglasses", "book"];
const recommendations = ["water bottle", "sunglasses", "camera"];
const weather = "sunny";

const packedBag = packBeachBag(initial, recommendations, weather);
// Expected output: ["book", "camera", "sunglasses", "sunscreen", "towel", "water bottle"]
```

---

## ✅ Key Requirements

- ✨ **Unique items only** - no duplicates
- 🌤️ **Weather-aware** - adapts to conditions
- 🔤 **Alphabetically sorted** - easy to read
- 🎒 **Smart filtering** - removes inappropriate items for rainy weather

---

<div align="center">

**Happy Coding!** 🚀

</div>
