# 🍒 Cherry Species Bookmarker

## Challenge Overview

**Difficulty Level:** `Easy`

Create a function that organizes a collection of cherry species names and adds a bookmark indicator to a specific species.

---

## 📋 Function Specification

### Function Name
```javascript
cherryBookmarker(cherrySpecies, bookmarkSpecies)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `cherrySpecies` | `Array<string>` | An array of strings representing different cherry species names |
| `bookmarkSpecies` | `String` | A string representing the species to be bookmarked |

### Return Value

- **Type:** `Array<string>`
- **Description:** A new array containing the organized cherry species with the bookmark indicator

---

## 🎯 Task Requirements

Your function should perform the following operations:

1. **Initialize** a new empty array to store the result
2. **Iterate** through the `cherrySpecies` array
3. **Add** each species name to the new array
4. **Check** if the current species matches the `bookmarkSpecies`
   - If it matches, concatenate `" (Bookmarked)"` to that species name
5. **Stop** adding more species after the bookmarked species (use `break` statement)
6. **Return** the new array with the organized and bookmarked species

---

## 💡 Key Points

- ✅ Only include species up to and including the bookmarked species
- ✅ Add `" (Bookmarked)"` suffix to the matching species
- ✅ Use the `break` statement to stop iteration after finding the bookmark
- ✅ Return a new array (do not modify the original)

---

## 📝 Example

```javascript
// Input
const species = ["Bing", "Rainier", "Montmorency", "Sweetheart", "Lapins"];
const bookmark = "Montmorency";

// Function call
cherryBookmarker(species, bookmark);

// Expected output
["Bing", "Rainier", "Montmorency (Bookmarked)"]
```

---

## 🔍 Implementation Steps

1. Create an empty result array
2. Loop through each species in the input array
3. Add the current species to the result array
4. Check if it matches the bookmark species
5. If yes, append `" (Bookmarked)"` and break
6. Return the result array

---

**Good luck with your implementation! 🚀**
