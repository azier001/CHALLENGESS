# 🏥 Medical Warehouse Organization System Challenge

**Level:** `Medium` | **Category:** `Data Structure & Algorithm`

---

## 📌 Problem Statement

Design and implement a function `organizeWarehouse` that processes medical supply inventory data. The function must organize supplies into an efficient warehouse management report by grouping items by type, sorting by lot numbers, and generating formatted storage labels with shelf positions.

---

## 🎯 Objective

Create a comprehensive warehouse organization system that transforms raw supply data into a structured, actionable report for inventory management and shelf positioning.

---

## 🔍 Processing Logic

The function must execute the following operations in sequence:

1. **Group supplies by type** — Collect all items into categories based on their `type` property
2. **Sort within groups** — Arrange items in each group by `lotNumber` in ascending order
3. **Calculate metrics** — For each type group:
   - Sum all units to get `totalUnits`
   - Assign sequential `shelfPosition` values (starting from 1)
4. **Generate labels** — Create formatted labels as `TYPE_LOTNUMBER`:
   - Convert type to UPPERCASE
   - Append the lot number
5. **Build report** — Combine all information into the return object structure

---

## 📊 Function Signature

```javascript
function organizeWarehouse(supplies) {
  // Implementation here
}
```

---

## 📥 Input: `supplies` Parameter

**Type:** Array of Objects

**Object Structure:**
```javascript
{
  name: String,        // Display name of the supply item
  type: String,        // Category/classification of supply
  lotNumber: Number,   // Lot identifier (unique tracking number)
  units: Number        // Quantity in inventory
}
```

**Example Input:**
```javascript
[
  { name: "Amitriptyline", type: "tricyclic_antidepressant", lotNumber: 89, units: 75 },
  { name: "Nortriptyline", type: "tricyclic_antidepressant", lotNumber: 92, units: 75 },
  { name: "Penicillin", type: "antibiotic", lotNumber: 45, units: 100 },
  { name: "Amoxicillin", type: "antibiotic", lotNumber: 67, units: 100 }
]
```

---

## 📤 Output: Return Value

**Type:** Object (Dictionary/Map)

**Structure:**
- **Key:** Type name (string) from the supplies
- **Value:** Object containing:
  - `totalUnits` (Number) — Sum of all units for this type
  - `shelfPosition` (Number) — Sequential position assignment (1, 2, 3, ...)
  - `labels` (Array) — Formatted storage labels for each lot

**Example Output:**
```javascript
{
  "tricyclic_antidepressant": {
    "totalUnits": 150,
    "shelfPosition": 1,
    "labels": [
      "TRICYCLIC_ANTIDEPRESSANT_LOT89",
      "TRICYCLIC_ANTIDEPRESSANT_LOT92"
    ]
  },
  "antibiotic": {
    "totalUnits": 200,
    "shelfPosition": 2,
    "labels": [
      "ANTIBIOTIC_LOT45",
      "ANTIBIOTIC_LOT67"
    ]
  }
}
```

---

## ✅ Requirements Checklist

- [ ] Group items by their `type` property
- [ ] Sort lot numbers in ascending numeric order (not lexicographic)
- [ ] Calculate correct total units per type group
- [ ] Assign shelf positions sequentially starting from 1
- [ ] Format labels as `TYPE_LOTNUMBER` with uppercase type
- [ ] Return properly structured object with all three required fields
- [ ] Handle edge cases (empty arrays, single items, duplicate types)

---

## 💭 Implementation Considerations

| Aspect | Note |
|--------|------|
| **Grouping** | Use `reduce()`, `Object.groupBy()`, or similar method to organize by type |
| **Sorting** | Sort numerically (use `(a, b) => a - b`), not alphabetically |
| **Type Case** | Convert all type names to UPPERCASE for labels only |
| **Shelf Order** | Maintain type order as they first appear in the grouped data |
| **Label Format** | Combine uppercase type + `_LOT` + lot number (e.g., `ANTIBIOTIC_LOT45`) |

---

## 🧪 Test Case Example

**Input:**
```javascript
const supplies = [
  { name: "Imipramine", type: "tricyclic_antidepressant", lotNumber: 92, units: 60 },
  { name: "Doxepin", type: "tricyclic_antidepressant", lotNumber: 89, units: 90 },
  { name: "Cephalexin", type: "antibiotic", lotNumber: 67, units: 150 },
  { name: "Ciprofloxacin", type: "antibiotic", lotNumber: 45, units: 100 }
];

organizeWarehouse(supplies);
```

**Expected Output:**
```javascript
{
  "tricyclic_antidepressant": {
    "totalUnits": 150,
    "shelfPosition": 1,
    "labels": [
      "TRICYCLIC_ANTIDEPRESSANT_LOT89",
      "TRICYCLIC_ANTIDEPRESSANT_LOT92"
    ]
  },
  "antibiotic": {
    "totalUnits": 250,
    "shelfPosition": 2,
    "labels": [
      "ANTIBIOTIC_LOT45",
      "ANTIBIOTIC_LOT67"
    ]
  }
}
```

---

## 🚀 Bonus Challenges

- Handle duplicate lot numbers within the same type
- Add validation for missing or invalid properties
- Implement maximum shelf capacity constraints
- Add filtering capability for specific supply types
