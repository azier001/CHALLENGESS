# ⚡ Count Lightning Flash Sequences

## 📋 Challenge Overview

**Difficulty:** `Easy`

Create a function that analyzes lightning flash patterns recorded by a sensor and counts valid sequences.

---

## 🎯 Objective

Implement a function named `countLightningFlashes` that processes a string of lightning sensor data.

---

## 📥 Input

The function receives:
- A **string** containing only two characters:
  - `*` → Lightning flash detected
  - `-` → No flash detected

**Example input:**
```
"**-***----*-**"
```

---

## 📤 Output

Return the **total number** of valid consecutive lightning flash sequences.

---

## 📏 Rules & Constraints

### ✅ What to Count
- A **sequence** is defined as one or more `*` characters appearing consecutively
- Each valid sequence contributes `1` to the total count

### ❌ What to Ignore
- **Sequences longer than 4 flashes** must be excluded from the count
- Use `break` and `continue` statements to handle these long sequences

### 💡 Examples

| Input | Valid Sequences | Count | Explanation |
|-------|----------------|-------|-------------|
| `"**-***-*"` | `**`, `***`, `*` | **3** | All sequences ≤ 4 flashes |
| `"*****-**"` | `**` | **1** | First sequence (5 flashes) ignored |
| `"*-**-***-****"` | `*`, `**`, `***`, `****` | **4** | All sequences ≤ 4 flashes |
| `"*****"` | none | **0** | Sequence exceeds 4 flashes |

---

## 🔧 Technical Requirements

- **Function name:** `countLightningFlashes`
- **Must use:** `break` and/or `continue` statements for control flow
- **Parameter:** Single string argument
- **Return type:** Number (integer)

---

## 💭 Hints

- Think about how to identify when a sequence starts and ends
- Consider tracking the length of each sequence as you iterate
- Remember to reset your sequence counter appropriately
- Use `continue` or `break` when you detect a sequence exceeding 4 flashes

---

## 🚀 Getting Started

```javascript
function countLightningFlashes(sensorData) {
  // Your code here
}

// Test cases
console.log(countLightningFlashes("**-***-*"));        // Expected: 3
console.log(countLightningFlashes("*****-**"));        // Expected: 1
console.log(countLightningFlashes("*-**-***-****"));   // Expected: 4
```

---

**Good luck! ⚡**
