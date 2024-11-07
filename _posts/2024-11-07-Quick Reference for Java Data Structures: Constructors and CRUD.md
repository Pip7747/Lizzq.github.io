---
title: "Java Data Structures: Constructors and CRUD Operations"
layout: post
categories: [Coding, Study]
tags: [Java, Data Structures, Algorithms]
---

# Java Data Structures - CRUD Operations

While learning algorithms and exploring data structures, it can be extremely helpful to familiarize ourselves with the constructors and CRUD operations (Create, Read, Update, Delete) for commonly used data structures. This guide provides a quick reference for each of these operations across different Java data structures.


## 1. ArrayList

`ArrayList` is a resizable array implementation, which is fast for random access but slower for inserting and removing elements.

```java
//Constructor
List<Integer> list = new ArrayList<>();

// Add elements
list.add(10); 
list.add(20);

// Remove elements
list.remove(Integer.valueOf(10)); // Remove by value
list.remove(0); // Remove by index

// Update element
list.set(0, 30); // Update element at index 0 to 30

// Retrieve element
int value = list.get(0); // Get value at index 0
int index = list.indexOf(20); // Find index of element 20  ```
### Characteristics
Fast for random access
Slower for inserting and removing elements

## 2. LinkedList 
LinkedList is a doubly-linked list, suitable for frequent inserts and deletes but slower for random access.

### Constructor
```java
List<String> linkedList = new LinkedList<>();

// Add elements
linkedList.add("A");
linkedList.add("B");
linkedList.addFirst("Head"); // Add at the beginning
linkedList.addLast("Tail"); // Add at the end

// Remove elements
linkedList.remove("A"); // Remove element "A"
linkedList.removeFirst(); // Remove first element
linkedList.removeLast(); // Remove last element

// Update element
linkedList.set(1, "NewB"); // Update element at index 1 to "NewB"

// Retrieve element
String value = linkedList.get(0); // Get value at index 0
boolean contains = linkedList.contains("B"); // Check if "B" exists  ```
### Characteristics
Great for frequent insertions and deletions
Slower for random access
## 3. HashMap
HashMap is a key-value pair data structure. It allows for fast lookup, insertion, and deletion based on the key.

```java
//Constructor
Map<Integer, String> map = new HashMap<>();

// Add elements
map.put(1, "One");
map.put(2, "Two");

// Remove elements
map.remove(1); // Remove key-value pair with key 1

// Update element
map.put(2, "Two Updated"); // Update value for key 2

// Retrieve element
String value = map.get(2); // Get value associated with key 2
boolean containsKey = map.containsKey(2); // Check if key 2 exists
boolean containsValue = map.containsValue("Two Updated"); // Check if value "Two Updated" exists ```
### Characteristics
Fast lookups, insertions, and deletions based on key
No ordering of elements
## 4. TreeMap
TreeMap is a map implementation that stores key-value pairs in a sorted order.


```java
//Constructor
Map<Integer, String> treeMap = new TreeMap<>();

// Add elements
treeMap.put(3, "Three");
treeMap.put(1, "One");
treeMap.put(2, "Two");

// Remove elements
treeMap.remove(1); // Remove key-value pair with key 1

// Update element
treeMap.put(2, "Two Updated");

// Retrieve element
String value = treeMap.get(3); // Get value associated with key 3
boolean containsKey = treeMap.containsKey(2); // Check if key 2 exists```
### Characteristics
Sorted by keys in natural order or by a comparator
Slower than HashMap for most operations
## 5. HashSet
HashSet is a collection of unique elements, which does not allow duplicate values.

```java
// Constructor
Set<String> set = new HashSet<>();

// Add elements
set.add("Apple");
set.add("Banana");

// Remove elements
set.remove("Apple");

// Retrieve element
boolean contains = set.contains("Banana"); // Check if "Banana" exists ```

### Characteristics: Unordered, no duplicate elements, fast for lookups and inserts.


## 6. TreeSet
TreeSet is a sorted set based on a red-black tree, with elements ordered either by natural order or custom comparator.

### Constructor
java
Copy code
// Constructor
Set<String> treeSet = new TreeSet<>();

// Add elements
treeSet.add("Apple");
treeSet.add("Banana");

// Remove elements
treeSet.remove("Apple");

// Retrieve element
boolean contains = treeSet.contains("Banana"); // Check if "Banana" exists
### Characteristics: Ordered, no duplicates, useful when sorted order is required.

## 7. Stack
Stack is a last-in, first-out (LIFO) data structure.

```java
// Constructor
Stack<Integer> stack = new Stack<>();

// Add elements
stack.push(10);
stack.push(20);

// Remove elements
stack.pop(); // Removes and returns the top element

// Retrieve element
int top = stack.peek(); // Returns the top element
boolean isEmpty = stack.isEmpty(); // Check if stack is empty
```
### Characteristics: Suitable for LIFO operations.

## 8. Queue (LinkedList Implementation)
Queue is a first-in, first-out (FIFO) data structure.

```java
// Constructor
Queue<Integer> queue = new LinkedList<>();

// Add elements
queue.offer(10);
queue.offer(20);

// Remove elements
queue.poll(); // Removes and returns the front element

// Retrieve element
int front = queue.peek(); // Returns the front element
boolean isEmpty = queue.isEmpty(); // Check if queue is empty
```
###Characteristics: Suitable for FIFO operations.

## 9. PriorityQueue
PriorityQueue is a queue that sorts elements based on their priority, where elements are dequeued in priority order.

```java
//Constructor
PriorityQueue<Integer> priorityQueue = new PriorityQueue<>();

// Add elements
priorityQueue.offer(30);
priorityQueue.offer(10);
priorityQueue.offer(20);

// Remove elements
priorityQueue.poll(); // Removes and returns the element with the highest priority

// Retrieve element
int highestPriority = priorityQueue.peek(); // Returns the element with the highest priority ```
### Characteristics: Elements are dequeued by priority, useful when dynamic sorting is needed.

## Explanation:

- All content is enclosed within proper Markdown syntax, including headings, lists, and Java code blocks.
- Each Java code section is wrapped in triple backticks with `java` to enable syntax highlighting in supported Markdown environments.
- The explanations and code examples follow the logical structure of **ArrayList**, **LinkedList**, **HashMap**, **TreeMap**, and **HashSet** sections.
