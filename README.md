05_Hashing_Lab
==============

Implement a hash table in C++

Requirements
------------

1. `keyExists`, `find`, `remove`, and `size` should all be O(1)
2. `add` should be reasonably fast. Use linear probing to find an open slot in the hash table. This will be O(1), on average, except when `grow` is called.
3. `grow` should be O(n)
4. Do not leak memory


Reading
=======
"Open Data Structures," Chapter 5, except for 5.2.3. http://opendatastructures.org/ods-cpp/5_Hash_Tables.html

Questions
=========

#### 1. Which of the above requirements work, and which do not? For each requirement, write a brief response.

1. The above functions run in constant time.
2. When grow is not called the runtime is roughly O(1)
3. Grow does not always work correctly, but should run in linear time.
4. All unused objects are deleted

#### 2. I decided to use two function (`keyExists` and `find`) to enable lookup of keys. Another option would have been to have `find` return a `T*`, which would be `NULL` if an item with matching key is not found. Which design do you think would be better? Explain your reasoning. You may notice that the designers of C++ made the same decision I did when they designed http://www.cplusplus.com/reference/unordered_map/unordered_map/

Using keyExists and and find is a safer way to deal with the table because there is no chance to be passed refrences within the array that could potentially be dangerous.  Using keyExists and find will throw an exception before any damage can be done.

#### 3. What is one question that confused you about this exercise, or one piece of advice you would share with students next semester?

Spend a good amount of time learning how your hashing function works will be benficial to figuring out collisions.