# 🐠 Marine Creature Observation Tags

## Challenge Overview

**Difficulty Level:** `Easy` 🟢

---

## 📋 Problem Statement

Write a function called `createObservationTags` that processes an array of marine creature names and generates standardized field observation tags for research purposes.

### How It Works

The function should:
- Extract the **first 4 characters** from each marine creature name
- Convert these characters to **UPPERCASE**
- Return an array of formatted observation tags

---

## 🔧 Function Specification

### Function Signature

```javascript
createObservationTags(creatures)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `creatures` | `Array<string>` | An array containing marine creature names as strings |

### Returns

- **Type:** `Array<string>`
- **Format:** An array of uppercase observation tags, each containing the first 4 characters of the creature name

---

## 💡 Example

### Input
```javascript
["Brittle Star", "Starfish", "Jellyfish"]
```

### Output
```javascript
["BRIT", "STAR", "JELL"]
```

---

## 🎯 Expected Behavior

1. Take each creature name from the input array
2. Extract only the first 4 characters
3. Convert those characters to uppercase
4. Compile all tags into a new array
5. Return the resulting array

---

## 📝 Notes

- Ensure proper handling of creature names
- The observation tags should always be exactly 4 characters long (when possible)
- All output should be in uppercase format
- Maintain the same order as the input array

---

> **Tip:** Think about string manipulation methods that can help you extract substrings and change their case!
