Video [Link](https://youtu.be/_HRA37X8N_Q?si=AQPhBYGY5ZS9C6yT)
Topic No 12
Next Topic [[Binary Search]]

#### Linear search is an algorithm that go through all the items from first to the last element and picks the required one.

#### Example:

###### Problem : Finding the position of the targeted element in an array

```Java
public class Arr {  
    public static void main(String[] args) {  
        int[] Number = {1,2,3,4,5,6,6,7};  
        System.out.println(LinearSearch(Number,6));  
    }  
    static int LinearSearch(int[] ArrS,int Target){  
        for(int index = 0; index <ArrS.length; index++){  
            if(ArrS[index] == Target){  
                return index;  
            }  
        }  
        return -1;  
    }  
    static int LinearSearch2(int[] ArrS,int Target){  
        for (int arr : ArrS) {  
            if (arr == Target) {  
                return arr;  
            }  
        }  
        return -1;  
    }  
} //Out = 5
```

## Questions

#### Search in Strings

==To find length in String '.length()' should be used instead of '.length' as it is used for the integers 

```Java
public class StringSearch {  
    public static void main(String[] args) {  
        System.out.println(CharBool("hello",'o'));  
    }  
    static boolean CharBool(String Word,char target){  
        if(Word.isEmpty()){
            return false;
        }
        for(int i=0;i<Word.length();i++){
            if(Word.charAt(i) == target){  
                return true;  
            }
        }
        return false;
    }  
} // Out = true
```

This program is using Enhanced for loop for String
```Java
public class StringSearch {  
    public static void main(String[] args) {  
        System.out.println(CharBool("hello",'z'));  
    }  
    static boolean CharBool(String Word,char target){  
        if(Word.isEmpty()){  
            return false;  
        }  
        for(char ch : Word.toCharArray()){  
         if(ch == target){  
             return true;  
         }  
        }  
        return false;  
    }  
} // Out = False
```


#### Search in Range

```Java
public class SearchInRange {  
    public static void main(String[] args) {  
        int[] ArrayInp = {1,2,3,4,5,6,7,8,9,0};  
        System.out.println(SearcherFunc(ArrayInp,8,2,8));  
    }  
    static int SearcherFunc(int[] Array,int target ,int start,int end){  
        if(Array.length == 0){  
            return -1;  
        }  
        for(int index=start;index<=end;index++){  
            if(Array[index] == target){  
                return index;  
            }  
        } return -1;  
    }  
}
```


#### Minimum in Array
```Java
public class MinimunFinder{
	public static void main(String[] args){
		int[] ArrInp = {-3,2,3,4,5,6,7,9};
		System.out.println(MinFunc(ArrInp));
	}
	static int MinFunc(int[] Array){
	if(Array.length == 0){
		return 0;
	}
	int min = 0;
	for(int Element : Array){
		if(Element < min){
			min = Element;
			}
		} 	return min;
	}
}
```

####  Search in 2D Array 
```Java
import java.util.Arrays;  
  
public class Search2D {  
    public static void main(String[] args) {  
        int[][] ArrInp = {  
                {1,2,3,4},{5,6,7,8},{9,0},{11,22,33,44,55}  
        };  
        System.out.println(Arrays.toString(Searcher(ArrInp,22)));  
    }  
    static int[] Searcher(int[][] Array,int target){  
        for(int index = 0; index<Array.length ; index++){  
            for(int Jindex =0;Jindex<Array[index].length;Jindex++){  
                if(Array[index][Jindex] == target){  
                   return new int[]{index, Jindex};//Create object array then return it 
                }  
            }  
        } return new int[]{-1,-1};  
    }  
} // Out = [3,1]
```

#### Max in 2D Array

Same code from the last question with small changes and for Loop to for Each Loop
```Java
import java.util.Arrays;  
  
public class Search2D {  
    public static void main(String[] args) {  
        int[][] ArrInp = {  
                {1,2,3,4},{5,6,7,8},{9,0,55},{11,22,33,44}  
        };  
        System.out.println(MaxFunc(ArrInp));  
    }  
    static int MaxFunc(int[][] Array){  
        int max = Integer.MIN_VALUE;  // Min value of the int (-2147483647) 
        for(int[] ArrInsider : Array){  
            for(int InInsider : ArrInsider){  
                if(InInsider > max){  
                    max = InInsider;  
                }  
            }  
        } return max;  
    }  
}
```

#### Finding the Even Number of Element in the Arraty

This question is to find the number of element that are even in count 
Ex: 2020 : 4 numbers so even , 567 : 3 number so odd

```Java
public class EvenNumber {  
    public static void main(String[] args) {  
        int[] Array = {200,2000,23,2345,22222,22};  
        System.out.println(FindNumber(Array));  
    }  
    static int FindNumber(int[] Array){  
        int count = 0;  
        for(int i=0;i<Array.length;i++){  
            if(evenFind(Array[i])){  
                count++;  
            }  
        } return count;  
    }  
    static boolean evenFind(int number){  
        int Count = 0;  
        while(number > 0){  
            number/=10;  
            Count++;  
        }  
        return Count%2==0; // returns True or False
    }  
} // Out = 4 
```

#### ==Trick to find the Number of digits in a number==

```Java
public class EvenNumber {  
    public static void main(String[] args) {   
        System.out.println(digitCount(323));  
    }
static int digitCount(int Number){  
    if(Number < 0){  
        Number*=-1;  // Converting to positive number
    }  
    return (int)(Math.log10(Number)+1);  
} // Out = 3
```

#### Wealth Checker

[Link Of Leet code](https://leetcode.com/problems/richest-customer-wealth)

```Java
public class WealthFind {  
    public static void main(String[] args) {  
        int [][] Array = {  
                {3,4},{3,7},{8,6}  
        };  
        System.out.println(Finder(Array));  
    }  
    static int Finder(int[][] Account){  
        int WealthAmount = 0;  
        for(int[] Person : Account){  
            int AmountOfPerson = 0;  
            for(int WealthOfPerson : Person){  
                AmountOfPerson += WealthOfPerson;  
            }  
            if(WealthAmount < AmountOfPerson ){  
                WealthAmount = AmountOfPerson;  
            }  
        } return WealthAmount;  
    }  
}
```

