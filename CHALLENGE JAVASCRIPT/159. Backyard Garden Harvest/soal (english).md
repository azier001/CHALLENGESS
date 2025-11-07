# 🥕 Backyard Garden Harvest

## 🌿 Challenge Overview

**Difficulty:** Easy
**Goal:** Combine two baskets of vegetables into a single harvest list.

---

## 🧺 Task Description

Create a function named **`harvestVegetables`** that receives two parameters:

* **`carrotBasket`** *(array)*: An array of strings representing the carrots harvested from the carrot basket.
* **`tomatoBasket`** *(array)*: An array of strings representing the tomatoes harvested from the tomato basket.

The function should combine the vegetables from both baskets into a single array representing the total harvest.

---

## 🧩 Function Requirements

### ✅ Parameters

* `carrotBasket`: Array of strings (e.g., `["carrot1", "carrot2"]`)
* `tomatoBasket`: Array of strings (e.g., `["tomato1", "tomato2"]`)

### 🎯 Return Value

* Returns **an array of strings** containing all the harvested vegetables from both baskets.
* The order should be:

  1. All **carrots** first (in their original order)
  2. Followed by all **tomatoes** (in their original order)

---

## 🌱 Summary

* Combine two arrays into one harvest list.
* Maintain the original order of both carrot and tomato baskets.
* Simple and efficient solution using array spread syntax (`...`).

> 🍅 Tip: You can also use `concat()` to achieve the same result!
