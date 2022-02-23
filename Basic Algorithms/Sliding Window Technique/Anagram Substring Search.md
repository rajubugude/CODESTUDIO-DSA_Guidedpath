### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376583?leftPanelTab=0)

```
def findAnagramsIndices(n, m, s, p):
    ans = []
    pd = [0]*26 #visited for p substring
    sd = [0]*26
    for k in range(m):
        n1 = ord(p[k])-65 
        pd[n1] += 1
        n2 = ord(s[k])-65
        sd[n2] += 1
 
    if pd == sd:
        ans.append(0)
        
    for i in range(m,n):
        number1 = ord(s[i])-65 
        sd[number1] += 1
        number2 = ord(s[i-m])-65
        sd[number2] -= 1
        if pd == sd:
            ans.append(i+1-m)
            
    return ans
```
