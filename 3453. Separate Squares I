class Solution {
public:
    double separateSquares(vector<vector<int>>& squares) {
        long double area = 0, sum = 0, py = 0, now = 0;
        for(auto& s : squares) area += s[2] / 2. * s[2];
        vector<pair<long long, long long>> S;
        unordered_map<long long, long long> mp;
        for(auto& s : squares) {
            mp[s[1]] += s[2];
            mp[s[1] + s[2]] -= s[2];
        }
        for(auto& [k,v] : mp) if(v) S.push_back({k,v});
        sort(begin(S), end(S));
        for(auto& [y, l] : S) {
            long double nxt = now + (y - py) * sum;
            if(nxt >= area) {
                return py + (area - now) / sum;
            }
            sum += l;
            now = nxt;
            py = y;
        }
        return -1;
    }
};
