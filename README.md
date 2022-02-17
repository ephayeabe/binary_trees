# 0x1D. C - Binary trees
## Learning Objectives
### What students should learn 
- What is a binary tree
- What is the difference between a binary tree and a Binary Search Tree
- What is the possible gain in terms of time complexity compared to linked lists
- What are the depth, the height, the size of a binary tree
- What are the different traversal methods to go through a binary tree
- What is a complete, a full, a perfect, a balanced binary tree
###  Project Requirements
#### Requirements for Python scripts
- Allowed editors: vi, vim, emacs
- All your files will be compiled on Ubuntu 14.04 LTS
- Your programs and functions will be compiled with gcc 4.8.4 using the flags -Wall -Werror -Wextra and -pedantic
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
- You are not allowed to use global variables
- No more than 5 functions per file
- You are allowed to use the standard library
- In the following examples, the main.c files are showed as examples. You can use them to test your functions, but you don?t have to push them to your repo (if you do we won?t take them into account). We will use our own main.c files at compilation. Our main.c files might be different from the one showed in the examples
- The prototypes of all your functions should be included in your header file called binary_trees.h
- Don?t forget to push your header file
- All your header files should be include guarded
### Data Structures
```C
/**
 * struct binary_tree_s - Binary tree node
 *
 * @n: Integer stored in the node
 * @parent: Pointer to the parent node
 * @left: Pointer to the left child node
 * @right: Pointer to the right child node
 */
struct binary_tree_s
{
    int n;
    struct binary_tree_s *parent;
    struct binary_tree_s *left;
    struct binary_tree_s *right;
};

typedef struct binary_tree_s binary_tree_t;
```
```C
Binary Search Tree

typedef struct binary_tree_s bst_t;


AVL Tree

typedef struct binary_tree_s avl_t;

Max Binary Heap

typedef struct binary_tree_s heap_t;
```

### TASKS
#### 0. New node
##### Write a function that creates a binary tree node
- Prototype: binary_tree_t *binary_tree_node(binary_tree_t *parent, int value);
- Where parent is a pointer to the parent node of the node to create
- And value is the value to put in the new node
- When created, a node does not have any child
- Your function must return a pointer to the new node, or NULL on failure

#### 1. Insert left
##### Write a function that inserts a node as the left-child of another node
- Prototype: binary_tree_t *binary_tree_insert_left(binary_tree_t *parent, int value);
- Where parent is a pointer to the node to insert the left-child in
- And value is the value to store in the new node
- Your function must return a pointer to the created node, or NULL on failure or if parent is NULL
- If parent already has a left-child, the new node must take its place, and the old left-child must be set as the left-child of the new node.

#### 2. Insert right
##### Write a function that inserts a node as the right-child of another node
- Prototype: binary_tree_t *binary_tree_insert_right(binary_tree_t *parent, int value);
- Where parent is a pointer to the node to insert the right-child in
- And value is the value to store in the new node
- Your function must return a pointer to the created node, or NULL on failure or if parent is NULL
- If parent already has a right-child, the new node must take its place, and the old right-child must be set as the right-child of the new node.

#### 3. Delete
##### Write a function that deletes an entire binary tree
- Prototype: void binary_tree_delete(binary_tree_t *tree);
- Where tree is a pointer to the root node of the tree to delete
- If tree is NULL, do nothing

#### 4. Is leaf
##### Write a function that checks if a node is a leaf
- Prototype: int binary_tree_is_leaf(const binary_tree_t *node);
- Where node is a pointer to the node to check
- Your function must return 1 if node is a leaf, otherwise 0
- If node is NULL, return 0

#### 5. Is root
##### Write a function that checks if a given node is a root
- Prototype: int binary_tree_is_root(const binary_tree_t *node);
- Where node is a pointer to the node to check
- Your function must return 1 if node is a root, otherwise 0
- If node is NULL, return 0