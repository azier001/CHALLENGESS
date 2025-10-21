# ✈️ Busy Day at the Airpark

## 🧬 Challenge Overview

**Difficulty:** Easy
**Function Name:** `airportTraffic`

Simulate a **busy day at the airpark** by managing the runway and processing various pilot actions.
Your goal is to update the state of the runway based on these actions and return its final configuration.

---

## 📥 Parameters

### `runway` (Array)

* Represents the **initial state** of the airpark's runway.
* Each element indicates:

  * `0` → empty spot
  * `1` → occupied by a plane

### `pilotActions` (Array)

* Represents a list of **pilot actions** throughout the day.
* Each element is an integer describing what happens on the runway.

---

## ⚙️ Rules & Behavior

Process each action in `pilotActions` sequentially and update the `runway` accordingly:

| Action Type  | Example | Meaning                               | Effect                          |
| ------------ | ------- | ------------------------------------- | ------------------------------- |
| **Positive** | `2`     | A plane is landing at position 2      | Change `runway[1]` from `0 → 1` |
| **Negative** | `-3`    | A plane is taking off from position 3 | Change `runway[2]` from `1 → 0` |
| **Zero**     | `0`     | No change for that turn               | Skip the action                 |

> 🧠 **Note:**
>
> * If a **landing action** targets an already occupied spot (`1`), **ignore it**.
> * If a **takeoff action** targets an already empty spot (`0`), **ignore it**.
> * The positions are **1-based indexes** (e.g., `1` refers to the first element).

---

## 🧾 Function Description

```javascript
function airportTraffic(runway, pilotActions) {
  // Your code here
}
```

The function should:

1. Iterate through each action in `pilotActions`.
2. Update the `runway` based on the rules above.
3. Return the **final state** of the runway after all actions are processed.

---

## 💡 Example

### Input

```javascript
const runway = [0, 1, 0, 0];
const pilotActions = [1, -2, 3, 0, -4];
```

### Step-by-step Process

| Step | Action | Resulting Runway | Description                           |
| ---- | ------ | ---------------- | ------------------------------------- |
| 1    | `1`    | `[1, 1, 0, 0]`   | Plane lands at position 1             |
| 2    | `-2`   | `[1, 0, 0, 0]`   | Plane takes off from position 2       |
| 3    | `3`    | `[1, 0, 1, 0]`   | Plane lands at position 3             |
| 4    | `0`    | `[1, 0, 1, 0]`   | No change                             |
| 5    | `-4`   | `[1, 0, 1, 0]`   | Invalid (spot already empty), ignored |

### Output

```javascript
[1, 0, 1, 0]
```

---

## 🏁 Final Output

The function returns the **final runway state** as an array after processing all pilot actions.

```javascript
return [/* updated runway */];
```

---

✨ **Tip:** Focus on handling invalid actions properly to ensure accurate runway simulation.
