Questions [Doc](https://docs.google.com/document/d/19XtlW0zlLAvF-gdkJxOrFFdf37RFQ47B5mYSveZSad8/edit?usp=sharing)
Pending Ques : 7, 8, 9, 11, 13, 16, 22
### 1.Recursive Fibonacci Series

```C
#include<stdio.h>

int fibannoci(int n){
    if(n == 0) return 0;
    if(n == 1) return 1;   
    return fibannoci(n-1)+fibannoci(n-2);
}

int main(){
    printf("%d",fibannoci(10));
}
```

### 2.Palindrome checker 
```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

int isPalindrome(char* str){
    
    int p1 = 0;
    int p2 = strlen(str)-1;
    
    while(p1<p2){
        if(str[p1++] != str[p2--]){
            return 0;
        }
    }
    return 1;
}

int main() {
    char str[1024];
    scanf("%s",&str);
    // char str[] = "aabbaa";
    printf("%d",isPalindrome(str));   
}
```

### 3.Prime Number Checker

```C
#include <stdio.h>
int isPrime(int n){
    
    int divi = 2;
    
    while(divi<n){
        if(n%divi == 0) return 0;
        divi++;
    }
    return 1;
}
int main() {
    int n;
    scanf("%d",&n);
    
    printf("%d",isPrime(n));
    return 0;
}
```

### 4.Anagram detector

```C
#include <stdio.h>
#include <string.h>
#include <ctype.h>
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int isAnagram(char* str1, char* str2){
    
    for(int i=0;i<strlen(str1);i++){
        for(int j=0;j<strlen(str1)-1;j++){
            if(str1[j] > str1[j+1]){
                char temp = str1[j];
                str1[j] = str1[j+1];
                str1[j+1] = temp;
            }
        }
    }
    
    for(int i=0;i<strlen(str2);i++){
        for(int j=0;j<strlen(str2)-1;j++){
            if(str2[j] > str2[j+1]){
                char temp = str2[j];
                str2[j] = str2[j+1];
                str2[j+1] = temp;
            }
        }
    }
    
    printf("%s\n%s\n",str1,str2);
    
    for(int i=0,j=0;i<strlen(str1) && j<strlen(str2);i++){
        if(!isalpha(str1[i])) continue;
        if(!isalpha(str2[i])) continue;
        printf("%c %c\n",str1[i],str2[i]);
        if(str1[i] != str2[i]) return 0;
        j++;
    }
    
    return 1;
}


int main() {

    char ch1[1024];
    fgets(ch1,sizeof(ch1),stdin);
    char ch2[1024];
	fgets(ch1,sizeof(ch2),stdin);
    
    for(int i=0;i<strlen(ch1);i++){
        ch1[i] = tolower(ch1[i]);
    }
    for(int i=0;i<strlen(ch2);i++){
        ch2[i] = tolower(ch2[i]);
    }
    
    printf("%d",isAnagram(ch1,ch2));
    return 0;
}
```

### 5.Recursive Factorial Calculator

```C
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int factorial(int n){
    if(n == 1) return 1;
    return n*factorial(n-1);
}

int main() {
    int n;
    scanf("%d",&n);
    
    printf("%d",factorial(n));
}
```

### 6.Power Function

```C
#include <stdio.h>
#include <string.h>
#include <ctype.h>
#include <math.h>

int powFunc(float inc1,float inc2){

    int ans = 1;
    if(inc2>=0){
        for(int i=0;i<inc2;i++){
            ans*=inc1;
        }
    }
    else if(inc2<0){
        for(int i=0;i<(inc2*-1);i++){
            ans/=inc1;
        }
    }
    return ans;
}

int main() {
    int n,n1;
    scanf("%d",&n);
    scanf("%d",&n1);
    
    printf("%d",powFunc(n,n1));
    printf("\n%f",pow(n,n1));
}
```

### 10.Sort the Array

```C
// Online C compiler to run C program online
#include <stdio.h>

void sortNo(int* arr,int n){
    
    for(int i=0;i<n;i++){
        
        for(int j=0;j<n-1;j++){
            
            if(arr[j]>arr[j+1]){
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
            
        }
        
    }
}

int main() {
    
    int n;
    scanf("%d",&n);
    
    int arr[n];
    for(int i=0;i<n;i++) scanf("%d",&arr[i]);
    
    sortNo(arr,n);
    
    for(int i=0;i<n;i++) printf("%d ",arr[i]);
}
```

### 12.String Reversal

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

char* reverse(char* str){
    
    int j=0,i=strlen(str)-1;
    
    while(j<i){
        char temp = str[i];
        str[i] = str[j];
        str[j] = temp;
        
        j++; i--;
    }
    return str;
}

int main() {
    char str[1024];
    fgets(str,sizeof(str),stdin);
    
    printf("%s",reverse(str));
}
```

### 14. Find string length

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

int findLen(char* str){
    return strlen(str)-1;
}

int main() {
    char str[1024];
    fgets(str,sizeof(str),stdin);
    
    printf("%d",findLen(str));
}
```

### 15.Odd & Even Sum

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

int Sum(int st,int end,int bln){
    
    int sum = 0;
    for(int i=st;i<=end;i+=2){
        sum+=i;
        printf("%d ",sum);
    } 
    return sum;
}

int main() {
    int st,end,bln;
    scanf("%d %d %d",&st,&end,&bln);
    
    printf("%d",Sum(st,end,bln));
    
}
```

### 17.Binary to Decimal

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
int BinaryToDecimal(char* str){
	return (int)strtol(str,NULL,2);
}

int main() {
	char str[2048];
	fgets(str,sizeof(str),stdin);
	
	printf("%d",BinaryToDecimal(str));
}
```

### 18.Lowercase to Uppercase

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>

char* toUpperCase(char* str){
    for(int i=0;i<strlen(str);i++){
        str[i] = toupper(str[i]);
    }
    return str;
}

int main() {
    char str[2048];
    fgets(str,sizeof(str),stdin);
    
    printf("%s",toUpperCase(str));
}
```

### 19.Leap year

```C
// Online C compiler to run C program online
#include <stdio.h>

int isLeapYear(int yr){
    if((yr%4 == 0 && yr%100 != 0) || yr%400 == 0){
        return 1;
    }
    return 0;
}

int main() {
    int n;
    scanf("%d",&n);
    
    printf("%d",isLeapYear(n));
}
```

### 20.Remove Duplicates

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>

int removeDup(int* arr,int n){
    
    int* res = (int*)malloc(n*sizeof(int));
    int count = 0;
    
    for(int i=0;i<n;i++){
        int flag = 1;
        for(int j=0;j<n;j++){
            if(i == j) continue;
            if(arr[i] == arr[j]){
                flag = 0;
                break;
            }
        }
        if(flag){
            res[count] = arr[i];
            count++;
        }
    }
    
    for(int i=0;i<count;i++){
        arr[i] = res[i];
    }
    return count;
}

int main() {
    int n;
    scanf("%d",&n);
    
    int arr[n];
    for(int i=0;i<n;i++) scanf("%d",&arr[i]);
    
    int res = removeDup(arr,n);
    
    for(int i=0;i<res;i++){
        printf("%d ",arr[i]);
    }
}
```

### 21.Reverse the Sentence

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

char* reverse(char* str){
    int p1 = 0,p2 = strlen(str)-1;
    
    while(p1<p2){
        
        char temp = str[p1];
        str[p1] = str[p2];
        str[p2] = temp;
        
        p1++;p2--;
    }
    return str;
}

int main() {
    char str[1024];
    
    fgets(str,sizeof(str),stdin);
    
    printf("%s",reverse(str));
}
```

### 23. Armstrong or perfect numbers

```C
// Online C compiler to run C program online
#include <stdio.h>
#include<math.h>

int isAmstrong(int n){
    
    int dup = n;
    int len = 0;
    
    while(dup>0){
        len++;
        dup/=10;
    }
    
    dup = n;
    int ans = 0;
    while(dup>0){
        ans+=(pow(dup%10,len)); dup/=10;
    }
    
    return ans == n;
    
}

int isPerfect(int n){
    
    int ans = 1;
    for(int i=2;i<n;i++){
        if(n%i == 0) ans+=i;
    }
    return ans == n;
}

int main() {
    printf("%d",isPerfect(27));
}
```
### 24.Simple Calculator

```C
// Online C compiler to run C program online
#include <stdio.h>

int add(int a,int b) {return a+b;}
int sub(int a,int b) {return a-b;}
int mul(int a,int b) {return a*b;}
int divi(int a,int b) {return a/b;}


int calci(char ch,int a,int b){
    
    if(ch == '-') return sub(a,b);
    if(ch == '+') return add(a,b);
    if(ch == '/') return divi(a,b);
    if(ch == '*') return mul(a,b);
    
    return 0;
}

int main() {
    
    char ch;
    int a,b;
    scanf("%c %d %d",&ch,&a,&b);
    
    int res = calci(ch,a,b);
    printf("%d",res);
}
```

### 25.Even Number counter

```C
// Online C compiler to run C program online
#include <stdio.h>

int countEven(int* n,int size){
    int count = 0;
    
    for(int i=0;i<size;i++){
        if(n[i]%2 == 0){
            count++;
        } 
    }
    return count;
}

int main() {
    int n;
    scanf("%d",&n);
    
    int arr[n];
    for(int i=0;i<n;i++) scanf("%d",&arr[i]);
    
    printf("%d",countEven(arr,n));
}
```

### 26.Odd Number counter

```C
// Online C compiler to run C program online
#include <stdio.h>

int countOdd(int* n,int size){
    int count = 0;
    
    for(int i=0;i<size;i++){
        if(n[i]%2 == 1){
            count++;
        } 
    }
    return count;
}

int main() {
    int n;
    scanf("%d",&n);
    
    int arr[n];
    for(int i=0;i<n;i++) scanf("%d",&arr[i]);
    
    printf("%d",countOdd(arr,n));
}
```

### 27.First Non Repeating Character

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>
#include <ctype.h>

char firstRepeat(char* str){
    
    for(int i=0;i<strlen(str);i++){
        str[i] = tolower(str[i]);
    }
    
    for(int i=0;i<strlen(str);i++){
        int flag = 0;
        for(int j=0;j<strlen(str);j++){
            
            if(i == j) continue;
            if(str[i] == str[j]) flag = 1;
            
        }
        if(!flag) return str[i];
    }
    return '1';
}

int main() {
    char str[100];
    fgets(str,sizeof(str),stdin);
    
    printf("%c",firstRepeat(str));
}
```