## Implementation: sortColors

```javascript
```javascript
function sortColors(colors) {
  // Memfilter semua elemen yang bernilai 'green' dan menyimpannya di greenColors
  const greenColors = colors.filter(color => color === 'green');

  // Memfilter elemen yang bukan 'green', lalu mengurutkannya secara alfabetis
  const otherColors = colors.filter(color => color !== 'green').sort();

  // Menggabungkan 'greenColors' di depan dengan 'otherColors' setelahnya
  return [...greenColors, ...otherColors];
}
```

}
```

#example
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
