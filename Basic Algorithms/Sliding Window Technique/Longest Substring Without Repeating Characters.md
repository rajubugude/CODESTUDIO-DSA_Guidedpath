### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376581)

[Explantion](https://www.youtube.com/watch?v=RqxIXM6eyiY)
```
def lengthOfLongestSubstring(s):
    i = 0 #end
    j = 0 #start
    ans = 0
    n = len(s)
    st = set()
    while j < n:
        if s[j] not in st:
            st.add(s[j])
            temp = j - i + 1
            if temp >ans:
                ans = temp
            j += 1
        else:
            st.remove(s[i])
            i += 1
    return ans
```
