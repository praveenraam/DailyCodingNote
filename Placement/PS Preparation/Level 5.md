Questions [Doc](https://docs.google.com/document/d/19XtlW0zlLAvF-gdkJxOrFFdf37RFQ47B5mYSveZSad8/edit?usp=sharing)
Pending Ques : 8, 9, 11, 13 
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

### 7.String Compression

```C
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

char* comp(char* str){
    
    char* res = (char*)malloc((strlen(str)*2 +1)*sizeof(char));
    
    int count = 1;
    int j=0;
    
    for(int i=0;i<strlen(str);i++){
        if(str[i] == str[i+1]) count++;
        else{
            res[j] = str[i];
            j++;
            if(count > 1){
                res[j] = count+'0';
                j++;
            }
            count=1;
        }
    }
    return res;
}

int main(){
    char str[1024];
    scanf("%s",str);
    
    printf("%s",comp(str));
}

```

### 8.Matrix Transpose

```C
#include<stdio.h>
#include<stdlib.h>


int** transpose(int m,int n,int arr[m][n]){
    
    int** ans = (int**)malloc(n*sizeof(int*));
    
    for(int i=0;i<n;i++){
        ans[i] = (int*)malloc(m*sizeof(int));
    }
    
    for(int i=0;i<m;i++){
        for(int j=0;j<n;j++){
            ans[j][i] = arr[i][j];
        }
    }
    
    for(int i=0;i<n;i++){
        for(int j=0;j<m;j++){
            printf("%d ",ans[i][j]);
        }
        printf("\n");
    }
    
    return ans;
}

int main(){
    int m=3,n=4;
    int arr[3][4] = {
        {1,2,3,4},{3,4,5,6},{5,6,7,8}
    };
    
    transpose(m,n,arr);
    
}
```

### Matrix Multiplication

```C
// Online C compiler to run C program online
#include <stdio.h>
void is(int r1,int c1,int r2,int c2,int ar1[][c1],int ar2[][c2]){
    
    int res[r1][c2];
    
    for(int i=0;i<r1;i++){
        for(int j=0;j<c2;j++){
            res[i][j] = 0;
        }
    }
    
    for(int i=0;i<r1;i++){
        for(int j=0;j<c2;j++){
            for(int k=0;k<r2;k++){
                res[i][j] += ar1[i][k]*ar2[k][j];
            }
        }
    }
    
    for(int i=0;i<r1;i++){
        for(int j=0;j<c2;j++){
            printf("%d ",res[i][j]);
        }
        printf("\n");
    }
    
}
int main() {
    int ar1[][2] = {{2,2},{3,3}};
    int ar2[][2] = {{3,3},{4,4}};
    
    is(2,2,2,2,ar1,ar2);
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

### 16.GCD & LCM

```C
// Online C compiler to run C program online
#include <stdio.h>

int lcm(int n,int m){
    
    int res = 0;
    
    for(int i=(n>m ? n : m);1;i++){
        
        if(i%n == 0 && i%m == 0) return i;
        
    }
    return -1;
}

int gcd(int n,int m){
    
    int res = 0;
    for(int i=1;i<n && i<m;i++){
        
        if(n%i==0 && m%i == 0){
            res = i;
        }
        
    }
    return res;
}

int main() {

    int n1,n2;
    scanf("%d %d",&n1,&n2);
    
    printf("%d",gcd(n1,n2));
    
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

### 22.Sum of Prime

```C
// Online C compiler to run C program online
#include <stdio.h>

int isPrime(int n){
    
    if(n <= 1) return 0;
    
    int divi = 2;
    while(n>divi){
        if(n%divi == 0) return 0; 
        divi++;
    }
    return 1;
}

int isSumOfPrime(int n){
    
    for(int i=1;i<n;i++){
        if(isPrime(i)) {
            for(int j=1;j<n;j++){
                if(isPrime(j) && (i+j == n)) return 1;
            }
        }
    }
    return 0;
}

int main() {
    int n;
    scanf("%d",&n);
    printf("%d",isSumOfPrime(n));
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

### Find the max and min length of the word in the given string

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void is(char* str){
    
    int lastSpace = 0,max = -1, maxCount = 0;
    int min = 0, minCount = 100000; 
    int count = 0;
    
    for(int i=0;i<strlen(str);i++){
        
        if(str[i] == ' '){
            
            if(count > maxCount){
                maxCount = count;
                max = lastSpace;
                lastSpace = i+1;
            }
            if(count < minCount){
                minCount = count;
                min = lastSpace;
                lastSpace = i+1;
            }
            count=0;
            
        }else{
            count++;
        }
    }
    count = 0;
    for(int i=strlen(str)-1;i>=0;i--){
        if(str[i] == ' '){
            
            if(count > maxCount){
                maxCount = count;
                max = i+1;
            }
            if(count < minCount){
                minCount = count;
                min = i+1;
            }
            count=0;
            break;
        }else{
            count++;
        }
    }
    
    for(int i=max;str[i] != ' ' & i<strlen(str);i++){
        printf("%c",str[i]);
    }
    printf("\n");
    for(int i=min;str[i]!=' ' & i<strlen(str);i++){
        printf("%c",str[i]);
    }
}

int main() {
    is("google isee the largest companys");
}
```

### Int to roman 

```C
#include <stdio.h>  
int main() {  

  int n;  
  scanf("%d",&n);  

  int ar[] = {1000,900,500,400,100,90,50,40,10,9,5,4,1};   
  char str[][3] = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};  

  for(int i=0;i<13;i++){  
    while(ar[i]<=n){  
        printf("%s",str[i]);  
        n-=ar[i];  
    }  
  }  
  return 0;  
}
```

### Roman to Int

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>
int main() {
    
    char str[1024];
    scanf("%s",str);
    
    int ans = 0;
    
    for(int i=0;i<strlen(str);i++){
        if(str[i] == 'M'){
            ans+=1000;
        }else if(str[i] == 'D'){
            ans+=500;
        }else if(str[i] == 'C'){
            if(str[i+1] == 'M'){
                ans+=900;
                i++;
            }else if(str[i+1] == 'D'){
                ans+=400;
                i++;
            }else{
                ans+=100;
            }
        }else if(str[i] == 'L'){
            if(str[i+1] == 'C'){
                ans+=90;
                i++;
            }else{
                ans+=50;
            }
        }else if(str[i] == 'X'){
            if(str[i+1] == 'L'){
                ans+=40;
                i++;
            }else{
                ans+=10;
            }
        }else if(str[i] == 'V'){
            ans+=5;
        }else if(str[i] == 'I'){
            if(str[i+1] == 'X'){
                ans+=9;
                i++;
            }else if(str[i+1] = 'V'){
                ans+=4;
                i++;
            }else{
                ans+=1;
            }
        }
    }
    printf("%d",ans);
}
```

### Circular Prime

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>

int isPrime(int n){
    
    if(n == 0 || n == 1) return 1;
    
    int divi = 2;
    while(divi<n){
        if(n%divi == 0) return 0;
        divi++;
    }
    return 1;
}
int isCircular(int n){
    
    int dup = n;
    int rem = dup%10; dup/=10;
    int no = 0;
    while(dup!=0){
        no = no*10 + dup%10;
        dup/=10;
    }
    while(no != 0){
        rem = rem*10 + no%10;
        no/=10;
    }
    
    if(!isPrime(n)) return 0;
    
    while(rem!=n){
        if(!isPrime(rem)) return 0;
        
        int var = rem%10; rem/=10;
        int no2 = 0;
        
        while(rem!=0){
            no2 = no2*10+(rem%10);
            rem/=10;
        }
        while(no2!=0){
            var = var*10+(no2%10);
            no2/=10;
        }
        
        rem = var;
    }
    return 1;
}

int main() {

    int n;
    scanf("%d",&n);
    
    printf("%d",isCircular(n));

}
```

### Find the pivot 

```C
// Online C compiler to run C program online
#include <stdio.h>

int is(int ar[],int n){
    
    int tot = 0;
    for(int i=0;i<n;i++){
        tot+=ar[i];
    }
    int tot2 = 0;
    for(int i=0;i<n;i++){
        tot2+=ar[i];
        if(tot == tot2) return i;
        tot-=ar[i];
    }
    return -1;
}

int main() {
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    printf("%d",is(arr,n));
}
```

### Sum of max in row and col

```C
// Online C compiler to run C program online
#include <stdio.h>

int is(int n,int m, int ar[n][m]){
    int res = 0;
    for(int i=0;i<n;i++){
        int maxInd = 0;
        for(int j=0;j<m;j++){
            if(ar[i][maxInd] < ar[i][j]){
                maxInd = j;
            }
        }
        res+=ar[i][maxInd];
        
        int MI = 0;
        for(int j=0;j<m;j++){
            if(ar[j][i] > ar[MI][i]){
                MI = j;
            }
        }
        res+=ar[MI][i];
        
    }
    return res;
}

int main() {
    int ar[][3] = {
        {1,2,3},
        {4,5,6},
        {7,8,9}
    };
    
    printf("%d",is(3,3,ar));
    
}
```