## Implementation: sortColors

```javascript
function sortColors(colors) {
  // Separate green colors from other colors
  const greens = colors.filter((color) => color === 'green');
  const others = colors.filter((color) => color !== 'green');

  // Sort the non-green colors alphabetically
  others.sort();

  // Return greens first, followed by sorted others
  return [...greens, ...others];
}
```

## Example

```javascript
// Test cases
console.log(sortColors(['blue', 'red', 'yellow']));
// Expected: ["blue", "red", "yellow"]

console.log(sortColors(['blue', 'green', 'red']));
// Expected: ["green", "blue", "red"]

console.log(sortColors(['purple', 'orange', 'green', 'cyan']));
// Expected: ["green", "cyan", "orange", "purple"]

// Additional test cases
console.log(sortColors(['green', 'green', 'blue', 'red']));
// Expected: ["green", "green", "blue", "red"]

console.log(sortColors(['Green', 'green', 'blue']));
// Expected: ["green", "Green", "blue"] (case-sensitive)

```
