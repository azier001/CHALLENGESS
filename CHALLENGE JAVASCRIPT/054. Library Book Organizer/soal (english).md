# 📚 Library Book Organizer

## 🎯 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that organizes and formats book titles from different categories into a single, well-structured array.

---

## 📋 Function Specification

### Function Name
```javascript
organizeLibrary(scienceBooks, philosophyBooks)
```

### 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `scienceBooks` | `Array<string>` | An array of strings representing the titles of science books |
| `philosophyBooks` | `Array<string>` | An array of strings representing the titles of philosophy books |

### 🎯 Return Value
- **Type:** `Array<string>`
- **Description:** An array of strings where each string is a properly formatted book title

---

## 📝 Requirements

### 🔄 Processing Order
1. **First:** Add all science books to the result array
2. **Second:** Add all philosophy books to the result array

### 📖 Title Formatting Rules
Each book title must be formatted with:
- ✅ **First letter:** Uppercase
- ✅ **Remaining letters:** Lowercase
- ✅ **Applied regardless** of original formatting

### 🛠️ Technical Requirements
- Use **array concatenation** to combine book arrays
- Use **nested loops** to format each book title correctly
- Process titles before adding them to the final array

---

## 💡 Formatting Example

```javascript
// Original title (any case combination)
let title = "THE COSMOS";

// Proper formatting technique
let formattedTitle = title.charAt(0).toUpperCase() + title.slice(1).toLowerCase();

// Result
console.log(formattedTitle); // Output: "The cosmos"
```

### 🔍 Step-by-Step Breakdown
1. `title.charAt(0).toUpperCase()` → Gets first character and makes it uppercase
2. `title.slice(1).toLowerCase()` → Gets remaining characters and makes them lowercase
3. Concatenate both parts using `+` operator

---

## 🎪 Example Usage

```javascript
// Sample input
const scienceBooks = ["PHYSICS FUNDAMENTALS", "chemistry basics", "BiOlOgY eSSenTiAlS"];
const philosophyBooks = ["ANCIENT WISDOM", "modern ethics", "PhIlOsOpHy Of MiNd"];

// Function call
const organizedBooks = organizeLibrary(scienceBooks, philosophyBooks);

// Expected output
console.log(organizedBooks);
/*
[
  "Physics fundamentals",
  "Chemistry basics", 
  "Biology essentials",
  "Ancient wisdom",
  "Modern ethics",
  "Philosophy of mind"
]
*/
```

---

## ✨ Key Points to Remember

> 🔑 **Important:** Apply the formatting transformation to **each book title** in both input arrays before adding them to your result array.

- 📊 **Order matters:** Science books first, then philosophy books
- 🔤 **Consistent formatting:** First letter uppercase, rest lowercase
- 🔧 **Use proper methods:** Array concatenation and nested loops
- 🎯 **Process before adding:** Format titles during the organization process

---

## 🏷️ Tags
`JavaScript` `Arrays` `String Manipulation` `Loops` `Easy Challenge`
