- [[algo tricks]]
    - storing value and counts in an array, assuming all values are an existing index in the array (0 <= arr[i] <= len(arr)-1):
        - ```python
N = len(arr)
for val in arr:
  arr[val % N] += N```
        - note: because we are updating the array values in place, we must %N to get the original number
        - because we are adding fixed N to each index, the value at that index //N will give us the count of the times it was found
        - ref [[41 - First Missing Positive]]
	- Always thinks from both sides of the array/string/any DS [[32 - Longest Valid Parantheses]]