![[BTInsert.png]]
#### BT-Insert
- Start at the root. If root is a leaf, set root = new node and return
- Walk down the tree, searching for key k. If a full node is encountered. split it
- If k is found, replace the payload and return
- If you reach the bottom level of internal nodes, then insert into this node and increase keycount
- If it is full, split about the median key and insert the median into its parent.

#### BT-Delete
- Start a the root
- Walk down the tree, searching for key k
- If k is not found, then return
- If it is the only key in the root, replace the root with a leaf node and return
- If k is found but not at the bottom level, swap k with its predecessor
- If the node is not minimum size, remove k from the node and decrease n.keycount
- If the node containing k is minimum size, look at left and right siblings and redistribute into this node. Then delete k and decrease keycount
- If both siblings are minimum size, or dont exist, then merge this node with the sibling and steal the seperator key from the parent. Delete k and decrease keycount
- If the parent is minimum size, and cannot give us a key, recursively redistribute or merge it with its siblings first
- If the root's last key is stolen by its merging children, update the root pointer

### Red-Black Trees
Binary search trees where each node has an additional colour attribute
The colour is used by modified insert and delete algorithms to maintain approximate balance
- Every node is either red or black
- The root is black
- The leaves are black and contain no keys or payloads
- Both children of a red node are black
- For each node, all simple paths to descendant leaves contain the same number of black nodes (the tree is black-height balanced)

Black height is counted as follows:
- Do not count the node you start from
- Do count black nodes below
- Do count black leaves
Minimum black-height occurs when all nodes are black
Maximum black-height occurs when all black nodes have two red children
A red-black tree wit n internal nodes (not counting leaves) has at most $\text{lg}(n+1)$ levels

#### Tree isomorphism
A B-tree with minimum degree T=2 (also known as a 2-3-4 tree) can be mapped to a red-black tree
All leaves are turned black
Internal nodes with 1 key are turned black
A node with 3 keys becomes a red node with 2 black children
A tree rotation is a local restructuring that preserves the global ordering property