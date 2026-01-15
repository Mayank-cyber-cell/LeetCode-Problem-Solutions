class Solution {
public:
    int maximizeSquareHoleArea(int n, int m, vector<int>& hBars, vector<int>& vBars) {
        // Lambda function to find the maximum consecutive sequence length in bars
        // Returns the maximum gap size (consecutive bars + 1)
        auto findMaxConsecutiveGap = [](vector<int>& bars) {
            int maxGap = 1;        // Maximum gap found so far
            int currentGap = 1;    // Current consecutive sequence length
          
            // Sort bars to check consecutive elements
            sort(bars.begin(), bars.end());
          
            // Iterate through sorted bars to find consecutive sequences
            for (int i = 1; i < bars.size(); ++i) {
                // Check if current bar is consecutive to previous bar
                if (bars[i] == bars[i - 1] + 1) {
                    // Extend current consecutive sequence
                    currentGap++;
                    maxGap = max(maxGap, currentGap);
                } else {
                    // Reset counter for new sequence
                    currentGap = 1;
                }
            }
          
            // Return gap size (number of spaces between bars)
            return maxGap + 1;
        };
      
        // Find maximum gaps in both horizontal and vertical directions
        int maxHorizontalGap = findMaxConsecutiveGap(hBars);
        int maxVerticalGap = findMaxConsecutiveGap(vBars);
      
        // The maximum square hole is limited by the smaller dimension
        int maxSquareSide = min(maxHorizontalGap, maxVerticalGap);
      
        // Return the area of the maximum square hole
        return maxSquareSide * maxSquareSide;
    }
};
