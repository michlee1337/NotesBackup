https://leetcode.com/problems/longest-string-chain/

        sort words by length
        
        at each length
        - dp will be all the words of the previous length
        - for each word at this length
                try omitting one character of this word and seeing if it is in dp
                += 1, glob, cur

patterns
- [[optimal substructure]]
- [[DP]] top down better
- 
