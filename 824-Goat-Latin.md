>A sentence S is given, composed of words separated by spaces. Each word consists of lowercase and uppercase letters only.

>We would like to convert the sentence to "Goat Latin" (a made-up language similar to Pig Latin.)

>The rules of Goat Latin are as follows:

>If a word begins with a vowel (a, e, i, o, or u), append "ma" to the end of the word.
>For example, the word 'apple' becomes 'applema'.
 
>If a word begins with a consonant (i.e. not a vowel), remove the first letter and append it to the end, then add "ma".
>For example, the word "goat" becomes "oatgma".
 
>Add one letter 'a' to the end of each word per its word index in the sentence, starting with 1.
>For example, the first word gets "a" added to the end, the second word gets "aa" added to the end and so on.
>Return the final sentence representing the conversion from S to Goat Latin. 

# Example
Input: "The quick brown fox jumped over the lazy dog"
Output: "heTmaa uickqmaaa rownbmaaaa oxfmaaaaa umpedjmaaaaaa overmaaaaaaa hetmaaaaaaaa azylmaaaaaaaaa ogdmaaaaaaaaaa"

# Code:
```
class Solution:
    def toGoatLatin(self, S):
        """
        :type S: str
        :rtype: str
        """
        s=S.split()
        lst=[]
        count=0
        for j in range(len(s)):
            count+=1
            if s[j][0].lower() in ['a','e','i','o','u']:
                n=s[j]+'ma'+count*'a'
                lst.append(n)
            else:
                n=s[j][1:]+s[j][0]+'ma'+count*'a'
                lst.append(n)
        return ' '.join(lst)
```
