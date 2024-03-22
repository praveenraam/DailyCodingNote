### Print all the Alphabets

```Java
class Solution{
	public static void main(String[] args){
		String aTOz = "";
		for(int i=0;i<26;i++){
			char ch = 'a' + i;
			aTOz = aTOz + " " + ch; // add alphabets to a string
			System.out.println(ch); // Print all the alphabets
		}
		System.out.println(aTOz);
	}
}
```

- In this case , it creates new object every time we try to change the value of the string
- So , once all the loop were done , 26 objects will be created which will affect the Space complexity
- This is how the pool looks![[Pasted image 20240113162752.png]]
 **Optimized Solution :**
 ![[Strings#Better Solution]]
```Java
class Solutions{
	public static void main(String[] args){
		StringBuilder aTOz = new StringBuilder();
		for(int i=0;i<26;i++){
			char ch = 'a'+i;
			System.out.println(ch);
			aTOz.append(ch);
		}
		System.out.println(aTOz);
	}
}
```

### String Palindrome 
- Create two variable From Start and From End variable and check whether they are equal , if not return false 
```Java
public static boolean isStringPalindrome(String Input){  
    String DupInput = Input;  
    int FromLast = Input.length() - 1;  
    for(int i=0;i<Input.length()/2;i++){  // Only need to check half the string
        if(DupInput.charAt(i) != Input.charAt(FromLast)) return false;  
        FromLast--;  
    }  
    return true;  
}
```


### [1108. Defanging an IP Address](https://leetcode.com/problems/defanging-an-ip-address/)

```Java
class Solution {
    public String defangIPaddr(String address) {
        StringBuilder Ans = new StringBuilder();
        for(int i=0;i<address.length();i++){
            if(address.charAt(i) =='.' ){
                Ans.append("[.]");
            }else {
                Ans.append(address.charAt(i));
            }
        }
        return Ans.toString();
    }
}
```

###  [1528. Shuffle String](https://leetcode.com/problems/shuffle-string/)

```Java
class Solution {
    public String restoreString(String s, int[] indices) {
        char[] Result = new char[indices.length];
        for(int i=0;i<indices.length;i++){
            Result[indices[i]] = s.charAt(i);
        }
        return new String(Result);
    }
}
```


### [1678. Goal Parser Interpretation](https://leetcode.com/problems/goal-parser-interpretation/)

```Java
class Solution {
    public String interpret(String command) {
        StringBuilder Result = new StringBuilder();
        for(int i=0;i<command.length();i++){
            if(command.charAt(i) == '('){
                if(command.charAt(i+1) == 'a'){
                    Result.append('a');
                    Result.append('l');
                    i+=3;
                }else{
                    Result.append('o');
                    i++;
                }
            }
            else Result.append(command.charAt(i));
        }
        return Result.toString();
    }
}
```

### [1859. Sorting the Sentence](https://leetcode.com/problems/sorting-the-sentence/)
```Java
class Solution {
    public String sortSentence(String s) {
        String[] words = s.split(" "), ans = new String[words.length];
        for (String word : words) {
            int i = word.length() - 1;
            ans[word.charAt(i) - '1'] = word.substring(0, i);
        }
        return String.join(" ", ans);
    }
}
```

### [28. Find the Index of the First Occurrence in a String](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/)
```Java
public int strStr(String haystack, String needle) {
  for (int i = 0; ; i++) {
    for (int j = 0; ; j++) {
      if (j == needle.length()) return i;
      if (i + j == haystack.length()) return -1;
      if (needle.charAt(j) != haystack.charAt(i + j)) break;
    }
  }
}
```

### [709. To Lower Case](https://leetcode.com/problems/to-lower-case/)
```Java
class Solution {
    public String toLowerCase(String s) {
        char[] a = s.toCharArray();
        for(int i=0;i<a.length;i++){
            if(a[i] >= 'A' && a[i] <= 'Z'){
                a[i] = (char) (a[i] + 32);
            }
        }
        return new String(a);
    }
}
```

### [2942. Find Words Containing Character](https://leetcode.com/problems/find-words-containing-character/)
```Java
class Solution {
    public List<Integer> findWordsContaining(String[] words, char x) {
       ArrayList<Integer> Result = new ArrayList<>();
       for(int i=0;i<words.length;i++){
           for(int j=0;j<words[i].length();j++){
               if(words[i].charAt(j) == x){
                   Result.add(i);
                   break;
               }
           }
       }
       return Result;
    }
}
```

### [Remove Outermost Parentheses](https://leetcode.com/problems/remove-outermost-parentheses/)
```Java
class Solution {
    public String removeOuterParentheses(String s) {
        int counter = 0;
        int pCounter = 0;
        String Ans = "";
        for(int i=0;i<s.length();i++){
            if(s.charAt(i) == '(') {
             counter++;
            }
            if(s.charAt(i) == ')') {
                counter--;
            }
            if(counter >= 1){
                if(counter >= pCounter && counter!= 1){
                    Ans+="(";
                }else if(counter <= pCounter && counter !=1){
                    Ans+=")";
                }if(pCounter == 2 && counter == 1){
                    Ans+=")";
                }
            }if(counter == 0){
                counter = 0;
            }
            pCounter = counter;
        }
        return Ans;
    }
}
```

### [Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/)
```Java
class Solution {
    public String reverseWords(String s) {
        String res ="";
        int left = -1;
        int right = s.length()-1;
        boolean flag = false;
        for(int i=s.length()-1;i>=0;i--){
            if(s.charAt(i) != ' ') {
                if(!flag)
                    right = i;
                flag = true;
            }
            if((s.charAt(i) == ' ' && flag) || i == 0){
                left = i+1;
                if(i == 0) left = i;
                boolean flag2 = false;
                while(left<=right){
                    if(s.charAt(left) == ' ') {
                        left++; continue;
                    }
                    res+=s.charAt(left);
                    left++;
                    flag2 = true;
                }
                if(flag2) res+=' ';
                flag2 = false;
                right = i-1;
                left = -1;
            }
        }
        return res.trim();
    }
}
```

###  [Largest Odd Number in String](https://leetcode.com/problems/largest-odd-number-in-string/)
```Java
class Solution {
    public String largestOddNumber(String num) {
        for(int i=num.length()-1;i>=0;i--){
            int no = num.charAt(i) - 48;
            if(no%2 != 0) return num.substring(0,i+1);
        }
        return "";
    }
}
```

### [Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)
```Java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String Ans = "";
        String Temp = strs[0];
        for (int i = 0; i < strs.length; i++) {
            String value = strs[i];
            String tempAns = "";
            for (int j = 0; j < value.length(); j++) {
                if (j < Temp.length() && Temp.charAt(j) != value.charAt(j)) break;
                else if(j < Temp.length()){
                    tempAns += Temp.charAt(j);
                }else{
                    break;
                }
            }
            Temp = tempAns;
            Ans = Temp;
        }
        return Ans;
    }
}
```

### [Check If One String Is A Rotation Of Another String](https://www.codingninjas.com/studio/problems/check-if-one-string-is-a-rotation-of-another-string_1115683?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)
```Java
public class Solution {
    public static int isCyclicRotation(String p, String q)  {
        int start = -1;
        for(int i=0;i<p.length();i++){
            if(p.charAt(i) == q.charAt(0)){
                start = i;
                String res = (p.substring(start)+p.substring(0,start));
                if(res.equals(q)) return 1;
            }
        }
        return 0;
    }
}
```

### [Isomorphic Strings](https://www.codingninjas.com/studio/problems/isomorphic-strings-_1117636?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
```Java
import java.util.*;
public class Solution {
    public static boolean areIsomorphic(String str1, String str2) {
        HashMap <Character,Character> Mapper = new HashMap<>();
        if(str1.length() != str2.length() ) return false;
        for(int i=0;i<str1.length();i++){
            if( Mapper.get(str1.charAt(i)) == null ) Mapper.put(str1.charAt(i),str2.charAt(i));
            if( Mapper.get(str1.charAt(i)) != str2.charAt(i)) return false;
        }
        Mapper.clear();
        for(int i=0;i<str2.length();i++){
            if(Mapper.get(str2.charAt(i)) == null ) Mapper.put(str2.charAt(i),str1.charAt(i));
            if(Mapper.get(str2.charAt(i)) != str1.charAt(i)) return false;
        }
        return true;
    }
}
```
### [Valid Anagram](https://leetcode.com/problems/valid-anagram/)
```Java
class Solution {
    public boolean isAnagram(String s, String t) {
        if(s.length() != t.length()) return false;
        int[] arr = new int[26];
        for(int i=0;i<s.length();i++){
            int ch = s.charAt(i)-97;
            arr[ch] = arr[ch] + 1;
        }
        for(int i=0;i<t.length();i++){
            int ch = t.charAt(i)-97;
            arr[ch] = arr[ch] - 1;
            if(arr[ch] < 0) return false;
        }
        return true;
    }
}
```

