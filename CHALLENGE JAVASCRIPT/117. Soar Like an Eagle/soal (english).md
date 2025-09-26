# 🦅 Soar Like an Eagle

## 📋 Challenge Information

| **Difficulty** | **Function Name** | **Parameters** |
|----------------|-------------------|----------------|
| Easy | `soarLikeEagle` | `string` str, `number` n |

## 🎯 Problem Description

Create a function that transforms a string by repeating each character based on specific rules:

- **Regular characters**: Repeat `n` times
- **Vowels (a, e, i, o, u)**: Repeat `n + 1` times
- **Edge case**: If `n` is 0 or negative, return an empty string

## 🔍 Function Signature

```javascript
function soarLikeEagle(str, n) {
    // Your implementation here
}
```

## 📝 Examples

### Example 1
```javascript
soarLikeEagle("Hi", 2)
// Expected output: "HHiii"
```
**Explanation:**
- `H` (consonant) → repeated 2 times → `HH`
- `i` (vowel) → repeated 2+1=3 times → `iii`

### Example 2
```javascript
soarLikeEagle("Hello", 3)
// Expected output: "HHHeeeelllllooo"
```
**Explanation:**
- `H` (consonant) → repeated 3 times → `HHH`
- `e` (vowel) → repeated 3+1=4 times → `eeee`
- `l` (consonant) → repeated 3 times → `lll`
- `l` (consonant) → repeated 3 times → `lll`
- `o` (vowel) → repeated 3+1=4 times → `oooo`

### Example 3
```javascript
soarLikeEagle("Bye", 0)
// Expected output: ""
```
**Explanation:**
- Since `n` is 0, return empty string immediately

## ✅ Requirements

- Handle both uppercase and lowercase vowels
- Return empty string for `n ≤ 0`
- Process each character sequentially
- Maintain original character case

## 🧠 Key Concepts

- **String manipulation**
- **Conditional logic**
- **Character classification**
- **Loop iteration**
- **Edge case handling**

## 💡 Hints

- Consider using `includes()` method to check for vowels
- Remember to handle both uppercase and lowercase vowels
- Use string repetition methods like `repeat()`
- Don't forget the edge case validation

---

*Happy coding! 🚀*
