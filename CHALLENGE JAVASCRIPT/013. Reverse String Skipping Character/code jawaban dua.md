# 🔄 Function `reverseSkip` (Optimized Version)

## 📋 Overview
Function yang elegan dan ringkas ini melakukan dua operasi sekaligus dalam satu chain:
1. **Membalik urutan karakter** (reverse)
2. **Menghapus karakter tertentu** (filter)

## 💻 Kode Function

```javascript
function reverseSkip(str, char) {
  return str.split('').reverse().filter(c => c !== char).join('');
}
```

## 🔗 Method Chaining Breakdown

```mermaid
graph LR
    A[Input String] --> B[split('')]
    B --> C[reverse()]
    C --> D[filter()]
    D --> E[join('')]
    E --> F[Output String]
    
    style A fill:#FFE6E6
    style F fill:#E6FFE6
    style B fill:#E6F3FF
    style C fill:#FFF0E6
    style D fill:#F0E6FF
    style E fill:#E6FFE6
```

## 🔍 Penjelasan Step-by-Step

| Step | Method | Input | Output | Penjelasan |
|------|--------|-------|---------|------------|
| 1️⃣ | `.split('')` | `"hello"` | `['h','e','l','l','o']` | Ubah string ke array karakter |
| 2️⃣ | `.reverse()` | `['h','e','l','l','o']` | `['o','l','l','e','h']` | Balik urutan array |
| 3️⃣ | `.filter(c => c !== char)` | `['o','l','l','e','h']` | `['o','e','h']` | Hapus karakter tertentu |
| 4️⃣ | `.join('')` | `['o','e','h']` | `"oeh"` | Gabung array jadi string |

## 🎯 Contoh Penggunaan

### ✨ Contoh Interaktif

```javascript
// 🌟 Contoh 1: Menghapus huruf vokal
reverseSkip("hello world", "l");
// "hello world" → ['h','e','l','l','o',' ','w','o','r','l','d'] 
// → ['d','l','r','o','w',' ','o','l','l','e','h']
// → ['d','r','o','w',' ','o','e','h'] (hapus 'l')
// → "drow oeh"

// 🌟 Contoh 2: Programming terms
reverseSkip("javascript", "a");
// "javascript" → "tpircsavj" (reverse)
// → "tpircsavj" (no 'a' to remove after reverse)
// Output: "tpircsavj"

// 🌟 Contoh 3: Repeated characters
reverseSkip("banana", "a");
// "banana" → "ananab" (reverse)
// → "nnnb" (remove all 'a')
// Output: "nnnb"
```

### 📊 Comparison Table

| Input | Char to Remove | Reversed | After Filter | Final Output |
|-------|----------------|----------|--------------|--------------|
| `"hello"` | `"l"` | `"olleh"` | `"oeh"` | **"oeh"** |
| `"world"` | `"r"` | `"dlrow"` | `"dlow"` | **"dlow"** |
| `"coding"` | `"g"` | `"gnidoc"` | `"nidoc"` | **"nidoc"** |

## 💡 Saran & Best Practices

### ✅ **Yang Sudah Bagus**
- **Method Chaining**: Sangat clean dan readable
- **Arrow Function**: Modern ES6 syntax
- **Strict Equality**: Menggunakan `!==` instead of `!=`
- **Single Responsibility**: Setiap method punya tugas jelas

### 🚀 **Saran Peningkatan**

#### 1. **Error Handling** (Opsional)
```javascript
function reverseSkip(str, char) {
  if (typeof str !== 'string' || typeof char !== 'string') {
    throw new Error('Both parameters must be strings');
  }
  return str.split('').reverse().filter(c => c !== char).join('');
}
```

#### 2. **JSDoc Documentation** (Recommended)
```javascript
/**
 * Reverses a string and removes all occurrences of specified character
 * @param {string} str - The input string to process
 * @param {string} char - The character to remove
 * @returns {string} Processed string
 */
function reverseSkip(str, char) {
  return str.split('').reverse().filter(c => c !== char).join('');
}
```

#### 3. **Alternative dengan Regex** (Advanced)
```javascript
function reverseSkip(str, char) {
  return str.split('')
            .reverse()
            .join('')
            .replace(new RegExp(char.replace(/[.*+?^${}()|[\]\\]/g, '\\$&'), 'g'), '');
}
```

## ⚡ Performance Analysis

```
Time Complexity: O(n)
Space Complexity: O(n)
```

- **O(n) operations**: split, reverse, filter, join
- **Memory usage**: Temporary arrays created during chaining
- **Efficiency**: Optimal for small to medium strings

## 🎨 Real-World Use Cases

| Use Case | Example | Benefit |
|----------|---------|---------|
| **Text Processing** | Remove spaces from reversed text | Data cleaning |
| **String Manipulation** | Create unique identifiers | Algorithm preprocessing |
| **Game Development** | Process player names | Input validation |
| **Data Transformation** | Clean reversed user input | Form processing |

## 🧪 Testing Examples

```javascript
// Edge cases to consider
reverseSkip("", "a");        // "" (empty string)
reverseSkip("aaa", "a");     // "" (all chars removed)
reverseSkip("abc", "x");     // "cba" (char not found)
reverseSkip("a", "a");       // "" (single char removed)
```

---
*Function ini mendemonstrasikan kekuatan method chaining dalam JavaScript untuk operasi string yang kompleks namun tetap readable.* ✨
