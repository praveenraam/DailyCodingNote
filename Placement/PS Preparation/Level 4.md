### Topic : String 


### Print without vowels
```C
#include <stdio.h>
#include<string.h>

int main() {
    char s[100];
    fgets(s,sizeof(s),stdin);
    
    for(int i=0;i<strlen(s);i++){
        if(s[i] == 'A' || s[i] == 'E' || s[i] == 'I' || s[i] == 'O' || s[i] == 'U'|| s[i] == 'a'|| s[i] == 'e'|| s[i] == 'i'|| s[i] == 'o'|| s[i] == 'u'){
            continue;
        }
        printf("%c",s[i]);
    }


    return 0;
}
```

### program to print the given string by replacing specific letter in a string and replace it with provided characters  Example : e-->f  h-->j  numbers --> n hello there 123! --> jfllo tjfrf 123!

```C
#include <stdio.h>
#include<string.h>

int main() {
    char s[100];
    fgets(s,sizeof(s),stdin);
    
    char c1, c2,c3,c4;
    scanf("%c %c %c %c",&c1,&c2,&c3,&c4);
    printf("%c %c %c %c",c1,c2,c3,c4);
    printf("\n");
    for(int i=0;i<strlen(s);i++){
        if(s[i] == c1){
            printf("%c",c2);
            continue;
        }else if(s[i] == c3){
            printf("%c",c4);
            continue;
        }else{
            printf("%c",s[i]);
        }
    }


    return 0;
}
```

### program to print maximum character that is repeated in the string i.e Hello World - l ( l 3 repetition )
```C
#include<stdio.h>
#include<string.h>


int main(){
    char in[1000];
    fgets(in,sizeof(in),stdin);
    
    int ar[256];
    int max = -1;
    char c = ' ';
    
    for(int i=0;i<strlen(in);i++){
        if(in[i] == ' ') continue;
        char ch = in[i];
        ar[ch] = ar[ch]+1;
        if(max < ar[ch]) {
            max = ar[ch];
            c = ch;
        }
    }
    printf("%c %d\n",c,max);
}
```

### program to print the given string without any alphabet character
```C
#include<stdio.h>
#include<string.h>


int main(){
    char in[1000];
    fgets(in,sizeof(in),stdin);
    
    int ar[256];
    int max = -1;
    char c = ' ';
    
    for(int i=0;i<strlen(in);i++){
        char ch = in[i];
        if((ch >= 'A' && ch <= 'Z')||(ch>='a'&&ch<='z')) continue;
        else {
            printf("%c",ch);
        }
    }
}
```

### print the string replacing the space with given character - input : string - "Hello World" replace :- "$" -- output : "Hello$World"
```C
#include<stdio.h>
#include<string.h>


int main(){
    char in[1024];
    fgets(in,sizeof(in),stdin);
    
    char ch;
    scanf("%d",&ch);
    
    for(int i=0;i<strlen(in);i++){
        if(in[i] == ' ') printf("%c",ch);
        else printf("%c",in[i]);
    }
    
}
```

### Print the First UpperCase Letter.  <br>Eg. Input: "hello World" --> Ouput: W
```C
#include<stdio.h>
#include<string.h>


int main(){
    char in[1024];
    fgets(in,sizeof(in),stdin);
    
    
    for(int i=0;i<strlen(in);i++){
        char c = in[i];
        if(c>='A'&&c<='Z'){
            printf("%c",c);
            break;
        }
    }
    
}
```

### Valid Anagram

```C
#include<stdio.h>
#include<string.h>


int main(){
    char in1[1024];
    char in2[1024];
    fgets(in1,sizeof(in1),stdin);
    fgets(in2,sizeof(in2),stdin);
    int ar[256];
    
    for(int i=0;i<256;i++){
        ar[i] = 0;
    }
    
    if(strlen(in2) != strlen(in1)){
        printf("False");
        return 0;
    }
    
    for(int i=0;i<strlen(in1);i++){
        char ch = in1[i];
        ar[ch] = ar[ch]+1;
    }
    
    for(int i=0;i<strlen(in2);i++){
        char ch = in2[i];
        ar[ch] = ar[ch]-1;
    }
    
    for(int i=0;i<256;i++){
        if(ar[i] != 0) {
            printf("False");
            return 0;
        }
    }
    
    printf("True");   
}
```


### Find the largest and smallest word in a string. Input: The bottle is full Output: is bottle

```C
// Online C compiler to run C program online
#include <stdio.h>
#include<string.h>
int main() {
    char in[1024];
    
    fgets(in,sizeof(in),stdin);
    int start = -1;
    int min = 10000;
    int mS=-1;
    int count=0;
    int max = -1;
    int maxS = 0;
    for(int i=0;i<strlen(in);i++){
        if(in[i] == ' ' || i+1 == strlen(in)){
            if(min > count){
                min = count;
                mS=start+1;
            }else if(max<count){
                max = count;
                maxS = start+1;
            }
            start=i;
            count=0;
        }else{
            count++;
        }
    }
    
    for(int i=mS;in[i] != ' ';i++){
        printf("%c",in[i]);
    }
    printf("\n");
    
    for(int i=maxS;in[i] != ' ' && i < strlen(in);i++){
        printf("%c",in[i]);
    }
    
}
```

