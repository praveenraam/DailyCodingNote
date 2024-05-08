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