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
```Java
import java.util.*;
public class Solution {
    public static boolean isAnagram(String str1, String str2) {
        // to lower case
        str1.toLowerCase(); 
        str2.toLowerCase();
        // converting to array
        char[] s1 = str1.toCharArray();
        char[] s2 = str2.toCharArray();
        // sorting 
        Arrays.sort(s1); 
        Arrays.sort(s2);
        
        return Arrays.equals(s1,s2);
    }
}
```

### [Sort Characters By Frequency](https://leetcode.com/problems/sort-characters-by-frequency/description/)
```Java
class Solution {
    public String frequencySort(String s) {
     Map<Character,Integer> map = new HashMap<>();
     for(int i=0;i<s.length();i++){
        if(map.containsKey(s.charAt(i))){
            map.put(s.charAt(i),map.get(s.charAt(i))+1);
        }
        else{
            map.put(s.charAt(i),1);
        }
     }
     List<Character> chars = new ArrayList<>(map.keySet());
     Collections.sort(chars,(a,b) -> map.get(b) - map.get(a));
     StringBuilder sb = new StringBuilder();
     for(Character cb : chars){
        for(int i=0;i<map.get(cb);i++){
            sb.append(cb);
        }
     }
     return sb.toString();
    }
}
```

### [Sort Characters By Frequency](https://leetcode.com/problems/sort-characters-by-frequency/description/)
```Java
class Solution {
    public String frequencySort(String s) {
     Map<Character,Integer> map = new HashMap<>();
     for(int i=0;i<s.length();i++){
        if(map.containsKey(s.charAt(i))){
            map.put(s.charAt(i),map.get(s.charAt(i))+1);
        }
        else{
            map.put(s.charAt(i),1);
        }
     }
     List<Character> chars = new ArrayList<>(map.keySet());
     Collections.sort(chars,(a,b) -> map.get(b) - map.get(a));
     StringBuilder sb = new StringBuilder();
     for(Character cb : chars){
        for(int i=0;i<map.get(cb);i++){
            sb.append(cb);
        }
     }
     return sb.toString();
    }
}
```

### [Maximum Nesting Depth of the Parentheses](https://leetcode.com/problems/maximum-nesting-depth-of-the-parentheses/)
```Java
class Solution {
    public int maxDepth(String s) {
        int counter = 0;
        int max = 0;
        for(int i=0;i<s.length();i++){
            char ch = s.charAt(i);   
            if(ch == '('){
                counter++;
                if(counter > max) max = counter;
            }else if(ch == ')'){
                counter--;
            }
        }
        return max;
    }
}
```

### [Roman to Integer](https://leetcode.com/problems/roman-to-integer/description/)
```Java
class Solution {
    public int romanToInt(String s) {
        int sum = 0;
        Map<Character,Integer> romanValues = new HashMap<>();
        romanValues.put('I',1);
        romanValues.put('V', 5);
        romanValues.put('X', 10);
        romanValues.put('L', 50);
        romanValues.put('C', 100);
        romanValues.put('D', 500);
        romanValues.put('M', 1000);

        for(int i=s.length()-1;i>=0;i--){
            char ch = s.charAt(i);
            if(i < s.length()-1 && romanValues.get(ch) < romanValues.get(s.charAt(i+1))){
                sum-=romanValues.get(ch);
            }else{
                sum+=romanValues.get(ch);
            }
        }
        return sum;
    }
}
```

### [58. Length of Last Word](https://leetcode.com/problems/length-of-last-word/)

```Java
class Solution {
    public int lengthOfLastWord(String s) {
        int counter = 0;
        boolean flag = false;
        for(int i=s.length()-1;i>=0;i--){
            if(s.charAt(i) != ' '){
                counter++;
                flag = true;
            } 
            else if(flag && s.charAt(i) == ' '){
                break;
            }
        }   
        return counter;
    }
}
```

### [392. Is Subsequence](https://leetcode.com/problems/is-subsequence/)

```Java
class Solution {
    public boolean isSubsequence(String s, String t) {
        if(s.length() == 0) return true;
        int p1=0,p2=0;
        int sc = 0;
        int sSize = s.length();
        while(p1<s.length() && p2<t.length()){
            if(s.charAt(p1) == t.charAt(p2)){
                p1++;
                p2++;
                sc++;
            }else p2++;
            if(sSize == sc) return true;
        }
        return false;
    }
}
```

### [929. Unique Email Addresses](https://leetcode.com/problems/unique-email-addresses/)

```Java
class Solution {
    public int numUniqueEmails(String[] emails) {
        Set<String> set = new HashSet<>();
        for(int i=0;i<emails.length;i++){
            String s = emails[i];
            StringBuilder sb = new StringBuilder();
            boolean flag = true;
            boolean flag2 = false;
            for(int j=0;j<s.length();j++){
                if(s.charAt(j) == '.' && flag2 ) sb.append('.');
                else if(s.charAt(j) == '.' ) continue;
                else if(s.charAt(j) == '+' && flag2){
                    continue;
                }
                else if(s.charAt(j) == '+') flag = false;
                else if(s.charAt(j) == '@' ) {
                    sb.append(s.charAt(j));
                    flag = true; flag2 = true;
                }else if(flag) sb.append(s.charAt(j));
            }
            set.add(sb.toString());
        }
        return set.size();
    }
}
```

### [205. Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)

```Java
class Solution {
    public boolean isIsomorphic(String s, String t) {
        Map<Character,Character> set = new HashMap<>();
        if(s.length() != t.length()) return false;
        for(int i=0;i<s.length();i++){
            if(set.containsKey(s.charAt(i))) {
                if(set.get(s.charAt(i)) != t.charAt(i)) return false;
            }
            else {
                if(!set.containsValue(t.charAt(i)))
                    set.put(s.charAt(i),t.charAt(i));
                else return false;
            }
        }
        return true;
    }
}
```

### [Maximum Number of Balloons](https://leetcode.com/problems/maximum-number-of-balloons/)

```Java
class Solution {
    public int maxNumberOfBalloons(String text) {
        if(text.length() < 7) return 0;

        int[] ch = new int[26];

        for(int i=0;i<text.length();i++){
            int letter = text.charAt(i) - 97;
            ch[letter] = ch[letter]+1;
        }
        boolean flag = false; String wrd = "balloon"; int counter = 1550;

        for(int i=0;i<wrd.length();i++){
            int letter = wrd.charAt(i) - 97;
            char c = wrd.charAt(i);
            int no = Integer.MAX_VALUE;
            if(c == 'l' || c == 'o'){
                no = ch[letter]/2;
            }else if(c == 'b' || c == 'a' || c == 'n'){
                no = ch[letter];
            }
            counter = Math.min(counter,no);
        }
        return counter;
    }
}
```

```Java
class Solution {
    public int maxNumberOfBalloons(String text) {
        int b=0, a=0, l=0, o=0,n=0;

        for(int i=0;i<text.length();i++){
            char ch = text.charAt(i);

            if(ch == 'b') b++;
            else if(ch == 'a') a++;
            else if(ch == 'l') l++;
            else if(ch == 'o') o++;
            else if(ch == 'n') n++;
        }

        l = l/2; o = o/2;

        return Math.min(Math.min(a,b),Math.min(l,Math.min(o,n)));

    }
}
```
### [Word Pattern](https://leetcode.com/problems/word-pattern/description/)

```Java
class Solution {
    public boolean wordPattern(String pattern, String s) {
        Map<Character,String> mp = new HashMap<>();
        boolean space = true;
        int pointer = 0;
        
        for(int i=0;i<pattern.length() && pointer<s.length();i++){
            char ch = pattern.charAt(i);
            StringBuilder sb = new StringBuilder();

            while(space && pointer<s.length()){
               if(s.charAt(pointer) != ' ') sb.append(s.charAt(pointer));
               else space = false;
               pointer++;
            }

            space = true;
            
            if(mp.containsKey(ch)){
                if(mp.get(ch).equals(sb.toString())) continue;
                else return false;
            }else{
                if(mp.containsValue(sb.toString())){
                    return false;
                }
                mp.put(ch,sb.toString());
            }
        }
        for(int i=0;i<pattern.length();i++){
            if(!mp.containsKey(pattern.charAt(i))) return false;
        }

        if(pointer < s.length()) return false;
        return true;
    }
}
```

### [38. Count and Say](https://leetcode.com/problems/count-and-say/)

```Java
class Solution {
    public String countAndSay(int n) {
        StringBuilder cur = new StringBuilder("1");
        StringBuilder prev;
        int counter;
        char no;

        for(int i=1;i<n;i++){
            prev = cur;
            cur = new StringBuilder();
            counter = 1;
            no = prev.charAt(0);

            for(int j=1,len = prev.length();j<len;j++){
                if(prev.charAt(j) != no){
                    cur.append(counter);
                    cur.append(no);
                    counter = 1;
                    no = prev.charAt(j);
                }else{
                    counter++;
                }
            }
            cur.append(counter);
            cur.append(no);
        }
        return cur.toString();
    }
}
```

### [438. Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/description/) 

```Java
class Solution {
    public List<Integer> findAnagrams(String s, String p) {
        
        List<Integer> res = new ArrayList<>();
        if(s.length() < p.length()) return res;

        Map<Character,Integer> pMap = new HashMap<>();

        for(char ch:p.toCharArray()){
            pMap.put(ch,pMap.getOrDefault(ch,0)+1);
        }
        
        int p1 = 0;
        int p2 = p.length()-1;

        while(p2<s.length()){
            Map<Character,Integer> sMap = new HashMap<>();
            for(int i=p1;i<=p2;i++){
                char ch = s.charAt(i);
                sMap.put(ch,sMap.getOrDefault(ch,0)+1);
            }
            if(pMap.equals(sMap)){
                res.add(p1);
            }
            p1++;p2++;
        }

        return res;
    }
}
```

### [28. Find the Index of the First Occurrence in a String](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/)

```Java
class Solution {
    public int strStr(String haystack, String needle) {
        int j=0;

        if(haystack.length() < needle.length()) return -1;

        for(int i=0;i<haystack.length();i++){
            int temp = i;

            while( i<haystack.length() && haystack.charAt(i) == needle.charAt(j) ){
                i++;
                j++;
                if(needle.length() == j) return temp;
            }

            i = temp;
            j = 0;
        
        }

        return -1;
    }
}
```

### [Valid-Palindrome](https://leetcode.com/problems/valid-palindrome)

```Java
class Solution {
    public boolean isPalindrome(String s) {
        int p1=0,p2=s.length()-1;

        if(s.length() == 0) return false;

        s = s.toLowerCase();
        while(p1<p2){

            char ch1 = s.charAt(p1);
            char ch2 = s.charAt(p2);
            
            if((ch1 >= 'a' && ch1 <= 'z' || ch1 >= '0' && ch1 <= '9') && (ch2 >= 'a' && ch2 <= 'z'|| ch2 >= '0' && ch2 <= '9')){
                if( ch1 == ch2 ){
                    p1++; p2--;
                } else return false;
            }
            if(!(ch1 >= 'a' && ch1 <= 'z' || ch1 >= '0' && ch1 <= '9')){
                p1++;
            }if(!(ch2 >= 'a' && ch2 <= 'z'|| ch2 >= '0' && ch2 <= '9')){
                p2--;
            }

        }
        return true;

    }
}
```

### [838. Push Dominoes](https://leetcode.com/problems/push-dominoes/)

```Java
class Solution {
    public String pushDominoes(String dominoes) {

        int p1=0,p2=2;

        if(dominoes.length() == 1 || dominoes.length() == 0) return dominoes; 


        while(true){
            StringBuilder sb = new StringBuilder();
            p1=0;p2=2;

            if(dominoes.charAt(0) == '.'){
                if(dominoes.charAt(1) == 'L'){
                    sb.append('L');
                }else sb.append('.');
            }else{
                sb.append(dominoes.charAt(0));
            }

            while(p2<dominoes.length()){
                char c1 = dominoes.charAt(p1);
                char c2 = dominoes.charAt(p2);

                if(dominoes.charAt(p1+1) == '.'){
                    if((c1 == '.' && c2 == '.')  || (c1 == '.' && c2 == 'R') || (c1 == 'L' && c2 == '.') || (c1 == 'R' && c2 == 'L') || (c1 == 'L' && c2 == 'R')){
                        sb.append(dominoes.charAt(p1+1));
                    }else if(c1 == 'R'){
                        sb.append('R');
                    }else if(c2 == 'L'){
                        sb.append('L');
                    }
                }else sb.append(dominoes.charAt(p1+1));
                p1++;p2++;
            }

            if(dominoes.charAt(dominoes.length()-1) == '.'){
                if(dominoes.charAt(dominoes.length()-2) == 'R'){
                    sb.append('R');
                }else sb.append('.');
            }else{
                sb.append(dominoes.charAt(dominoes.length()-1));
            }

            if(sb.toString().equals(dominoes)) return sb.toString();

            dominoes = sb.toString();
        }
    }
}
```

### [187. Repeated DNA Sequence](https://leetcode.com/problems/repeated-dna-sequences)

```Java
class Solution {
    public List<String> findRepeatedDnaSequences(String s) {
        int start =0,end=10;
        Set<String> set = new HashSet<>();
        Set<String> ans = new HashSet<>();

        while(end <= s.length()){
            String st = s.substring(start,end);
            if(set.contains(st)){
                ans.add(st);
            }
            set.add(st);
            end++; start++;
        }

        List<String> re = new ArrayList<>(ans);

        return re;

    }
}
```

### [1768. Merge Strings Alternately](https://leetcode.com/problems/merge-strings-alternately/)
```Java
class Solution {
    public String mergeAlternately(String word1, String word2) {
        int p1=0,p2=0;
        StringBuilder sb = new StringBuilder();

        while(p1<word1.length() && p2<word2.length()){
            sb.append(word1.charAt(p1));
            sb.append(word2.charAt(p2));
            p1++;p2++;
        }
        while(p1<word1.length()){
            sb.append(word1.charAt(p1));
            p1++;
        }
        while(p2<word2.length()){
            sb.append(word2.charAt(p2));
            p2++;
        }

        return sb.toString();

    }
}
```

### [1461. Check If a String Contains All Binary Codes of Size K](https://leetcode.com/problems/check-if-a-string-contains-all-binary-codes-of-size-k/)

```Java
import java.lang.Math;

class Solution {
    public boolean hasAllCodes(String s, int k) {
        Set<String> st = new HashSet<>();
        int total = (int)(Math.pow(2.0,k));
        int j=0;
        
        for(int i=k;i<=s.length();i++){
            st.add(s.substring(j,i));
            j++;
        }

        if(st.size() == total) return true;

        return false;

    }
}
```

###[Valid Parenthese](https://leetcode.com/problems/valid-parentheses/)

```Java
class Solution {
    public boolean isValid(String s) {
        Stack<Character> st = new Stack<>();

        for(int i=0;i<s.length();i++){

            char ch = s.charAt(i);

            if(ch == '('){
                st.push(')');
            }else if(ch == '{'){
                st.push('}');
            }else if(ch == '['){
                st.push(']');
            }else if(st.isEmpty() || st.pop() != ch){
                return false;
            }

        }
        return st.isEmpty();
    }
}
```

### [BaseBall game](https://leetcode.com/problems/baseball-game/)

```Java
class Solution {
    public int calPoints(String[] op) {
        Stack<Integer> st = new Stack<>();

        for(int i=0;i<op.length;i++){

            char ch = op[i].charAt(0);

            if(ch == '+'){
                int firstPop = st.pop();
                int sum = firstPop + (st.peek());
                
                st.push(firstPop);
                st.push(sum);
            }
            else if(ch == 'D'){
                int sum = st.peek()*2;
                
                st.push(sum);
            }
            else if(ch == 'C'){
                st.pop();
            }
            else{
                int add = Integer.parseInt(op[i]);
                
                st.push(add);
            }
        }
        
        int sum = 0;
        while(!st.isEmpty()){
            sum+= st.pop();
        }
        return sum;
    }   
}
```