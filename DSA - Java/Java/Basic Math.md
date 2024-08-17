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

### Module of 10^9+7

What is this and why we use this -> Incase if the output is very large integer, only few algo can solve in efficient time.

- The reason to use this to prevent the integer overflow 


Example:
a = 145785635595363569532135132
b = 3151635135413512165131321321
c = 999874455222222200651351351
m = 1000000007

``Print (a*b*c)%m.``

**Method 1:**

```
First, multiply all the number and then take modulo:

(a*b*c)%m = (459405448184212290893339835148809
515332440033400818566717735644307024625348601572) % 
1000000007
a*b*c does not fit even in the unsigned long long 
int due to which system drop some of its most 
significant digits. Therefore, it gives the wrong answer.
(a*b*c)%m = 798848767
```

**Method 2:**
```
Take modulo at each intermediate steps:
i = 1
i = (i*a) % m    // i = 508086243
i = (i*b) % m    // i = 144702857
i = (i*c) % m    // i = 798848767
i = 798848767 

Method 2 always gives the correct answer.
```

