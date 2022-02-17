### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376565)

```
def removeConsecutiveDuplicates(s):
    n = len(s)
    ans = ''
    x = s[0]
    ans += x    
    for i in range(1, n):    	    
        if(s[i] == x):
            continue		
        x = s[i]        
        ans += s[i]        
    return ans

```
