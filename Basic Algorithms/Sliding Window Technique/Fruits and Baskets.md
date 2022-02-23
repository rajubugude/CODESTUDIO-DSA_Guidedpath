### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376582?leftPanelTab=0)

#### HINT : LONGEST SUBSTRING WITH 2 DISTINCT CHARACTERS

```
from collections import defaultdict
def findMaxFruits(fruits, n):
    baskets = defaultdict(int)
    start = 0
    maxFruit = 0
    for index in range(n):
        baskets[fruits[index]] += 1
        while len(baskets) > 2:
            baskets[fruits[start]] -= 1
            if baskets[fruits[start]] == 0:
                del baskets[fruits[start]]
            start += 1
        maxFruit = max(maxFruit, index - start+1)
    return maxFruit
```
