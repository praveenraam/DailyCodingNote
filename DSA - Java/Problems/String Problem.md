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
