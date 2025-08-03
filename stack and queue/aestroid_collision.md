# Question
We are given an array asteroids of integers representing asteroids in a row. The indices of the asteriod in the array represent their relative position in space.

For each asteroid, the absolute value represents its size, and the sign represents its direction (positive meaning right, negative meaning left). Each asteroid moves at the same speed.

Find out the state of the asteroids after all collisions. If two asteroids meet, the smaller one will explode. If both are the same size, both will explode. Two asteroids moving in the same direction will never meet.

##### Example:
Input: asteroids = [5,10,-5]
Output: [5,10]
Explanation: The 10 and -5 collide resulting in 10. The 5 and 10 never collide.

# Optimal Solution
``` python
    def asteroidCollision(self, asteroids):
        """
        :type asteroids: List[int]
        :rtype: List[int]
        """
        n=len(asteroids)
        st=[]
        for i in range(n):
            if asteroids[i]>0:
                st.append(asteroids[i])
            else:
                while(st and st[-1]>0 and st[-1]<abs(asteroids[i])):
                    st.pop() 
                if st and st[-1]==abs(asteroids[i]):
                    st.pop()
                elif not st or st[-1]<0:
                    st.append(asteroids[i])
        return st
            
```
### Time Complexity:O(n)
### Space Complexity: O(n)
