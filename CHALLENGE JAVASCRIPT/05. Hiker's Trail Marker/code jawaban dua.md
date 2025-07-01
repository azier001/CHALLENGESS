## Implementation: trailMarker

```javascript
function trailMarker(steps, capitalize) {
  let reversedSteps = steps.reverse();

  if (capitalize) {
    reversedSteps = reversedSteps.map((step) => step.toUpperCase());
  }

  return `🏔️ ${reversedSteps.join(' -> ')} 🥾`;
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
