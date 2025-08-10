# Intro to Trees
## Tree Concepts
### Trees in the World
* Real trees:
  * Have single trunk
  * Branches
    * Branches can have branches
    * *ad nauseum*
  * Each branch can end in a leaf
* Book
  * Has chapters (can have subchapters)
  * Chapter has paragraphs
  * Paragraphs have sentences
  * Sentence consists of words
  * Words consist of letters

### Trees in CS
* Trees are data structures
* Trees are composed of nodes and edges (sometimes called arcs)
  * Nodes store data
  * Edges connect nodes
  * Always n-1 edges, where n = # of nodes
* All nodes in a tree must be connected
  * A tree *cannot* have a loop (this is a graph)
  * Each node can have one and only one upward edge to a parent node
* Trees are
  * Structurally recursive
  * Nonlinear (because they branch)

### Tree Terminology
* Root
  * Base or originating node (usually drawn at the top)
* Parent
  * A node connected by an edge *toward the root*, can be immediate/direct or indirect
* Child
  * Node connected by an edge *away from root*, can be immediate/direct or indirect
* Leaf
  * Node with no children (doesn't branch)
* N-ary tree
  * Tree where each node can have between 0 and N direct child nodes
* Subtree (or sub-tree)
  * A given node & all of its children


## Binary Trees & BSTs
### Binary Tree
* A tree with *at most* 2 child nodes per node
* Each node can have 0, 1, or 2 child nodes
* The order of "left" vs. "right" child is usually important
* The order & its importance depends on application

### Binary Trees for Arithmetic Expression
* Almost all arithmetic operations have 3 components
  * Left operand
  * Operator
  * Right operand
  * Order is critical
* Each operand can be a value or an operation
  * Value or variable: 2 + y
  * Operation: (2+y) * (x+3)
* We can represent this as a binary tree
  * Root will be the last operator
  * Each node will either be an operator or value

### Binary Search Tree (BST)
* BST is a binary tree with the following features
  * For each node x, all values in the left subtree are <= to the value in x
  * For each node x, all values in the right subtree are >= to the value in x
* Also called a sorted or ordered tree
* Any given BST can be drawn in multiple ways

### BST Balance
* Unbalanced trees don't provide optimal search
  * Worst case tree has a height of N, where N is the # of values
  * First value as topmost node, last value as bottommost node
* Balanced BST
  * Provides fast operations
* Defining Balance
  * For all subtrees, the difference in height between left & right subtrees <= 1
  * Recursive definition
* Balancing Trees is a complex problem

### BST Advantages
* Balanced BST provides fast operations:
  * Insertion (adding new node)
  * Deletion (removing node)
  * Search (finding node based on value)
* Easy to get the order of values stored in the tree
  * Inorder traversal provides sorted order
* All searches are binary
  * What is big O For binary search?

### Recursive Inorder Traversal Algorithm
1. If we have left subtree
   * Call inorder function, passing the left subtree
2. Print current node
3. If we have right subtree
   * Call inorder function, passing right subtree

### Other Traversal Algorithms
* Preorder
  * Self, left, right
* Postorder
  * Left, Right, Self
* Breadth-First
  * Go across (horizontally)
* Depth-First
  * Go all the way down the left
  * Then come up and visit each right node


### What should you be able to do?
* Explain basic structure of a tree
* Describe use of trees
* Describe & implement simple tree traversal operations
* Understand the relationship between trees & linked lists




