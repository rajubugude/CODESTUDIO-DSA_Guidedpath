### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376576?leftPanelTab=0)
```
def switchingSubarray(arr, n):
	if n <= 2:
		return n
	else :
		ans = 2;
		tmp_ans = 2;
		for i in range(2 , n):
			if arr[i]==arr[i-2]:
				tmp_ans = tmp_ans + 1
			else :
				tmp_ans = 2
			ans = max(ans , tmp_ans)
		return ans
```    
