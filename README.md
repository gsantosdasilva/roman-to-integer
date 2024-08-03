# Complexity
- Details

https://leetcode.com/problems/roman-to-integer/submissions/1343407428/

# Code
```
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int romanToInt(String s) {
        // map pra armazenar cada valor
        Map<Character, Integer> map = new HashMap<>();
        map.put('I', 1);
        map.put('V', 5);
        map.put('X', 10);
        map.put('L', 50);
        map.put('C', 100);
        map.put('D', 500);
        map.put('M', 1000);
        
        int total = 0; 
        int prevValue = 0;
        
        for (int i = 0; i < s.length(); i++) {
            char currentChar = s.charAt(i);
            int currentValue = map.get(currentChar);
            
            if (currentValue > prevValue) {
                total += currentValue - 2 * prevValue;
            } else {
                total += currentValue;
            }
            
            // atualiza o valor do símbolo anterior
            prevValue = currentValue;
        }
        
        return total;
    }
}

```