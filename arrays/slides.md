---
theme: excali-slide
background: https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&w=1920&q=80
class: text-center
highlighter: shiki
lineNumbers: true
info: |
  ## INF 221 - Data Structures and Algorithms
  Chapter 2: Arrays
drawings:
  persist: false
transition: slide-left
title: Arrays - Data Structures
mdc: true
---

# Arrays 📊

## INF 221 – Data Structures and Algorithms

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Chapter 2 <carbon:arrow-right class="inline"/>
  </span>
</div>

---
transition: fade-out
layout: two-cols
---

# What is Array? 🗂️

Array is a **linear data structure** where all elements are arranged sequentially.

::right::

<div class="mt-8">

### Key Characteristics

- Collection of elements of **same data type**
- Stored at **contiguous memory locations**
- Zero-indexed (first element at index 0)
- Fixed size when created

</div>

---
layout: center
class: text-center
---

# Memory Representation 💾

<div class="grid grid-cols-5 gap-4 mt-8 justify-center">
  <div v-for="i in 5" :key="i" class="p-4 border-2 border-blue-400 rounded-lg bg-blue-50">
    <div class="text-xs text-gray-600">Index {{ i-1 }}</div>
    <div class="text-2xl font-bold text-blue-600">{{ i * 10 }}</div>
    <div class="text-xs text-gray-500 mt-2">4 bytes</div>
  </div>
</div>

<div class="mt-8 text-sm text-gray-600">
Assuming size of int is 4 bytes
</div>

---
transition: slide-up
---

# Why Use Arrays? 🎯

<v-clicks>

- ✅ **Efficient Access**: Direct access to any element using index
- ✅ **Memory Management**: Consecutive memory allocation
- ✅ **Faster Operations**: Sequential data manipulation
- ✅ **Better than Individual Variables**: Manage collections easily
- ✅ **Sequential Representation**: Perfect for list implementation

</v-clicks>

---
layout: two-cols
---

# Array Properties 📋

<v-clicks>

### Data Types Support
- Primitive types: `int`, `double`, `boolean`
- Object types: `String`, `Integer`
- Any Java data type

### Dimensions
- One-dimensional (vector)
- Multi-dimensional (matrix)

</v-clicks>

::right::

<v-clicks>

### Size Characteristics
- **Fixed Size**: Cannot change after creation
- **Dynamic Alternatives**:
  - Java: `ArrayList`
  - Python: `List`
- **C Language**: Strictly fixed size

</v-clicks>

---
transition: fade
---

# Types of Arrays 🔢

<div class="grid grid-cols-2 gap-8 mt-8">

<div>

## Based on Size 📏

<v-clicks>

- **Fixed Size**
  - Size determined at creation
  - Cannot be modified
  
- **Dynamic Size**
  - Can grow/shrink
  - ArrayList, List implementations

</v-clicks>

</div>

<div>

## Based on Dimension 📐

<v-clicks>

- **One-dimensional**
  - Vector (linear array)
  
- **Multi-dimensional**
  - Two-dimensional (matrix)
  - Three-dimensional (data cube)
  - N-dimensional

</v-clicks>

</div>

</div>

---
layout: center
---

# Array Declaration & Initialization 🚀

Three common approaches in Java

---

# Method 1: Single Statement 💡

Declare and initialize in one line
```java {all|1|2|3}
// Syntax: dataType[] arrayName = {values};
int[] numbers = {1, 2, 3, 4, 5};
String[] languages = {"Java", "Python", "HTML", "CSS"};
```

<v-click>

<div class="mt-8 p-4 bg-green-50 border-l-4 border-green-500 rounded">
✨ <strong>Quick & Clean</strong>: Perfect when you know the values upfront
</div>

</v-click>

---

# Method 2: Separate Statements 📝

Declare first, initialize later
```java {all|1-2|4-5|7-8}
// Declaration
int[] numbers;
String[] languages;

// Initialization
numbers = new int[]{1, 2, 3, 4, 5};

languages = new String[]{"Java", "Python", "HTML", "CSS"};
```

<v-click>

<div class="mt-8 p-4 bg-blue-50 border-l-4 border-blue-500 rounded">
🔧 <strong>Flexible</strong>: Useful when initialization depends on logic
</div>

</v-click>

---

# Method 3: Default Values ⚙️

Create array with fixed size
```java {all|1|2|3}
int[] prime_numbers = new int[5];      // Default: 0
boolean[] failed = new boolean[5];      // Default: false
String[] student_names = new String[5]; // Default: null
```

<v-click>

<div class="mt-8 grid grid-cols-3 gap-4">
  <div class="p-4 bg-purple-50 rounded text-center">
    <div class="text-sm text-gray-600">int</div>
    <div class="text-2xl font-bold">0</div>
  </div>
  <div class="p-4 bg-pink-50 rounded text-center">
    <div class="text-sm text-gray-600">boolean</div>
    <div class="text-2xl font-bold">false</div>
  </div>
  <div class="p-4 bg-orange-50 rounded text-center">
    <div class="text-sm text-gray-600">String</div>
    <div class="text-2xl font-bold">null</div>
  </div>
</div>

</v-click>

---
transition: slide-left
---

# Printing Arrays 🖨️

## Example 1: Simple Approach
```java {all|3|4-6}
public class Chapter2 {
    public static void main(String[] args) {
        int[] array1 = new int[]{1, 2, 3, 4, 5};
        for(int i = 0; i < array1.length; i++) {
            System.out.print(array1[i] + " ");
        }
    }
}
```

<v-click>

<div class="mt-4 p-3 bg-gray-100 rounded font-mono text-sm">
Output: 1 2 3 4 5
</div>

</v-click>

---

# Printing Arrays 🖨️

## Example 2: Using Methods
```java {all|2-6|9-10}
public class Chapter2 {
    public void printArray(int[] arr) {
        for(int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }
    public static void main(String[] args) {
        Chapter2 arrUtil = new Chapter2();
        int[] array2 = {3, 7, 11, 8, 24};
        arrUtil.printArray(array2);
    }
}
```

---

# Array Operations Overview 🔧

<div class="grid grid-cols-2 gap-8 mt-8">

<div v-click>

## Unsorted Arrays 📋

- Search: Linear Search
- Insert: At end or any position
- Delete: Search then remove
- Simple but slower

</div>

<div v-click>

## Sorted Arrays 📊

- Search: Binary Search
- Insert: Maintain order
- Delete: Search then remove
- Faster search operations

</div>

</div>

---
layout: center
class: text-center
---

# Unsorted Array Operations 🔀

Working with unordered data

---

# Search in Unsorted Array 🔍

Linear traversal from first to last element
```java {all|2-5|7}
static int searchElement(int arr[], int key) {
    for(int i = 0; i < arr.length; i++)
        if (arr[i] == key)
            return i;
    return -1; // if the key is not found
}

int[] array2 = {3, 7, 11, 8, 24};
int index = searchElement(array2, 8);
// Returns: 3
```

<v-click>

<div class="mt-8 flex justify-center">
  <div class="p-6 bg-red-50 border-2 border-red-400 rounded-lg">
    <div class="text-sm text-gray-600">Time Complexity</div>
    <div class="text-3xl font-bold text-red-600">O(n)</div>
  </div>
</div>

</v-click>

---

# Insert at End 📌

Fast insertion without position consideration
```java {all|2-6|8}
static int insertEnd(int arr[], int size, int inserted, int nthIndex) {
    if (nthIndex >= size) {
        System.out.println("Not enough space!");
        return nthIndex;
    }
    arr[nthIndex] = inserted;
    return nthIndex + 1;
}
```

<div class="mt-6 grid grid-cols-5 gap-2">
  <div class="p-3 border-2 rounded bg-gray">12</div>
  <div class="p-3 border-2 rounded bg-gray">20</div>
  <div class="p-3 border-2 rounded bg-gray">6</div>
  <div v-click class="p-3 border-2 rounded bg-green-50 border-green-500">35</div>
  <div class="p-3 border-2 rounded bg-gray">0</div>
</div>

<v-click>

<div class="mt-6 flex justify-center">
  <div class="p-6 bg-green-50 border-2 border-green-400 rounded-lg">
    <div class="text-sm text-gray-600">Time Complexity</div>
    <div class="text-3xl font-bold text-green-600">O(1)</div>
  </div>
</div>

</v-click>

---

# Insert at Any Position 🎯

Insert element and shift others
```java {all|2-7|9-10|11}
static int insertAny(int[] arr, int nthIndex, int inserted, int anyIndex) {
    if(anyIndex >= arr.length || nthIndex >= arr.length) {
        System.out.println("Invalid operation!");
        return nthIndex;
    }
    
    // Shift elements to the right
    for(int i = nthIndex - 1; i >= anyIndex; i--)
        arr[i + 1] = arr[i];
    
    arr[anyIndex] = inserted;
    return nthIndex + 1;
}
```

<v-click>

<div class="mt-6 flex justify-center">
  <div class="p-6 bg-orange-50 border-2 border-orange-400 rounded-lg">
    <div class="text-sm text-gray-600">Time Complexity</div>
    <div class="text-3xl font-bold text-orange-600">O(n)</div>
  </div>
</div>

</v-click>

---

# Delete Operation 🗑️

Search element, then delete and shift left
```java {all|2-6|8-9|10}
static int deleteElement(int arr[], int nthIndex, int key) {
    int ind = searchElement(arr, key);
    if(ind == -1) {
        System.out.println("Element not found!");
        return nthIndex;
    }
    
    // Shift elements to the left
    for(int i = ind; i < nthIndex - 1; i++)
        arr[i] = arr[i + 1];
    
    arr[nthIndex - 1] = 0;
    return nthIndex - 1;
}
```

<v-click>

<div class="mt-6 flex justify-center">
  <div class="p-6 bg-red-50 border-2 border-red-400 rounded-lg">
    <div class="text-sm text-gray-600">Time Complexity</div>
    <div class="text-3xl font-bold text-red-600">O(n)</div>
  </div>
</div>

</v-click>

---
layout: center
class: text-center
---

# Sorted Array Operations 📈

Working with ordered data

---

# Binary Search 🎯

Efficient search in sorted arrays
```java {all|2-11|3-4|5-8}
static int binarySearch(int arr[], int low, int high, int key) {
    while(low <= high) {
        int mid = (low + high) / 2;
        if(key == arr[mid])
            return mid;
        if (key < arr[mid])
            high = mid - 1;
        else
            low = mid + 1;
    }
    return -1;
}

int[] array4 = {10, 20, 30, 40, 50};
int index = binarySearch(array4, 0, array4.length - 1, 30);
// Returns: 2
```

---

# Binary Search - Recursive 🔄

Alternative recursive implementation
```java {all|2-9|3-4|5-8}
static int binarySearch(int arr[], int low, int high, int key) {
    if(low <= high) {
        int mid = (low + high) / 2;
        if (key == arr[mid])
            return mid;
        if (key > arr[mid])
            return binarySearch(arr, (mid + 1), high, key);
        return binarySearch(arr, low, (mid - 1), key);
    }
    return -1;
}
```

<v-click>

<div class="mt-8 flex justify-center">
  <div class="p-6 bg-purple-50 border-2 border-purple-400 rounded-lg">
    <div class="text-sm text-gray-600">Time Complexity</div>
    <div class="text-3xl font-bold text-purple-600">O(log n)</div>
    <div class="text-sm text-gray-500 mt-2">Much faster than linear search!</div>
  </div>
</div>

</v-click>

---

# Time Complexity Comparison ⚡

<div class="mt-8">

| Operation | Unsorted Array | Sorted Array |
|-----------|----------------|--------------|
| **Search** | O(n) - Linear | O(log n) - Binary |
| **Insert at End** | O(1) | O(n) |
| **Insert at Position** | O(n) | O(n) |
| **Delete** | O(n) | O(n) |

</div>

<v-click>

<div class="mt-8 p-4 bg-blue-50 border-l-4 border-blue-500 rounded">
💡 <strong>Key Insight</strong>: Sorted arrays excel at searching but require maintaining order
</div>

</v-click>

---
layout: two-cols
---

# Research Questions 📝

## Question 1
Insert element into sorted array
```java
int[] myArray = new int[5];
myArray[0] = 10;
myArray[1] = 20;
myArray[2] = 30;
myArray[3] = 40;

int key_inserted = 24;
```

Expected Output: `10 20 24 30 40`

::right::

## Question 2
Delete element from sorted array
```java
// Using same array
int key_deleted = 20;
```

Expected Output: `10 24 30 40`

<v-click>

<div class="mt-8 p-4 bg-yellow-50 border-l-4 border-yellow-500 rounded text-sm">
⚠️ Remember to maintain sorted order!
</div>

</v-click>

---
layout: center
class: text-center
---

# Project-1 🎮

## HANGMAN

<div class="text-6xl mt-8">
🎯
</div>

<div class="mt-8 text-gray-600">
Build a classic word-guessing game using arrays!
</div>

---
layout: center
class: text-center
---

# Summary 📚

<v-clicks>

- Arrays store **same-type elements** in **contiguous memory**
- **Zero-indexed** with **fixed size** at creation
- **Unsorted arrays**: Fast insertion, slower search
- **Sorted arrays**: Fast search (binary), maintain order
- Choose the right array type for your needs!

</v-clicks>

---
layout: center
class: text-center
---

# Thank You! 🙏

## Questions?

<div class="mt-12 text-gray-500 text-sm">
INF 221 – Data Structures and Algorithms<br/>
Chapter 2: Arrays
</div>