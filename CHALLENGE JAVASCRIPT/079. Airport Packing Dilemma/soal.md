# 🧳 Dilema Packing Bandara

## 📋 Gambaran Challenge (Versi Bahasa Indonesia)
**Difficulty Level:** `Easy` 🟢

Anda adalah seorang traveler di counter check-in bandara, mencoba memasukkan barang-barang Anda ke dalam carry-on bag. Misi Anda adalah membuat smart packing assistant yang menentukan apakah semua item Anda dapat masuk berdasarkan kapasitas bag.

## 🎯 Objective
Buat function bernama `canFitInBag` yang secara intelligent membandingkan jumlah item dengan kapasitas berdasarkan size bag dan return apakah semuanya muat.

## 📝 Function Specifications

### Function Name
```javascript
canFitInBag(items, bagSize)
```

### Parameters
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `items` | `Array<string>` | Array string yang merepresentasikan item yang ingin Anda pack |
| `bagSize` | `string` | Size bag Anda: `"small"`, `"medium"`, atau `"large"` |

### Return Value
* **Type:** `boolean`
* **Return:**
   * `true` jika semua item dapat masuk dalam bag
   * `false` jika item melebihi kapasitas bag

## 📏 Bag Capacity Rules
Kapasitas bag bervariasi berdasarkan size:

| 🎒 Bag Size | 📦 Maximum Items | Icon |
|-------------|------------------|------|
| **Small** | 3 items | 🎒 |
| **Medium** | 5 items | 🧳 |
| **Large** | 7 items | 🛄 |

## 🔧 Implementation Requirements
**Poin Penting yang Harus Diingat:**
* ✅ Gunakan **string comparison** untuk validasi bag size
* ✅ Gunakan **array length** untuk menghitung jumlah item
* ✅ Bandingkan jumlah item dengan batas kapasitas berdasarkan size
* ✅ Return boolean result berdasarkan perbandingan

**Logic Flow:**
1. Tentukan kapasitas bag berdasarkan parameter `bagSize`
2. Hitung jumlah item dalam `items` array
3. Bandingkan jumlah item dengan kapasitas bag
4. Return `true` jika items ≤ kapasitas, `false` sebaliknya

## 💡 Contoh Usage

```javascript
// Contoh 1: Item muat dalam medium bag
const items1 = ["baju", "celana", "sepatu", "buku"];
const result1 = canFitInBag(items1, "medium"); // Harus return true (4 ≤ 5)

// Contoh 2: Terlalu banyak item untuk small bag
const items2 = ["laptop", "charger", "headphones", "notebook", "pulpen"];
const result2 = canFitInBag(items2, "small"); // Harus return false (5 > 3)

// Contoh 3: Perfect fit untuk large bag
const items3 = ["kamera", "lensa", "tripod", "baterai", "memory card", "cleaning kit", "manual"];
const result3 = canFitInBag(items3, "large"); // Harus return true (7 = 7)
```

## 🚀 Solution

```javascript
function canFitInBag(items, bagSize) {
    // Define kapasitas berdasarkan bag size
    let capacity;
    
    switch (bagSize) {
        case "small":
            capacity = 3;
            break;
        case "medium":
            capacity = 5;
            break;
        case "large":
            capacity = 7;
            break;
        default:
            return false; // Invalid bag size
    }
    
    // Hitung item dan bandingkan dengan kapasitas
    return items.length <= capacity;
}
```

**Selamat coding, traveler!** ✈️
