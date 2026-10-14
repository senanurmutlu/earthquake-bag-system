# earthquake-bag-system
# Earthquake Emergency Bag Management System

A robust, console-based Object-Oriented Programming (OOP) application developed in Java to dynamically plan, calculate, and manage emergency earthquake bags based on family demographics, risk levels, and strict weight constraints.

## Overview
This system helps households prepare optimized emergency kits by assessing family member types (Adults, Elderly, Babies, Chronic Patients), evaluating environmental risk levels (High, Medium, Low), and automatically aggregating essential items from structured data files while enforcing maximum bag capacity limits.

---

## Key Features & Architecture

### 1. Object-Oriented Hierarchy & Polymorphism
- **`Person` (Abstract Class):** Base class defining core user properties. Subclasses (`Adult`, `Elderly`, `Baby`, `ChronicPatient`) implement specific category files and rules.
- **`Weighable` (Interface):** Implemented by items to standardize weight tracking across different supply categories.
- **`Item`:** Encapsulates item names and individual weights.

### 2. Exception Handling (`OverweightBagException`)
- Implements custom exception handling to monitor total bag weight against user-defined capacity limits.
- Gracefully catches capacity overflows, alerts users with warnings, and prevents unsafe bag configurations.

### 3. File I/O & Dynamic Item Loading (`ItemLoader`)
- Reads base requirements and category-specific supplies dynamically from structured `.txt` files using `;` delimiters.
- Allows users to append new emergency items directly into category text files at runtime.

---

## Project Structure
```text
earthquake-bag-system/
│
├── Main.java                # Core application logic, menu loop, and bag generation
├── adult_items.txt          # Default supplies for adults
├── adult_items (1).txt      # Backup/alternative adult list
├── baby_items.txt           # Essential baby supplies & infant gear
├── elderly_items.txt        # Specialized supplies for elderly members
├── chronic_items.txt        # Medication & medical device requirements
├── base_items_high.txt      # High-risk emergency baseline items
├── base_items_medium.txt    # Medium-risk emergency baseline items
├── base_items_low.txt       # Low-risk emergency baseline items
└── README.md                # Project documentation
