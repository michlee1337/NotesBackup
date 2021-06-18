- note: just always maintain one of the heaps as the largest one, simplifies things
- 
- sol
    - ```python
class MedianFinder:

    def __init__(self):
        """
        initialize your data structure here.
        """
        self.heaps = [], []  # keep top largest

    def addNum(self, num: int) -> None:
        btm, top = self.heaps
        # heappushpop necessary to add to top
        ## while maintaining two heap sorted property 
        if len(top) == len(btm):
            heappush(top, -heappushpop(btm, -num))
        else:
            heappush(btm, -heappushpop(top, num))            

    def findMedian(self) -> float:
        btm, top = self.heaps
        if len(top) > len(btm):
            return top[0]
        else:
            return (-btm[0] + top[0])/2
```
