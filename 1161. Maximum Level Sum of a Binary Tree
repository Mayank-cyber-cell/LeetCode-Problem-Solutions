class Solution {
public:
    int maxLevelSum(TreeNode* root) {
        // Initialize queue for BFS traversal with root node
        queue<TreeNode*> bfsQueue;
        bfsQueue.push(root);
      
        // Track maximum sum found so far
        int maxSum = INT_MIN;
      
        // Track the level with maximum sum
        int levelWithMaxSum = 0;
      
        // Current level number (1-indexed)
        int currentLevel = 0;
      
        // Process tree level by level
        while (!bfsQueue.empty()) {
            currentLevel++;
          
            // Calculate sum for current level
            int currentLevelSum = 0;
            int nodesInCurrentLevel = bfsQueue.size();
          
            // Process all nodes at current level
            for (int i = 0; i < nodesInCurrentLevel; i++) {
                TreeNode* currentNode = bfsQueue.front();
                bfsQueue.pop();
              
                // Add current node's value to level sum
                currentLevelSum += currentNode->val;
              
                // Add children to queue for next level processing
                if (currentNode->left != nullptr) {
                    bfsQueue.push(currentNode->left);
                }
                if (currentNode->right != nullptr) {
                    bfsQueue.push(currentNode->right);
                }
            }
          
            // Update maximum sum and corresponding level if current level has higher sum
            if (currentLevelSum > maxSum) {
                maxSum = currentLevelSum;
                levelWithMaxSum = currentLevel;
            }
        }
      
        return levelWithMaxSum;
    }
};
