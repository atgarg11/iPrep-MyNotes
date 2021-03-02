# Binary Trees
## Level order Traversal
### Mehotd - 1.
* Maintain a que 
* iterate on que till que is not empty
* Maintain a count of nodes at a level and iterate for those nodes to complete the level within the out Loop.
```
   queue<TreeNode*> que;
        que.push(root);
        while ( !que.empty()) {
            len = que.size();
            while (len) {
                node = que.front();que.pop();
                len--;
                if ( node->left) {
                    que.push(node->left);
                } 
                if ( node->right) {
                    que.push(node->right);
                }
            }
            res.push_back(node->val);
        }
```
* [LC-199: BT right view](https://leetcode.com/problems/binary-tree-right-side-view/)

## Passing and Returning values from recursive helper function
```
    TreeNode* helper(TreeNode* root, TreeNode* p, TreeNode* suc) {
        if ( p->val == root->val) {
            if (root->right) {
                return tmin(root->right);
            } else {
                return suc;
            }
        } else if ( p->val < root->val) {
            return helper(root->left, p, root);    
        } else {
            return helper(root->right, p, suc);
        }
        return NULL;
    }
```
* [285. Inorder Successor](https://leetcode.com/problems/inorder-successor-in-bst/)
* [98. Validate BST](https://leetcode.com/problems/validate-binary-search-tree/)

## Interesting Problems on Binary Tree
* [99. Recover Binary Tree](https://leetcode.com/problems/recover-binary-search-tree/)
** Find two pairs which don't satisfy the BST property and swap them. 
    if A...B and .C..D are two such pairs swap A and D. ( This intuition is hard to come by)
* [314. Binary Tree Vertical Order Traversal](https://leetcode.com/problems/binary-tree-vertical-order-traversal/)
** In Vertical Order Traversal, we need to maintain two points called coordinates of a node ( row, col)
    Row is determined by the level of node from root. Level order traversal gives you that autmatically
    Col information needs to be stored in the que while storing the node. 

## Some interesting problems
* [669. Trim a Binary Search Tree](https://leetcode.com/problems/trim-a-binary-search-tree/)

# Graphs
## DFS 
### Cycle Detetion
####    Undirected Graphs
* Union Find
```
// UF implementation
    vector<int> parent;
    void init(int n) {
        parent.push_back(0);
        for ( int i = 1; i <= n; i++) {
            parent.push_back(i);
        }
    }
    int find(int v) {
        if ( v != parent[v]) {
            parent[v] = find(parent[v]);
        }
        return parent[v];
    }

    void lunion(int v1, int v2) {
         if ( find(v1) != find(v2)) {
             parent[parent[v2]] = find(v1); // Note parent[parent[]]. This is imp.
         }
    }
```
** [684. Redundant Connection](https://leetcode.com/problems/redundant-connection/)
####    Directed Graphs
* DFS
### grids ( undirected Graphs) 
#### Unique Paths on DFS
```
void dfs(vector<vector<int>>& grid, int x, int y) {
        // Recurssion breaking condition
        grid[x][y] = 0;

        if ( y+1 < cols && grid[x][y+1]) {
            pattern += "R";
            dfs(grid, x,y+1);
        }
        pattern += "0"; // This creates a unique Path 
        if ( y-1 >= 0 && grid[x][y-1]) {
            pattern += "L";
            dfs(grid, x,y-1);
        }
        pattern += "0"; // This creates a unique Path 
        if ( x+1 < rows && grid[x+1][y]) {
            pattern += "D";
            dfs(grid, x+1,y);
        }
        pattern += "0"; // This creates a unique Path 
        if ( x-1 >=0 && grid[x-1][y]) {
            pattern += "U";
            dfs(grid, x-1,y);
        }
        pattern += "0";
    }
```
[LC-694](https://leetcode.com/problems/number-of-distinct-islands/)
## BFS
### Interesting Techniques
* Put more entries in que than just one source.
#### Examples:
* [286. Walls and Gates](https://leetcode.com/problems/walls-and-gates/): Put all the gates in the queuefor BFS.
# Queues and Stacks
### Queue
```
class MyCircularQueue {
private:
    vector<int> data;
    int head;
    int tail;
    int size;
public:
    /** Initialize your data structure here. Set the size of the queue to be k. */
    MyCircularQueue(int k) {
        data.resize(k);
        head = -1;
        tail = -1;
        size = k;
    }

    /** Insert an element into the circular queue. Return true if the operation is successful. */
    bool enQueue(int value) {
        if (isFull()) {
            return false;
        }
        if (isEmpty()) {
            head = 0;
        }
        tail = (tail + 1) % size;
        data[tail] = value;
        return true;
    }

    /** Delete an element from the circular queue. Return true if the operation is successful. */
    bool deQueue() {
        if (isEmpty()) {
            return false;
        }
        if (head == tail) {
            head = -1;
            tail = -1;
            return true;
        }
        head = (head + 1) % size;
        return true;
    }

    /** Get the front item from the queue. */
    int Front() {
        if (isEmpty()) {
            return -1;
        }
        return data[head];
    }

    /** Get the last item from the queue. */
    int Rear() {
        if (isEmpty()) {
            return -1;
        }
        return data[tail];
    }

    /** Checks whether the circular queue is empty or not. */
    bool isEmpty() {
        return head == -1;
    }

    /** Checks whether the circular queue is full or not. */
    bool isFull() {
        return ((tail + 1) % size) == head;
    }
};
```
