# Main Concept of Stacks

A stack is a one-ended linear data structure which models a real world stack by having two primary operations, namely push and pop. Elements in a stack always gets removed and added to the top of the pile (LIFO). Means at the end of the list is getting changed in either way.
Stacks are often implemented as either Arrays, Singled Linked List oder sometimes as Doubly Linked List

## When and where is a stack used:
- Used by 'undo' mechanisms in text editors
- Used behind the scenes to support recursion by keeping track of the previous function calls
- Can be used to a Depth First Search (DFS) on a graph

## Complexity Analysis:
![ImgName](https://github.com/KarimsHub/Stack_Datastructure/blob/master/stack_time_complexity.png?raw=true)

## Python List vs. collections.deque
- list has the advantage of being familiar. You know how it works and likely have used it in your programs already.
- Unfortunately, list has a few shortcomings compared to other data structures you’ll look at. The biggest issue is that it can run into speed issues as it grows. The items in a list are stored with the goal of providing fast access to random elements in the list. At a high level, this means that the items are stored next to each other in memory.
- If your stack grows bigger than the block of memory that currently holds it, then Python needs to do some memory allocations. This can lead to some .append() calls taking much longer than other ones.

### Advantages and Disadvantages of Python Lists for implementing Stacks
- list has the advantage of being familiar. You know how it works and likely have used it in your programs already.
- Python’s built-in list type makes a decent stack data structure as it supports push and pop operations in amortized O(1) time.
- Python’s lists are implemented as dynamic arrays internally which means they occasionally need to resize the storage space for elements stored in them whenever they are added or removed. The storage space is allocated more than required, so that not every push or pop requires resizing and you get an amortized O(1) time complexity for these operations.
- On the other hand, lists provide fast O(1) time random access to elements on the stack which can be an added benefit.

### Advantages and Disadvantages of collections.deque for implementing Stacks
- The collections module contains deque, which is useful for creating Python stacks. deque stands for “double-ended queue.”
- deque is built upon a doubly linked list. A doubly linked list is just the same, except that each entry has references to both the previous and the next entry in the list. This allows you to easily add nodes to either end of the list.
- This constant-time addition and removal of entries onto a stack comes with a trade-off, however. Getting myDeque[3] is slower than it was for a list, because Python needs to walk through each node of the list to get to the third element (O(n) performance).

### Conclusion
- In general, you should use a deque if you’re not using threading. If you are using threading, then you should use a LifoQueue unless you’ve measured your performance and found that a small boost in speed for pushing and popping will make enough difference to warrant the maintenance risks.
- list may be familiar, but it should be avoided because it can potentially have memory reallocation issues. The interfaces for deque and list are identical, and deque doesn’t have these issues, which makes deque the best choice for your non-threaded Python stack.


