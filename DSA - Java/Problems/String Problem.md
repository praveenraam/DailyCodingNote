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

