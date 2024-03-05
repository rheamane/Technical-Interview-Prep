### Description:
You have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in **adjacent** plots.

Given an integer array `flowerbed` containing `0`'s and `1`'s, where `0` means empty and `1` means not empty, and an integer `n`, return `true` _if_ `n` _new flowers can be planted in the_ `flowerbed` _without violating the no-adjacent-flowers rule and_ `false` _otherwise_.

### Test Cases:
**Example 1:**

**Input:** flowerbed = [1,0,0,0,1], n = 1
**Output:** true

**Example 2:**

**Input:** flowerbed = [1,0,0,0,1], n = 2
**Output:** false

### Solution:
```python
class Solution:

    def canPlaceFlowers(self, flowerbed: List[int], n: int) -> bool:

        findZeros = 0

        m = len(flowerbed)

        openList = []

        if(m > 1):

  

            # First spot

            if(flowerbed[0] == 0 and flowerbed[1] == 0):

                findZeros+=1

                flowerbed[0]=1

                openList.append(0)

            # Middle Spots

            for i in range (1, m-1):

                if(flowerbed[i]==0 and flowerbed[i-1]==0 and flowerbed[i+1]==0):

                    findZeros+=1

                    flowerbed[i] = 1

                    openList.append(i)

  

            # Last Spot

            if(flowerbed[m-1] == 0 and flowerbed[m-2] == 0):

                findZeros+=1

                flowerbed[m-1] = 1

                openList.append(m-1)

        else:

            if(flowerbed[0] == 0):

                findZeros+=1

                flowerbed[0]=1

                openList.append(0)

  

        print("Open: ", openList)

        print("Available: ", findZeros)

        # Check

        if(findZeros >= n):

            return True;

        return False;
```

![[Pasted image 20240114180311.png]]