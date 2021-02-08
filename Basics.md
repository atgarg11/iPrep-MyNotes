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
[LC-199](https://leetcode.com/problems/binary-tree-right-side-view/)

# Graphs
## DFS 
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
