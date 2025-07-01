## Implementation: craftWoodSign

```javascript
function craftWoodSign(signText, borderWidth) {
    // Step 1: Reverse the signText
    const reversedText = signText.split('').reverse().join('');
    
    // Step 2: Calculate total width
    const totalWidth = signText.length + (2 * borderWidth);
    
    // Step 3: Create top and bottom borders
    const topBorder = '*'.repeat(totalWidth);
    const bottomBorder = '*'.repeat(totalWidth);
    
    // Step 4: Create side borders with reversed text
    const sideBorder = ' '.repeat(borderWidth) + reversedText + ' '.repeat(borderWidth);
    
    // Step 5: Construct the final sign
    const woodenSign = topBorder + '\n' + sideBorder + '\n' + bottomBorder;
    
    return woodenSign;
}
```
