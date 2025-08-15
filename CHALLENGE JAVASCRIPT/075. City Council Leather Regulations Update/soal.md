# 🏛️ City Council Leather Regulations Update

## 📋 Deskripsi Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Buat sebuah function yang mensimulasikan proses pengambilan keputusan dewan kota untuk regulasi barang kulit. Tugas Anda adalah mengimplementasikan function `updateLeatherRegulations` yang memodifikasi regulasi saat ini berdasarkan mood dewan dan tekanan industri.

---

## 🎯 Spesifikasi Function

### Nama Function
```javascript
updateLeatherRegulations(currentRegulations, councilMoodIndex, leatherIndustryPressure)
```

### Deskripsi
Function ini mensimulasikan bagaimana dewan kota memperbarui regulasi industri kulit berdasarkan mood mereka saat ini dan tekanan eksternal dari industri kulit.

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `currentRegulations` | `Array<string>` | An array of strings representing current leather regulations |
| `councilMoodIndex` | `number` | A number from 1 to 10 representing the council's mood<br/>• **1** = Very strict<br/>• **10** = Very lenient |
| `leatherIndustryPressure` | `boolean` | Indicates whether the leather industry is pressuring for looser regulations |

---

## ⚖️ Decision Rules

The function must apply the following rules in order:

### 1. 🔒 Strict Quality Control Rule
- **Condition:** `councilMoodIndex ≤ 3`
- **Action:** Add `"Strict quality control"` to regulations if not already present

### 2. 🌿 Environmental Assessment Rule
- **Condition:** `councilMoodIndex ≥ 8` AND `leatherIndustryPressure === true`
- **Action:** Remove `"Environmental impact assessment"` from regulations if it exists

### 3. 📅 Inspection Frequency Rule
- **Condition:** `councilMoodIndex` is between 4 and 7 (inclusive)
- **Action:** Change any occurrence of `"Monthly inspections"` to `"Quarterly inspections"`

### 4. 👥 Consumer Protection Rule
- **Condition:** `currentRegulations.length < 5` AND `leatherIndustryPressure === false`
- **Action:** Add `"Consumer protection guidelines"` to regulations

---

## 📤 Return Value

**Type:** `Array<string>`

**Description:** The modified array of regulations after applying all applicable rules.

---

## 💡 Implementation Tips

- Process rules in the order they are listed
- Check for existing regulations before adding duplicates
- Handle string replacements carefully for inspection frequency changes
- Consider edge cases where multiple rules might apply

---

## 🧪 Example Usage

```javascript
// Example 1: Strict council (mood = 2)
const regulations1 = ["Basic safety standards", "Worker protection"];
const result1 = updateLeatherRegulations(regulations1, 2, false);
// Expected: ["Basic safety standards", "Worker protection", "Strict quality control", "Consumer protection guidelines"]

// Example 2: Lenient council with industry pressure
const regulations2 = ["Environmental impact assessment", "Monthly inspections"];
const result2 = updateLeatherRegulations(regulations2, 9, true);
// Expected: ["Monthly inspections"]

// Example 3: Moderate council
const regulations3 = ["Monthly inspections", "Safety protocols"];
const result3 = updateLeatherRegulations(regulations3, 5, false);
// Expected: ["Quarterly inspections", "Safety protocols", "Consumer protection guidelines"]
```

---

## 🎨 Challenge Completed!

Once you've implemented the function, test it with various scenarios to ensure it handles all the decision rules correctly. Good luck! 🚀
