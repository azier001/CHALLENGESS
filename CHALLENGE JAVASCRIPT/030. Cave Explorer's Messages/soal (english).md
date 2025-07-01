# 🕳️ Cave Explorer Challenge

<div align="center">

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=for-the-badge)
![Language](https://img.shields.io/badge/Language-JavaScript-yellow?style=for-the-badge&logo=javascript)

</div>

---

## 🎯 Mission Briefing

You are developing a communication system for cave explorers! When explorers send messages in a cave system, sometimes they hear their own voice echoing back. Your task is to create a function that can distinguish between echo messages and different communications.

---

## 📋 Function Requirements

### 🔧 Function Signature
```javascript
function exploreCave(message1, message2) {
    // Your implementation here
}
```

### 📥 Input Parameters

| Parameter | Type | Description | Example |
|-----------|------|-------------|---------|
| `message1` | `string` | First explorer's message | `"Hello there"` |
| `message2` | `string` | Second explorer's message | `"All clear"` |

### 📤 Expected Output

| Scenario | Condition | Output Format | 
|----------|-----------|---------------|
| 🔊 **Echo Detected** | `message1 === message2` | `"Echo: [message]"` |
| 💬 **Different Messages** | `message1 !== message2` | `"[message1] & [message2]"` |

---

## 🎮 Examples in Action

### 📢 Echo Scenario
```javascript
exploreCave("Hello", "Hello")
```
**Output:** `"Echo: Hello"`

*The explorer hears their own voice bouncing back from the cave walls!*

---

### 🗣️ Communication Scenario  
```javascript
exploreCave("Help needed", "On my way")
```
**Output:** `"Help needed & On my way"`

*Two different explorers are communicating with each other.*

---

### 🌟 More Examples

```javascript
// Empty messages (still an echo!)
exploreCave("", "")
// Returns: "Echo: "

// Case matters!
exploreCave("SOS", "sos") 
// Returns: "SOS & sos"

// Numbers as strings
exploreCave("Cave 1", "Cave 2")
// Returns: "Cave 1 & Cave 2"
```

---

## 🎯 Your Mission

Build the `exploreCave` function that helps cave explorers understand whether they're hearing an echo of their own voice or receiving a message from another explorer. Good luck, explorer! 🗺️
