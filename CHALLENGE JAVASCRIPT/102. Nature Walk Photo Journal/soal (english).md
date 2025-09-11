# 🌲 Nature Walk Photo Journal

## 📸 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that helps organize nature photography collections by categorizing photos based on their environmental tags.

---

## 🎯 Objective

Develop a function named `organizePhotos` that efficiently sorts and groups nature photographs according to their location tags, making it easier to browse collections by specific environments.

---

## 📋 Function Specification

### Function Name
```javascript
organizePhotos(tags, photos)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `tags` | Array of Strings | Contains the environmental tags for each photo |
| `photos` | Array of Strings | Contains the corresponding photo filenames |

> **Note:** The photo at index `i` in the `photos` array corresponds to the tag at index `i` in the `tags` array.

### Expected Tags
- 🌲 `'forest'` - Woodland and forest environments
- 🏞️ `'lake'` - Large body of water scenes  
- 🪷 `'pond'` - Small water body environments

---

## ✅ Requirements

The function should:

1. **Process Input Arrays**: Accept two arrays of equal length containing tags and photo names
2. **Group by Tags**: Create categories based on unique environmental tags
3. **Return Organized Data**: Output a dictionary/object structure where:
   - **Keys** = Unique tags from the input
   - **Values** = Arrays of photo names associated with each tag

---

## 📤 Expected Output

The function returns an **Object** (dictionary) with the following structure:

```javascript
{
  "forest": ["photo1.jpg", "photo3.jpg"],
  "lake": ["photo2.jpg", "photo5.jpg"],
  "pond": ["photo4.jpg"]
}
```

---

## 💡 Example Usage

```javascript
// Input arrays
const tags = ['forest', 'lake', 'forest', 'pond', 'lake'];
const photos = ['sunrise_trees.jpg', 'lake_reflection.jpg', 'autumn_path.jpg', 'lily_pond.jpg', 'sunset_water.jpg'];

// Function call
const organized = organizePhotos(tags, photos);

// Expected result
console.log(organized);
/*
{
  "forest": ["sunrise_trees.jpg", "autumn_path.jpg"],
  "lake": ["lake_reflection.jpg", "sunset_water.jpg"], 
  "pond": ["lily_pond.jpg"]
}
*/
```

---

## 🏆 Success Criteria

- ✅ Function correctly groups photos by their corresponding tags
- ✅ All unique tags appear as keys in the result object
- ✅ Photo arrays contain the correct filenames for each tag
- ✅ No photos are lost or duplicated in the organization process

---

*Happy coding and enjoy organizing your nature photography collection! 📷🌿*
