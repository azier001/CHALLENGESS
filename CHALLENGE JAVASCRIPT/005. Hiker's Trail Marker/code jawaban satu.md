## Implementation: trailMarker

```javascript
function trailMarker(steps, capitalize) {
  // Reverse the order of steps to create the return path
  const reversedSteps = steps.slice().reverse();

  // Capitalize steps if the capitalize flag is true
  const processedSteps = capitalize
    ? reversedSteps.map((step) => step.toUpperCase())
    : reversedSteps;

  // Join the steps with ' -> ' and add emojis
  const formattedPath = `🏔️ ${processedSteps.join(' -> ')} 🥾`;

  return formattedPath;
}
```

## 📥 Contoh Input

```js
trailMarker(
  ["Uphill", "Through_Wheat", "Around_Rock", "Cross_Stream"],
  true
)
```

## 📤 Output yang Diharapkan

```
🏔️ CROSS_STREAM -> AROUND_ROCK -> THROUGH_WHEAT -> UPHILL 🥾
```
