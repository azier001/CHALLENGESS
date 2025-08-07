# 🚖 Taxi Cab Fare Calculator Challenge

## 📊 Challenge Level
**Easy**

## 🎯 Objective
Create a function named `calculateCabFare` that simulates a taxi cab meter by calculating the total fare based on distances traveled and a base fare.

## 📋 Function Requirements

### Function Signature
```javascript
function calculateCabFare(distances, baseFare)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `distances` | `array` | An array of integers representing the distances in kilometers for each leg of the journey |
| `baseFare` | `number` | An integer representing the base fare before distance-based charges are added |

### Return Value
- **Type**: `integer`
- **Description**: The total calculated fare

## 🔄 Algorithm Steps

The function should perform the following operations in order:

1. **Reverse the distances array** 
   - Transform the input array to reverse order

2. **Calculate total distance**
   - Sum all distances from the reversed array to get total kilometers traveled

3. **Apply distance-based pricing**
   - Multiply total distance by **$10 per kilometer**

4. **Calculate final fare**
   - Add the distance-based fare to the base fare

## 💡 Example Usage

```javascript
// Example 1
const distances = [5, 3, 8, 2];
const baseFare = 15;
const totalFare = calculateCabFare(distances, baseFare);
// Expected: 15 + (5+3+8+2) * 10 = 15 + 180 = 195

// Example 2  
const distances = [10, 7];
const baseFare = 20;
const totalFare = calculateCabFare(distances, baseFare);
// Expected: 20 + (10+7) * 10 = 20 + 170 = 190
```

## 📝 Implementation Notes

- Ensure the distances array is reversed **before** calculating the sum
- The rate is fixed at **$10 per kilometer**
- All inputs are integers, and the return value should be an integer
- Handle edge cases like empty arrays appropriately

## 🧪 Test Cases

Consider testing with:
- ✅ Normal case with multiple distances
- ✅ Single distance in array
- ✅ Empty distances array
- ✅ Zero base fare
- ✅ Large distance values

---

*Good luck with your implementation! 🚀*
