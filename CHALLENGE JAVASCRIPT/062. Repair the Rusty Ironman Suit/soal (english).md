# 🔧 Repair the Rusty Ironman Suit

## 📊 Challenge Information
- **Difficulty Level**: `Easy`
- **Function Name**: `repairIronmanSuit`
- **Programming Concept**: String manipulation and simulation

---

## 🎯 Problem Statement

Tony Stark has discovered his rusty Ironman suit in an old piehouse and needs your help to repair it! The suit's condition is critical, and time is running out before the next mission.

### 🦾 The Suit's Condition
The suit's status is represented by a string containing:
- **`R`** - Rusty parts (needs cleaning)
- **`C`** - Clean parts (in good condition)

### ⚡ The Challenge
Tony has limited energy and can only clean a certain number of parts at once. However, there's a catch - **rust spreads**! After cleaning, any remaining rusty parts will contaminate adjacent clean parts.

---

## 🔧 Function Specification

### Function Signature
```javascript
function repairIronmanSuit(suitStatus, cleanParts)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `suitStatus` | `string` | Current state of the suit (contains only 'R' and 'C') |
| `cleanParts` | `number` | Maximum number of parts Tony can clean in one round |

### Return Value
- **Type**: `string`
- **Description**: Final state of the suit after one round of cleaning and rust spreading

---

## ⚙️ Repair Process

The repair simulation follows these steps:

### Step 1: 🧹 Cleaning Phase
- Scan the suit **from left to right**
- Replace `R` with `C` for up to `cleanParts` rusty parts
- Stop when the cleaning limit is reached

### Step 2: 🦠 Rust Spreading Phase
- Each remaining rusty part (`R`) spreads rust to **one adjacent clean part**
- Rust can spread to either the **left** or **right** side (if a clean part exists)
- This happens simultaneously for all rusty parts

---

## 💡 Example Walkthrough

### Input
```
suitStatus = "RRRCCCRRR"
cleanParts = 3
```

### Process
1. **Initial State**: `"RRRCCCRRR"`
2. **After Cleaning** (3 parts): `"CCCCCCRRR"`
   - First 3 'R's from left are cleaned
3. **After Rust Spreading**: `"RCCCCCRR"`
   - The 7th position 'R' spreads left to position 6
   - The 8th and 9th 'R's spread left to position 7

### Output
```
"RCCCCCRR"
```

---

## 🎯 Key Points to Remember

> ⚠️ **Important**: Rust spreading happens **after** all cleaning is complete

> 💡 **Tip**: Consider edge cases where rust might not have adjacent clean parts to spread to

> 🔄 **Process Order**: Always clean first, then simulate rust spreading

---

## 🧪 Test Your Solution

Try these additional test cases to verify your implementation:

```javascript
// Test Case 1: No rust to spread
repairIronmanSuit("RRR", 3) // Expected: "CCC"

// Test Case 2: Limited cleaning capacity
repairIronmanSuit("RRRRR", 2) // Expected: "CCRR" (after spreading)

// Test Case 3: Mixed pattern
repairIronmanSuit("RCRCRC", 1) // Expected: varies based on implementation
```

---

## 🏆 Success Criteria

Your function should:
- ✅ Clean the correct number of rusty parts from left to right
- ✅ Simulate rust spreading accurately
- ✅ Handle edge cases (no rust, no clean parts, etc.)
- ✅ Return the correct final state as a string

---

*Good luck, and may the arc reactor be with you! ⚡*
