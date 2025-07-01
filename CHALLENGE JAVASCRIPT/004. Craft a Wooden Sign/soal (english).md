## Craft a Wooden Sign 🪵

### Challenge

**Easy**

Create a function named `craftWoodSign` that receives a string `signText` and a number `borderWidth`.

The function will create a wooden sign with the `signText` engraved in the center, surrounded by a border made of asterisks (`*`). The `borderWidth` determines the thickness of the border.

---

### Steps:

1. Reverse the `signText`.
2. Calculate the total width of the sign: `length of signText + 2 × borderWidth`.
3. Create the top and bottom borders by repeating the `*` character for the total width.
4. Create the side space rows by adding `borderWidth` spaces on each side of the reversed text, enclosed in asterisks.
5. Construct the final sign as follows:
   - Top border (repeated `borderWidth` times)
   - Empty space rows (repeated `borderWidth` times)
   - Center row with reversed text
   - Empty space rows (repeated `borderWidth` times)
   - Bottom border (repeated `borderWidth` times)

Return the completed wooden sign as a single string with newline (`\n`) characters.
