# 🏥 Stomach Checkup Diagnosis

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that simulates a basic diagnosis process at a doctor's office for a stomach checkup. The function analyzes a combination of symptoms and returns an appropriate diagnosis.

---

## 🎯 Objective

Implement a function named `diagnoseStomachIssue` that receives three boolean parameters representing different symptoms and returns a diagnosis based on their combination.

---

## 📥 Function Signature

```javascript
function diagnoseStomachIssue(hasNausea, hasStomachPain, hasHeartburn)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `hasNausea` | `boolean` | Whether the patient is experiencing nausea |
| `hasStomachPain` | `boolean` | Whether the patient is experiencing stomach pain |
| `hasHeartburn` | `boolean` | Whether the patient is experiencing heartburn |

### Return Value

- **Type:** `string`
- **Description:** A diagnosis message based on the combination of symptoms

---

## 🔍 Diagnosis Criteria

The function should evaluate symptoms and return diagnoses according to the following logic:

| Symptoms | Diagnosis |
|----------|-----------|
| ✅ All three symptoms present | `"Possible gastritis"` |
| ✅ Stomach pain + Heartburn (no nausea) | `"Likely acid reflux"` |
| ✅ Only nausea | `"Possible stomach bug"` |
| ✅ Only stomach pain | `"Possible stomach ulcer"` |
| ✅ Only heartburn | `"Mild indigestion"` |
| ❌ No symptoms | `"No issues detected"` |
| ❓ Any other combination | `"Inconclusive, please consult with the doctor"` |

---

## 💡 Requirements

- ✔️ Use **basic logical operators** (AND, OR, NOT) to determine the diagnosis
- ✔️ Utilize **variables** to store intermediate results
- ✔️ Follow the exact diagnosis criteria listed above
- ✔️ Return strings that match exactly as specified

---

## 📝 Example Usage

```javascript
// Example 1: All symptoms present
diagnoseStomachIssue(true, true, true);
// Returns: "Possible gastritis"

// Example 2: Stomach pain and heartburn only
diagnoseStomachIssue(false, true, true);
// Returns: "Likely acid reflux"

// Example 3: Only nausea
diagnoseStomachIssue(true, false, false);
// Returns: "Possible stomach bug"

// Example 4: No symptoms
diagnoseStomachIssue(false, false, false);
// Returns: "No issues detected"
```

---

## 🧠 Hints

1. Start by checking for the most specific conditions first (all symptoms, specific combinations)
2. Use logical operators like `&&` (AND), `||` (OR), and `!` (NOT)
3. Consider storing boolean expressions in variables for cleaner code
4. The order of your conditional statements matters!

---

## ⚠️ Important Notes

> **Disclaimer:** This is a simplified educational exercise. Real medical diagnosis requires professional medical evaluation and should never be replaced by automated systems.

---

**Good luck! 🚀**
