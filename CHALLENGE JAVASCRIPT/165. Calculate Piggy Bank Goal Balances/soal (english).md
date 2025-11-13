# 🐷 Calculate Piggy Bank Goal Balances

## Challenge Overview

**Difficulty:** `Easy`

Write a function that calculates the final balances for multiple savings goals by processing transaction data.

---

## 📋 Problem Statement

Create a function `calculateGoalBalances` that processes financial transactions across multiple savings goals and returns the final balance for each goal.

The function receives a 2D array where:
- Each **inner array** represents all transactions for a specific savings goal
- **Positive numbers** represent deposits (money added)
- **Negative numbers** represent withdrawals (money removed)

---

## 🔧 Function Signature

```javascript
function calculateGoalBalances(transactions)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `transactions` | `Array<Array<number>>` | 2D array containing transaction amounts for each savings goal |

### Returns

| Type | Description | Format |
|------|-------------|--------|
| `Array<number>` | Array of final balances for each goal | `[balance1, balance2, balance3]` |

---

## 💡 Examples

### Example 1: Basic Transactions

```javascript
const transactions = [
  [100, 50, -20],     // Goal 1: deposit $100, deposit $50, withdraw $20
  [200, -50, 100],    // Goal 2: deposit $200, withdraw $50, deposit $100
  [75, 25]            // Goal 3: deposit $75, deposit $25
];

calculateGoalBalances(transactions);
// Returns: [130, 250, 100]
```

### Example 2: Single Transaction Per Goal

```javascript
const transactions = [
  [500],
  [-100],
  [250]
];

calculateGoalBalances(transactions);
// Returns: [500, -100, 250]
```

---

## ✅ Requirements

- ✓ Process all transactions for each savings goal
- ✓ Handle positive numbers as deposits
- ✓ Handle negative numbers as withdrawals
- ✓ Return final balance for each goal in the same order
- ✓ Support any number of goals and transactions

---

## 🎯 Key Concepts

This challenge tests your understanding of:

- **Array manipulation** - Working with 2D arrays
- **Iteration** - Looping through nested structures
- **Accumulation** - Summing values to calculate totals
- **Data transformation** - Converting input format to output format

---

## 💭 Hints

<details>
<summary>Click to reveal hints</summary>

1. You'll need to iterate through each goal's transaction array
2. For each goal, sum all transaction amounts
3. The `reduce()` method might be useful here
4. Consider using `map()` to transform the 2D array into an array of balances

</details>

---

Good luck! 🚀
