Bit: binary digit
Byte: 8 bits (256 possible values)
Basis of storage is a byte

Encoding: Translating bytes to other characters
Octal, Hexadecimal, Base64, unicode, utf-8, etc.
2⁸ = 16² = 256
Hex: IP address, hexspeak for errors
Hex used for color codes because 256 values.
RGB is additive model (add colors), 3 bytes per color
Red-Yellow-Blue is subtractive, used in printing

Abstract Data Type- concept for storing data; the rules are what matter

Data Structure- A way of organizing data in memory

Sliding Window:
    -Construct for efficient array analysis
    -Start/end indices represent a sub-portion of data and are incremented separately

Set:
	-
	-Key Methods: add, includes, delete

Map:
	-
	-Key Methods: set, get, delete

Stack: "Last in, first out"
	-Data type where data entries can only be added and removed individually from one end
	-Key Methods: push, pop
	Example: function calls in other functions, including recursive calls
	Stacks - Simon says color game, backspace, language call stack
    Stack Frame - a function's slice of stack
    Stack (LIFO) - call stack, browsing history

Queue: "First in, first out"
	-Data type where entries are added in one end and removed on the opposite end
	-Key Methods: enqueue, dequeue
	job scheduling (Rails, DMV, deli)
    JS message queue (function order)
    Stack from queue
    OS queues: multi level priority
    Cyber Monday shopping

Node- An object with data and pointers to other objects with data.
	-They link together to form different data structures.

Trees:
	-Hierarchies of data branching outward. Nodes link to lower-level nodes in a "parent-child" arrangement, where parents can have multiple children but children have only one parent
		Example: file systems
		Root- The top-most node
		Leaves- Nodes without children
		Subtree- A subset of the tree not including the root
		Depth- The length of the longest chain of nodes from the root to a leaf
		Binary Tree- Tree where each node has only two children
		Binary Search Tree- Binary tree where all left nodes are less than the current node and all right nodes are greater than the current node
		Balanced Tree - Tree where the number of nodes on each side of the root is nearly equal and the difference in depth between the deepest left branch and right branch is not greater than one.
	-Key Methods: Parent, value, left & right (binary)

Root, parent, children, siblings, leaves
Childless nodes are leaves, others are internal
There are x-1 for x nodes
A tree is a recursive structure
Depth- number of edges a node is away from root
Height- number of edges from a node to its most distant leaf
Balanced trees are better for searching and insertion
Applications: OOP inheritance, folders
Binary trees useful for search and insertion
Tree - Node - root - left and right
Insertion: start at root, compare value, branch or insert
Binary search = divide and conquer
4 binary trees
Works because entries are ordered
In databases! B or t tree, indexing

	Traversal Methods:
		1. Depth-First-Search (moving down left-most branch first)
			-Recursive and iterative approaches
			-Iteration uses a stack
			-Recursion recursively checks all the children of each node (left first, then right)
		2. Breadth-First-Search (moving left to right, reading nodes the same distance from the root)
			-Iterative approach (a queue)
			-Add a node's children into the queue; eventually you will have all the nodes

Linked List:
	-Nodes organized like a chain, where nodes have pointers to other nodes (one-to-one)
		-AKA unary tree
	-Key Methods: next, value, previous (for doulby-linked lists)
	-Runtime: Insert/Eject (1), Read (n)

Hashmap: Runtime: Insert/Eject (n), Read (1)

LRU Cache: A combination of a hashmap and linked list, inheriting the best performance of both
Tracks links in the hashmap

Array:
	-Indices are not stable
Ring Buffer- Arrays employ these for greater efficiency when adding in values

Graph:
	-Nodes interconnected in a many-to-many relationship

Recursion:
	-Function that calls itself
		Base Case- The end result of recursion; a return value
		Inductive Step- Step in which recursion occurs
		Memoization- recording values of recursive calls during execution
			-Key to reducing runtime of many recursive functions (e.g. fibonacci sums)
	-Recursive methods can be written iteratively
	Strategy:
		1. Identify how to reduce the problem to its base case(s)
			-The base case is the most trivial case
		2. Think of how to get the next case after the base case
			-Make sure the return values are of the same type
			-Compare and contrast successive solutions to identify the inductive step
		3. Get a stack trace going for analysis

Binary Search: Find an element or its position in a list in
	O(logN)
	-Applies only to sorted lists; otherwise bifurcation provides no guarantee of finding element
	Base Case: Default to null value, find the element or run out of elements to check (1 or less)
	Inductive Step:
		1. Start at the list's midpoint
		2. Check against the midpoint value:
			a. For midpoints smaller than the target, look list values left of the midpoint
			b. For midpoints larger than the target, look right.
				-Track the index by adding the mid-point's index value
		3. Finally, if you find the element return its position. If not, return null

Merge Sort: Sort a list (describe more specifically here)
	Nlog(N)
	Base Case: return the array when one or fewer elements remain to sort
	Inductive Step:
		1. Split the array into halves
		2. Perform merge-sorting on each half
			1. Create two new arrays to add the array's contents to
			2. Append elements into each array based on some pivot value
			3. Concatenate the left and right arrays
		4. Finally, merge the sorted arrays

Quick Sort: Sort a list in the fastest(?) time possible
	Nlog(N)
	Base Case: return the array when one or fewer elements remain to sort
	Inductive Step:
		1. Select an element to be a pivot
		2. Divide up elements into those smaller than the pivot and those larger than the pivot
		3. Call quicksort on each list of elements
		4. Finally, concatenate left elements, the pivot, and right elements together

Traveling Salesman: O(N!)

Amortization- A technique to optimize average-case insertions into a data structure. Increasing a contiguous structure proportionaly amount creates occasional slowdowns but most insertions will be constant-time.

Base Case: function is done; no recursive calls
Recursive Case: function calls itself
Call Stack: memory stack used by computers to store variable data in different functions
Comes into play whenever function called in another function
Variables in each function call are inaccessible to other functions in stack

Graphs: Nodes connecting to whatever
Not always a starting point! Nonlinear, not always directional
Directed Graph: edges with direction
Major rules: at least one node
Singleton: graph with one node
G = (V, E), a set of vertices and set of edges
V = node, E = (node1, node2)
Edge- connection between nodes
Parentheses around edge pairs = ordered
Facebook: undirected, Twitter: directed
Path: origin node + edges to destination node
Cycle: path where starting point is ending point
Eulerian Cycle: cycle with no repeats except start
Simple Path: don't repeat edges or nodes already traversed.
Degrees- Number of a node's connections to other nodes

Memory: "drawers" with addresses (e.g. fe0ffeeb)
Array: contiguous storage
Because elements must be contiguous, adding new elements is challenging
if memory slot taken up whole array must be moved to wherever it can fit
Workaround: reserve more space (may waste memory or have to move anyway)
Strength: instant lookup, random access
Reading = O(1), Insertion = O(N), Deletion = O(N)
Linked List: items go anywhere
Strength: more manageable storage and additions
items store addresses to next item to connect
+ No need to move items!
Weakness: lookup (must start at #1 every time), sequential access
Reading = O(N), Insertion = O(1), Deletion = O(1)
Use a linked list if inserts matter more than lookup
Use an array for random access

Selection sort:
1. select the first item best meeting the criteria (O(N))
2. select the next item; do this repeatedly until none are left.
This process takes O(N^2) time