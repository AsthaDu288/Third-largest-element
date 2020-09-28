# Third-largest-element
#In a non-empty array of integers, return the third maximum number in this array. If it does not exist, return the maximum number. The time complexity must be in O(n).
class Solution {
    public int thirdMax(int[] a) {
        Integer max = null;
        Integer secondMax = null;
        Integer thirdMax = null;        
        max = a[0]; // assuming 1st element as max
        for(int i = 1; i < a.length; i++ ){
            
            if(a[i] > max){ // new max is found
                
                thirdMax = secondMax;
                secondMax = max;
                max = a[i];
                
            } else if(max > a [i] && (secondMax == null || secondMax < a[i])){ // new secondMax
                thirdMax = secondMax;
                secondMax = a[i];
            } else if(secondMax != null && secondMax > a [i] && (thirdMax == null || thirdMax < a[i])){ // new thirdMax
                thirdMax = a[i];
            }
        }
        
        if(thirdMax == null){ // if third max is not found, return max
            return max;
        } else {
            return thirdMax;
        }
    }
}
