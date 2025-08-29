# 🏆 Competition Placards Formatter

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that formats participant placards for a competition according to strict officiating requirements.

---

## 🎯 Objective

Develop a function named `formatPlacards` that transforms participant names into properly formatted competition placards that meet the regulatress's exacting standards.

### Requirements

The regulatress has established specific formatting rules for all competition placards:

- ✅ Each placard must be prefixed with `'Competitor: '`
- ✅ All characters must be converted to **UPPERCASE**
- ✅ Return a new formatted list (preserve original data)

---

## 🔧 Function Specification

### Function Name
```javascript
formatPlacards(names)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `names` | `Array<string>` | An array of strings representing participant names |

### Return Value

| Type | Description |
|------|-------------|
| `Array<string>` | A new array where each element is a formatted placard string |

---

## 💡 Expected Behavior

### Input Format
```javascript
["john doe", "jane smith", "alex wilson"]
```

### Output Format
```javascript
["COMPETITOR: JOHN DOE", "COMPETITOR: JANE SMITH", "COMPETITOR: ALEX WILSON"]
```

---

## 🎨 Format Pattern

Each formatted placard follows this exact pattern:

```
COMPETITOR: [PARTICIPANT NAME IN UPPERCASE]
```

### Examples

| Original Name | Formatted Placard |
|---------------|------------------|
| `"alice brown"` | `"COMPETITOR: ALICE BROWN"` |
| `"Bob Green"` | `"COMPETITOR: BOB GREEN"` |
| `"CHARLIE BLUE"` | `"COMPETITOR: CHARLIE BLUE"` |

---

## ⚠️ Important Notes

> **Data Integrity:** The function should create a new array and not modify the original `names` array.

> **Consistency:** All output must follow the exact format requirements to pass the regulatress's inspection.

> **Case Handling:** The function should handle names in any case (lowercase, uppercase, mixed case) and convert them all to uppercase.

---

## 🔍 Key Considerations

- Handle empty arrays gracefully
- Ensure consistent formatting across all entries
- Maintain the original order of participants
- Process each name independently

---

*Good luck with your implementation! Make sure every placard meets the regulatress's strict standards.* 🎯
