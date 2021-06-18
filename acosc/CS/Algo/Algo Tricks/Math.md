[[31 - Next Permutation]]
- next largest iteration is to 
- get the first num from the right that is decreasing (X at index i)
- swap it with the number directly larger that itself (next largest from X in arr[i:]). 
- Then reorder everything from smallest to largest
	- reverse everything in [i+1:] because of step 2 and 3 it is already in inverse order
