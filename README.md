### Set up

python3 -m venv ./venv_alg
source ./venv_alg/bin/activate
export PYTHONPATH="${PYTHONPATH}:./" - 'Rexecute the next command from your project dir'
pip3 install -r requirements.txt



## Program 

https://algomap.io


#### LeetCode's Interview Crash Course Data Structures and Algorithms:


TODO be sure you can solve (similar questions):
0. https://leetcode.com/problems/count-number-of-nice-subarrays/description
1. https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/
2. https://leetcode.com/problems/summary-ranges/
3. https://leetcode.com/problems/product-of-array-except-self/description/
4. https://leetcode.com/problems/merge-intervals/description/
5. https://leetcode.com/problems/rotate-list/






## top patterns you have to know 

https://www.youtube.com/watch?v=DjYZk8nrXVY


```text
1. Two pointers - "intersection, merging of sets, intervals"
2. Sliding window
3. Prefix sum
4. Binary search 
```


list of the MUST HAVE tasks:

- https://leetcode.com/discuss/general-discussion/460599/blind-75-leetcode-questions




## Cracking the coding interview (algorithms solving advices):

1. **listen carefully** - Yes, you do want to listen to the problem and make sure you heard it correctly. You do want to ask questions about anything you're unsure about.

2. **Draw Example:** When you hear a question, get out of your chair, go to the whiteboard, and draw an example. An example can dramatically improve your ability to solve an interview question

3. **Did you understans the task correctly:** Listen carefully to the problem, and be sure that you've mentally recorded any unique information in the problem.

### Draw example:

1. **Generalize your example:** Be careful. It's very easy to inadvertently draw a special case. Try to make the best example you can. If it later turns out your example isn't quite right, you can and should fix it.

2. **State a Brute Force:** -  It's okay and expected that your initial algorithm won't be very optimal. (You don't want your inter­ viewer to think that you're struggling to see even the easy solution.) It's okay that this initial solution is terrible. Explain what the space and time complexity is, and then dive into improvements.

2.1. **Ask interviewer** if brute force OK in this case or some specific complexity. As is it OK if we start from brute force and after that move to the optimisation. 

3. **Recognize algorithms and patterns:** Recognize algorithms and patterns which can be used for the problem solving

4. **Save space on the board:** Implement Start coding in the far top left corner of the whiteboard (you'll need the space). Remember that you only have a short amount of code

5. **One more time** - If you don't understand exactly what you're about to write, you'll struggle to code it!

### 0ptimize your solution

1. **Walk Through the code:** Be sure you have clear vision of the implementation - after you've nailed down an optimal algorithm, don't just dive into coding. Take a moment to solidify your understanding of the algorithm.
Walk through your algorithm and get a feel for the structure of the code. Know what the variables are and when they change.

2. **Precompute information:** Is there a way that you can reorganize the data (sorting, use hashtable, etc.) or compute some values upfront that will help save time in the long run.

2.1 **Use data structures**

3. **Write pseudocode** You can write pseudocode if you'd like. Be careful about what you write, write Basic steps:
- (1) Search array. 
- (2) Find biggest. 
- (3) Insert in heap:

Or brief logic:
("if p < q, move p. else move q") can be valuable. 

But when your pseudocode starts having for loops that are written in plain English, then you're essentially just writing sloppy code. It'd probably be faster to just write the code.




## Optimize&SolveTechnique :Lookfor BUD (Bottlenecks, Unnecessary work, Duplicated wor) 

1. **Bottlenecks:** A bottleneck is a part of your algorithm that slows down the overall runtime. 
For example, suppose you have a two-step algorithm:
- The first step isO(N log N) 
- The second step is O(N). 

The first step O(N log N) is the bottleneck despite you improve your second step O(n) to O(1)

2. **Unnecessary work**

<img src="./img/cracking_coding/1_unnec_work.png" alt="Getting started" />

<img src="./img/cracking_coding/2_unnec_work.png" alt="Getting started" />

3. **Duplicated work**
DRY - Do not Repeat Yourself.


## Optimize & Solve Technique #3: Simplify and Generalize

1. **simplify constraint** - simplify or tweak some constraint, such as the data type

2. **simplify the task** - We can solve the simplified ransom note problem with characters by simply creating an array and counting the characters. Each spot in the array corresponds to one letter. 

## Optimize & Solve Technique #4: Base Case and Build 


## What Good Coding Looks Like

1. **Correct:** The code should operate correctly on all expected and unexpected inputs.

2. **Efficient:** The code should operate as efficiently as possible in terms of both time and space. This "effi­
ciency" includes both the asymptotic (big O) efficiency and the practical, real-life efficiency. 

3. **Simple:** If you can do something in 10 lines instead of 100, you should. Code should be as quick as possible for a developer to write.

4. **Readable:** A different developer should be able to read your code and understand what it does and how it does it. Readable code has comments where necessary, but it implements things in an easily understandable way. That means that your fancy code that does a bunch of complex bit shifting is not necessarily good code.

5. **Maintainable:** Code should be reasonably adaptable to changes during the life cycle of a product and should be easy to maintain by other developers, as well as the initial developer.

## Use Data Structures Generously

**Bad example of data structures usage:**
```python 
# Bad use of data structures
def manage_bookstore():
    # A list of all books, mixed up with categories
    bookstore = [
        "Fiction", "1984", "To Kill a Mockingbird", "The Great Gatsby",
        "Non-Fiction

# Attempt to find all science fiction books
science_fiction_books = []
is_science_fiction = False
for book in bookstore:
    if book == "Science Fiction":
        is_science_fiction = True
    elif book in ["Fiction", "Non-Fiction"]:  # Assuming these are the only other categories
        is_science_fiction = False
    elif is_science_fiction:
        science_fiction_books.append(book)

print(f"Science Fiction Books: {science_fiction_books}")
```
Issues with this approach:

1. **Lack of Structure**: The list `bookstore` mixes categories and book titles, making it hard to distinguish between them.

2. **Inefficiency**: To find all books in a category, you have to iterate through the entire list and check for the category. This is inefficient compared to a dictionary lookup.

3. **Scalability and Maintenance**: Adding a new book or category becomes cumbersome and error-prone, as you have to place items correctly in the list.

4. **Readability**: The code for retrieving books in a particular category is not intuitive and requires additional logic, reducing readability.

This example shows how not thoughtfully using data structures can lead to inefficient, hard-to-maintain, and error-prone code, especially as the complexity of the data and operations increases.


**Good example of data structures usage**

```python
def manage_bookstore():
    bookstore = {
        "Fiction": ["1984", "To Kill a Mockingbird", "The Great Gatsby"],
        "Non-Fiction": ["Sapiens", "A Brief History of Time"],
        "Science Fiction": ["Dune", "Neuromancer", "Snow Crash"],
    }

    # Adding a book to a category
    bookstore["Fiction"].append("The Catcher in the Rye")

    # Adding a new category
    bookstore["Mystery"] = ["Murder on the Orient Express", "The Hound of the Baskervilles"]

    # Retrieving all books in a specific category
    science_fiction_books = bookstore.get("Science Fiction", [])

    print(f"Science Fiction Books: {science_fiction_books}")

manage_bookstore()
```

1. **Organized Data Structure**: 
   Utilizing a dictionary to categorize books by genre achieves an organized data structure. Each key represents a genre, with an associated value of a book list, enabling clear and straightforward identification and modification within categories.

2. **Ease of Access and Manipulation**: 
   This structure simplifies data access and manipulation. Adding a book to a category (`bookstore["Fiction"].append("The Catcher in the Rye")`) or introducing a new category (`bookstore["Mystery"] = [...]`) is accomplished with a single line of code.

3. **Scalability**: 
   The dictionary's structure is inherently scalable. As the collection grows, incorporating additional categories and books does not necessitate changes to the data handling logic.

4. **Default Values and Safe Access**: 
   Employing the `get` method (`bookstore.get("Science Fiction", [])`) for book retrieval ensures safe access to dictionary values and prevents `KeyError` exceptions by providing a default value for non-existent keys, useful for categories that are not yet present.

5. **Readability and Maintenance**: 
   With self-explanatory operations, the code's readability is ensured, which is essential for the maintenance of the codebase, particularly in larger projects or collaborative environments.

6. **Reduction in Errors**: 
   Appropriate data structuring and the use of dictionary methods diminish the risk of common programming errors, such as accessing an absent key.

7. **Flexibility for Future Enhancements**: 
   The current structure is flexible, accommodating future enhancements with ease. Whether it's adding new features like book searches across categories, updating book details, or removing categories, these tasks can be performed efficiently within this framework.



## Appropriate Code Reuse

## Modular

**Good example of modular usage:**
```python
def add(a, b):
    """Add two numbers."""
    return a + b

def subtract(a, b):
    """Subtract two numbers."""
    return a - b

def multiply(a, b):
    """Multiply two numbers."""
    return a * b

def divide(a, b):
    """Divide two numbers."""
    if b == 0:
        raise ValueError("Cannot divide by zero.")
    return a / b

def main():
    # Example usage of the modular functions
    x = 10
    y = 5

    print(f"{x} + {y} = {add(x, y)}")
    print(f"{x} - {y} = {subtract(x, y)}")
    print(f"{x} * {y} = {multiply(x, y)}")
    print(f"{x} / {y} = {divide(x, y)}")

if __name__ == "__main__":
    main()
```


**Bad example of modular usage:**
```python

def perform_operations(a, b):
    # Performing addition
    add_result = a + b
    print(f"{a} + {b} = {add_result}")

    # Performing subtraction
    subtract_result = a - b
    print(f"{a} - {b} = {subtract_result}")

    # Performing multiplication
    multiply_result = a * b
    print(f"{a} * {b} = {multiply_result}")

    # Performing division, without proper error handling
    if b != 0:
        divide_result = a / b
        print(f"{a} / {b} = {divide_result}")
    else:
        print("Cannot divide by zero.")

# Example usage
x = 10
y = 5
perform_operations(x, y)
```

## Flexible and Robust
1. **Implementation for solution** winner, doesn't mean you must assume that it's a 3x3 board. Why not write the code in a more general way that implements it for an NxN board?
Writing flexible, general-purpose code may also mean using variables instead of hard-coded values or using templates/ generics to solve a problem. If we can write our code to solve a more general problem.

## Error Checking

1. Of course, writing these error checks can be tedious and can waste precious time in an interview. The important thing is to point out that you would write the checks.

2. it may be best to leave some space where the error checks would go and indicate to your interviewer that you'll fill them in when you're finished with the rest of the code.


++++


# Programm
2. Dynamic programming
3. Binary search
4. Sliding window
5. Two pointers + 
6. Trees 
7. Graphs 
8. Pointers 




https://www.codecademy.com/
https://www.tryexponent.com/
https://www.educative.io/


### Basic Data-Structures
* 		Array
* 		Set
* 		Hashmap
* 		Linked List
* 		Stack
* 		Queue
* 		Tree
* 		Graph


Advanced Data-Structures (very often during interviews like Heaps and Binary Search Trees. LRU Caches and Tries come up less frequently but are becoming more common. Disjoint Sets and Skip Lists rarely come up, but even if not explicitly asked about them, they can be powerful tools to help you come up with quick and performant solutions.)

Getting a good understanding of the basic data-structures will make learning these advanced ones much easier. 
As we go into more advanced data-structures you’ll see they are usually made using the basic ones as building blocks.



### Complexity Problems
* 		Heap (a.k.a Priority Queue)
* 		LRU Cache
* 		Binary Search Tree (AVL, Redblack)
* 		Disjoint Set
* 		Trie
* 		Skip List


### Basic Searching/Traversal Algorithms

* 		Breadth First Search (BFS)
* 		Depth First Search (DFS)
* 		Binary Search


### Advanced Searching/Traversal Algorithms
* 		Quick Select
* 		Dijkstra
* 		Bellman-Ford
* 		A-star (rare)


### Sorting Algorithms (Know how to implement all of these without looking anything up)
* 		Quick Sort
* 		Merge Sort
* 		Topological Sort
* 		Counting Sort


### Important Topics
* 		Recursion
* 		Greedy Algorithms
* 		Dynamic Programming
* 		Bit Manipulation (AND, NOT, OR, XOR)



### Common Patterns (These patterns can be used to solve many similar algorithms questions)
* 		Backtracking
* 		Two Pointers
* 		Sliding Window
* 		Divide & Conquer
* 		Reservoir Sampling


### Math based problems
* 		Permutations
* 		Combinations
* 		Factorial
* 		Power Set



### Other Common Problems
* 		String to Integer
* 		Integer to String
* 		Adding huge numbers (that can’t fit into memory)
* 		Addition/Subtraction/Multiplication/Division without using operators


## Arrays:  
##### zero-based permutation:
Involves rearranging an array or list of integers so that each element is moved to the position specified by the value of the element itself.





### Preparation:
Bootcamp:
https://www.pramp.com/
https://www.interviewkickstart.com
https://interviewing.io/


Practice:
https://leetcode.com/
https://www.hackerrank.com/


Assisted:
https://www.pramp.com/dashboard#/
https://www.interviewbit.com/mock-interview/


MORE:

### Software Engineering Principles:
- Modularity: Writing code in a way that separates functionalities into distinct sections. For example, instead of having one large function that handles user authentication, database operations, and rendering data, you divide these into separate modules.

- DRY (Don't Repeat Yourself): Avoiding repetition of software patterns. For instance, if you have multiple functions that format user input, you can create a single utility function for formatting and use it everywhere.

- SOLID Principles: A set of design principles for object-oriented programming that enhance maintainability and scalability. For example, the Single Responsibility Principle dictates that a class should have only one reason to change.

- YAGNI (You Aren't Gonna Need It):
Principle: Focus on implementing things you need now, rather than anticipating and building features that might be needed in the future.
Example: If you're building a blog platform, don't implement a complex tagging and categorization system before basic posting functionality is completed and required.

### Architecture Patterns: 
- Understanding MVC (Model-View-Controller), Microservices, Monolith, etc. For instance, using a Microservices architecture to build a scalable e-commerce platform.

- Scalability: Designing systems that can handle growth, like using load balancers to distribute web traffic across multiple servers.

- Database Design: Structuring a database correctly, whether it's SQL or NoSQL. For example, designing a schema for a user database that optimizes query performance and data integrity.