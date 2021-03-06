> International Morse Code defines a standard encoding where each letter is mapped to a series of dots and dashes, as follows: "a" maps to ".-", "b" maps to "-...", "c" maps to "-.-.", and so on.

>For convenience, the full table for the 26 letters of the English alphabet is given below:

>[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
>Now, given a list of words, each word can be written as a concatenation of the Morse code of each letter. For example, "cab" >can be written as "-.-.-....-", (which is the concatenation "-.-." + "-..." + ".-"). We'll call such a concatenation, the >transformation of a word.

>Return the number of different transformations among all words we have.

# Example:
Input: words = ["gin", "zen", "gig", "msg"]
Output: 2
Explanation: 
The transformation of each word is:
"gin" -> "--...-."
"zen" -> "--...-."
"gig" -> "--...--."
"msg" -> "--...--."

*There are 2 different transformations, "--...-." and "--...--.".*
 
*Note:
The length of words will be at most 100.
Each words[i] will have length in range [1, 12].
words[i] will only consist of lowercase letters.*

# code
```
class Solution(object):
    def uniqueMorseRepresentations(self, words):
        """
        :type words: List[str]
        :rtype: int
        """
        Letters= list()
        for x in range(97,123):
            Letters.append(chr(x))
        
        Morse=[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
        for i in range(len(words)):
            word=''
            for letter in words[i]:
                for data in zip(Letters,Morse):
                    if letter ==data[0]:
                        word+=data[1]
                words[i]=word
        return len(set(words))
```

# Mark points
1.`zip()`:Returns a list of tuples, where the i-th tuple contains the i-th element from each of the argument sequences or iterables.
2.`set()`: no duplication
