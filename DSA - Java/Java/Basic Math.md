Video [Link](https://youtu.be/1xNbjMdbjug?si=cgSJMGocBOCHroqE)
Next Topic : [[Arrays]]
Problems : [[Math Problems]]
### Digit extraction 

The extraction is done in reverse order
```Java
class myClass{
	public static void main(String[] args){
		
	}
	public static void DigitPrinting(int Number){
		int breaking = 0;
		while(Number!=0){ // Condition
			breaking = x%10; // Point 1
			System.out.println(breaking);
			x = x/10; // Point 2
		} 
	}
} 
```

**Point 1** : we are doing mod operation , which will give us the remainder , while mod with 10 we can split the last number from the input number
**Point 2** : we divide the input number , so we neglect the last number that we got in the before step

Ex : ![[Pasted image 20240124090307.png]]