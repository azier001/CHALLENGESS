# 🥾 Hiker's Trail Marker

> **Challenge Level**: 🟢 Easy  
> **Topic**: JavaScript Function & String Manipulation

---

## 🌄 Overview

As a cautious hiker exploring the foothills of a mountain range, surrounded by fields of golden grain, you want to **mark your trail** for the return journey.

To do this, you will create a **custom function** that reverses and formats your hiking steps for easy readability.

---

## 🔧 Function Signature

```js
function trailMarker(steps, capitalize)
```

### 📌 Parameters

| Name         | Type      | Description                                                                 |
|--------------|-----------|-----------------------------------------------------------------------------|
| `steps`      | `array`   | An array of strings, each representing a step taken on the hike.            |
| `capitalize` | `boolean` | If `true`, each step should be converted to uppercase.                      |

---

## 🧭 What You Need to Do

The `trailMarker` function should perform the following operations:

1. 🔁 **Reverse** the order of the steps to represent the return path.
2. 🔠 If `capitalize` is `true`, convert all steps to **uppercase**.
3. 🔗 Join the steps using `' -> '` as a separator.
4. 🏔️ Add a **mountain emoji** at the beginning and a **hiker boot emoji** at the end of the string.

---

## 📥 Example Input

```js
trailMarker(
  ["Uphill", "Through_Wheat", "Around_Rock", "Cross_Stream"],
  true
)
```

## 📤 Expected Output

```
🏔️ CROSS_STREAM -> AROUND_ROCK -> THROUGH_WHEAT -> UPHILL 🥾
```

---

## 🧪 Another Example

```js
trailMarker(["Valley", "Bridge", "Forest"], false)
```

**Output:**

```
🏔️ Forest -> Bridge -> Valley 🥾
```

---

## 💡 Tips

- Use JavaScript methods like:
  - `.reverse()` to reverse the array.
  - `.map()` to modify each step.
  - `.join(' -> ')` to concatenate the steps with a separator.
- Add emojis with simple string concatenation.

---

