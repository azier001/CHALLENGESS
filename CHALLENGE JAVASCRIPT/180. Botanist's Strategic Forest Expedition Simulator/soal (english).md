# 🌲 Botanist's Strategic Forest Expedition Simulator

> **Challenge Level:** Medium

---

## 📋 Overview

Create a function named `exploreAncientForest` that simulates a botanist's expedition through an ancient forest. This challenge incorporates advanced hashing techniques, control flow, and game theory concepts to model strategic decision-making in resource management and exploration.

---

## 🎯 Objective

The botanist must make strategic decisions about which areas to explore, balancing the desire to discover rare species with the need to conserve resources and avoid potential dangers.

---

## 📝 Function Signature

```javascript
function exploreAncientForest(forestMap, energyLevel, maxDays, explorationStrategy) {
  // Your implementation here
}
```

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `forestMap` | `Array<Array<string>>` | A 2D array representing the forest layout, where each cell contains information about terrain and potential discoveries |
| `energyLevel` | `number` | Integer representing the botanist's initial energy level |
| `maxDays` | `number` | Integer representing the maximum number of days for the expedition |
| `explorationStrategy` | `string` | The botanist's chosen strategy: `'cautious'`, `'balanced'`, or `'aggressive'` |

---

## 📤 Return Value

The function should return an object with the following structure:

```javascript
{
  rareSpeciesDiscovered: number,      // Number of rare species discovered
  totalObservations: number,          // Total number of observations made
  remainingEnergy: number,            // Remaining energy level
  significantDiscoveries: string[]    // Array of most significant discoveries
}
```

---

## 🎮 Implementation Requirements

### 1. **Hash Table Management**
- Create a hash table (object) to efficiently store and retrieve information about discovered species and their locations
- Use the hash table for quick lookup and avoiding duplicate discoveries

### 2. **Advanced Control Flow**
- Iterate through the forest map for the given number of days or until energy is depleted
- Implement strategic use of `break` and `continue` statements to optimize the exploration path
- Use the exploration strategy to determine movement and observation priorities

### 3. **Game Theory Concepts**
- Model decision-making considering:
  - Rarity of species
  - Energy conservation
  - Potential risks
  - Expected value of exploring different areas

### 4. **Path Optimization**
- Use `break` and `continue` statements to:
  - Skip dangerous or low-value areas
  - Prioritize high-value locations
  - Optimize energy expenditure

### 5. **Data Tracking**
- Update counters for species discovered and observations made
- Track significant discoveries throughout the expedition
- Monitor remaining energy levels

---

## 💡 Key Concepts to Apply

### 🗂️ Hashing
- Efficient storage and retrieval of species data
- Quick duplicate detection
- Location-based indexing

### 🔄 Control Flow
- Strategic loop management
- Conditional exploration paths
- Early termination conditions

### 🎲 Game Theory
- Risk vs. reward assessment
- Resource allocation strategy
- Decision optimization under constraints

---

## 🎭 Exploration Strategies

### 🛡️ Cautious
- Prioritizes energy conservation
- Avoids high-risk areas
- Focuses on guaranteed discoveries

### ⚖️ Balanced
- Balances risk and reward
- Moderate energy expenditure
- Mix of safe and adventurous exploration

### ⚔️ Aggressive
- Maximizes discovery potential
- Takes calculated risks
- Higher energy consumption

---

## ⚠️ Important Notes

- Ensure efficient implementation with proper use of hash tables
- Handle edge cases (zero energy, empty forest, etc.)
- Optimize for performance with large forest maps
- Make strategic decisions based on the chosen exploration strategy
- Never access undefined cells in the forest map

---

## 🧪 Example Usage

```javascript
const forestMap = [
  ['tree', 'rare_orchid', 'bush'],
  ['danger', 'common_fern', 'rare_moss'],
  ['tree', 'water', 'rare_mushroom']
];

const result = exploreAncientForest(forestMap, 100, 3, 'balanced');

console.log(result);
// Output:
// {
//   rareSpeciesDiscovered: 3,
//   totalObservations: 5,
//   remainingEnergy: 45,
//   significantDiscoveries: ['rare_orchid', 'rare_moss', 'rare_mushroom']
// }
```

---

## 🏆 Success Criteria

✅ Correctly implements hash table for species tracking  
✅ Uses control flow statements strategically  
✅ Applies game theory in decision-making  
✅ Returns accurate expedition results  
✅ Handles all exploration strategies appropriately  
✅ Optimizes performance for large inputs  

---

**Good luck with your expedition! 🌿🔍**
