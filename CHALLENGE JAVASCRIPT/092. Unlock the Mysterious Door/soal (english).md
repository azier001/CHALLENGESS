# 🚪 Unlock the Mysterious Door

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that simulates unlocking a mysterious door by guessing the correct code through multiple attempts.

---

## 🎯 Objective

Implement a function named `unlockDoor` that attempts to crack a door code using a systematic approach.

## 📝 Function Specification

### Function Signature
```javascript
function unlockDoor(doorCode, numAttempts, clue)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `doorCode` | `number` | The secret code needed to unlock the door |
| `numAttempts` | `number` | Maximum number of attempts allowed to guess the code |
| `clue` | `string` | A helpful hint provided when all attempts fail |

---

## 🔧 Implementation Requirements

### Core Logic

1. **Loop Structure**
   - Use a `for` loop that iterates from `1` to `numAttempts`
   - Each iteration represents one attempt to guess the code

2. **Code Checking**
   - In each iteration, check if the current iteration number equals the `doorCode`
   - If a match is found, immediately return the success message

3. **Success Condition**
   ```javascript
   return "Door unlocked! The code was " + doorCode;
   ```

4. **Failure Condition**
   - If the loop completes without finding the correct code
   - Return the provided `clue` string

---

## 💡 Algorithm Flow

```
START
  ↓
FOR i = 1 TO numAttempts
  ↓
IS i == doorCode?
  ↓ YES
RETURN "Door unlocked! The code was " + doorCode
  ↓ NO
CONTINUE LOOP
  ↓
LOOP FINISHED?
  ↓ YES
RETURN clue
  ↓
END
```

---

## 🧪 Expected Behavior

### Successful Unlock
- **Condition:** Current attempt number matches the door code
- **Result:** Door unlocks with success message

### Failed Attempts
- **Condition:** All attempts exhausted without finding the code
- **Result:** Clue is provided to help solve the mystery

---

## 🎮 Example Usage

```javascript
// Example 1: Code found within attempts
unlockDoor(3, 5, "Think of a magic number")
// Expected: "Door unlocked! The code was 3"

// Example 2: Code not found within attempts
unlockDoor(7, 5, "The answer lies in lucky numbers")
// Expected: "The answer lies in lucky numbers"
```

---

## 🏆 Success Criteria

- ✅ Function correctly iterates through attempts
- ✅ Properly identifies when door code is found
- ✅ Returns appropriate success message with the code
- ✅ Falls back to clue when attempts are exhausted
- ✅ Uses exact string format for success message

---

*Good luck cracking the code! 🔓*
