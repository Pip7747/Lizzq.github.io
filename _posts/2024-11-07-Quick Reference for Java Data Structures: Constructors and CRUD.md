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

### Constructor

```java
List<Integer> list = new ArrayList<>();
Add elements
java
Copy code
list.add(10);
list.add(20);
Remove elements
java
Copy code
list.remove(Integer.valueOf(10)); // Remove by value
list.remove(0); // Remove by index
Update element
java
Copy code
list.set(0, 30); // Update element at index 0 to 30
Retrieve element
java
Copy code
int value = list.get(0); // Get value at index 0
int index = list.indexOf(20); // Find index of element 20 
Characteristics
Fast for random access
Slower for inserting and removing elements

## 2. LinkedList 
LinkedList is a doubly-linked list, suitable for frequent inserts and deletes but slower for random access.

### Constructor
java
Copy code
List<String> linkedList = new LinkedList<>();
Add elements
java
Copy code
linkedList.add("A");
linkedList.add("B");
linkedList.addFirst("Head"); // Add at the beginning
linkedList.addLast("Tail"); // Add at the end
Remove elements
java
Copy code
linkedList.remove("A"); // Remove element "A"
linkedList.removeFirst(); // Remove first element
linkedList.removeLast(); // Remove last element
Update element
java
Copy code
linkedList.set(1, "NewB"); // Update element at index 1 to "NewB"
Retrieve element
java
Copy code
String value = linkedList.get(0); // Get value at index 0
boolean contains = linkedList.contains("B"); // Check if "B" exists
Characteristics
Great for frequent insertions and deletions
Slower for random access
## 3. HashMap
HashMap is a key-value pair data structure. It allows for fast lookup, insertion, and deletion based on the key.

### Constructor
java
Copy code
Map<String, Integer> map = new HashMap<>();
Add elements
java
Copy code
map.put("one", 1);
map.put("two", 2);
Remove elements
java
Copy code
map.remove("one"); // Remove by key
Retrieve element
java
Copy code
int value = map.get("two"); // Get value associated with "two"
boolean contains = map.containsKey("one"); // Check if key "one" exists
Characteristics
Fast lookups, insertions, and deletions based on key
No ordering of elements
## 4. TreeMap
TreeMap is a map implementation that stores key-value pairs in a sorted order.

### Constructor
java
Copy code
Map<String, Integer> treeMap = new TreeMap<>();
Add elements
java
Copy code
treeMap.put("banana", 1);
treeMap.put("apple", 2);
Remove elements
java
Copy code
treeMap.remove("banana"); // Remove by key
Retrieve element
java
Copy code
int value = treeMap.get("apple"); // Get value associated with "apple"
Characteristics
Sorted by keys in natural order or by a comparator
Slower than HashMap for most operations
## 5. HashSet
HashSet is a collection of unique elements, which does not allow duplicate values.

### Constructor
java
Copy code
Set<String> set = new HashSet<>();
Add elements
java
Copy code
set.add("apple");
set.add("banana");
Remove elements
java
Copy code
set.remove("apple"); // Remove element "apple"
Check if an element exists
java
Copy code
boolean contains = set.contains("banana"); // Check if "banana" exists
Characteristics
Stores unique elements
Does not guarantee order of elements
markdown
Copy code

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
Characteristics: Ordered, no duplicates, useful when sorted order is required.

## 7. Stack
Stack is a last-in, first-out (LIFO) data structure.

### Constructor
java
Copy code
Stack<Integer> stack = new Stack<>();

// Add elements
stack.push(10);
stack.push(20);

// Remove elements
stack.pop(); // Removes and returns the top element

// Retrieve element
int top = stack.peek(); // Returns the top element
boolean isEmpty = stack.isEmpty(); // Check if stack is empty
Characteristics: Suitable for LIFO operations.

## 8. Queue (LinkedList Implementation)
Queue is a first-in, first-out (FIFO) data structure.

### Constructor
java
Copy code
Queue<Integer> queue = new LinkedList<>();

// Add elements
queue.offer(10);
queue.offer(20);

// Remove elements
queue.poll(); // Removes and returns the front element

// Retrieve element
int front = queue.peek(); // Returns the front element
boolean isEmpty = queue.isEmpty(); // Check if queue is empty
Characteristics: Suitable for FIFO operations.

## 9. PriorityQueue
PriorityQueue is a queue that sorts elements based on their priority, where elements are dequeued in priority order.

### Constructor
java
Copy code
PriorityQueue<Integer> priorityQueue = new PriorityQueue<>();

// Add elements
priorityQueue.offer(30);
priorityQueue.offer(10);
priorityQueue.offer(20);

// Remove elements
priorityQueue.poll(); // Removes and returns the element with the highest priority

// Retrieve element
int highestPriority = priorityQueue.peek(); // Returns the element with the highest priority
Characteristics: Elements are dequeued by priority, useful when dynamic sorting is needed.

### Explanation:

- All content is enclosed within proper Markdown syntax, including headings, lists, and Java code blocks.
- Each Java code section is wrapped in triple backticks with `java` to enable syntax highlighting in supported Markdown environments.
- The explanations and code examples follow the logical structure of **ArrayList**, **LinkedList**, **HashMap**, **TreeMap**, and **HashSet** sections.

Let me know if this is the format you were looking for!
