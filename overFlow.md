#OverFlows
## Do Subtractions and divisions first to handle OverFlows
```
class Solution {
public:
    bool isDigit(char c) {
        if ( c >='0' && c <= '9') return true;
        return false;
    }
    
    int myAtoi(string str) {
        int res = 0;
        int sign = 1, first = 0;
        double tmp;
        for ( auto c: str) {
            if ( first == 0) {
                if ( c == ' ') ;
                else if ( c == '-' || c == '+') { 
                    sign = c=='+' ? 1 : -1; // 1 means -ve
                    first = 1;
                } else if (isDigit(c)){
                    res = c-'0';
                    first = 1;
                } else {
                    return 0;
                }
            } else {
                // only digit is expected
                if ( !isDigit(c)) {
                    return sign*res;
                } else {
                    tmp = double(res)*10+c-'0';
                    if ( sign == 1 && tmp >= INT_MAX) {
                         return INT_MAX;
                    } else if ( sign == -1 && (sign*tmp) <= INT_MIN) {
                        return INT_MIN;
                    }
                    res = res*10-'0'+c; // Subtraction first follwed by addition
                }
            }
        }
        return sign*res;
    }
};
```