# Question
A sentence is a list of words that are separated by a single space with no leading or trailing spaces. Each word consists of lowercase and uppercase English letters.

A sentence can be shuffled by appending the 1-indexed word position to each word then rearranging the words in the sentence.

For example, the sentence "This is a sentence" can be shuffled as "sentence4 a3 is2 This1" or "is2 sentence4 This1 a3".
Given a shuffled sentence s containing no more than 9 words, reconstruct and return the original sentence.

##### Example:
Input: s = "is2 sentence4 This1 a3"
Output: "This is a sentence"
Explanation: Sort the words in s to their original positions "This1 is2 a3 sentence4", then remove the numbers.

# Optimal Solution


``` python
    def sortSentence(self, s):
        """
        :type s: str
        :rtype: str
        """
        ans=['']*10
        cnt=0
        temp=''
        i=0
        while i<len(s):
            if s[i]==' ':
                pos=int(temp[-1])
                temp=temp[:-1]
                ans[pos]=temp
                temp=''
                cnt+=1
            else:
                temp=temp+s[i]
            i=i+1
        if temp:
            pos=int(temp[-1])
            temp=temp[:-1]
            ans[pos]=temp
            temp=' '
            cnt+=1
        res=' '.join([i for i in ans if i])
        return res
            
```
### Time Complexity:O(n)
### Space Complexity: O(1) 
