### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376559)
#### Same as ([Longest Sub-string With K Distinct Characters]()) in strings> mixed> 1st problem with a little variation
```
def shortestSubstring(s):
    n = len(s)
    startIndex, minLength = 0, n

    hashSet = set()
    for x in s:
        hashSet.add(x)
    k = len(hashSet)

    count = 0  # Variable to count the current distinct elements in 's'.
    '''
        Variable to store starting index of the substring
	    with minimum length and having all distinct 
	    characters of 's' at least once.
    '''
    start = 0
    frequency = dict()
    for i in range(n):
        if s[i] in frequency:
            frequency[s[i]] += 1
        else:
            frequency[s[i]] = 1
        if frequency[s[i]] == 1: # New character inserted
            count += 1
        while count == k:
            if i - start + 1 < minLength:
                startIndex = start
                minLength = i - start + 1
            frequency[s[start]] -= 1
            if frequency[s[start]] == 0: # Character is not present in the window after this
                count -= 1
            start += 1
    return s[startIndex: startIndex + minLength]

```
