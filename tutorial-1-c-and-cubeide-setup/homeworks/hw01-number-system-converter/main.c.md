# Skeleton Code

> Please don't include any extra libraries in your homework. We already included
> all necessary libraries in the skeleton code.

```c
#include <stdio.h>
#include <string.h>
#include <stdint.h>
#include <stdbool.h>

const char* const error_msg_decimal = "Error! That set of number is not a decimal number.\n";
const char* const error_msg_trinary = "Error! That set of number is not a trinary number.\n";
const char* const error_msg_duodecimal = "Error! That set of number is not a duodecimal number.\n";
const char* const error_msg_unsupported_system = "Error! The number system is not supported.\n";

const char* const msg_prompt_number = "Please enter a set of number:\n";
const char* const msg_prompt_current_number_system = "Please enter the current number system:\n";
const char* const msg_prompt_number_system_to_convert = "Please enter the number system you want the set of number be converted to:\n";
const char* const msg_output = "Output=";

int poo(int a,int b){
    int d=1;
    for (int c=0;c<b;c++)
        d*=a;
    return d;
}   

int countnum(char a[]){
    int count=0;
    for (int i=0;a[i] != '\0';i++){
            count++; }
    return count;
}
int main(){
  
    

    printf("%s", msg_prompt_number);
     char num[64]={};
     scanf("%s",num);
     if(num[0]=='-'){
        printf("Error! Then negative number system is not supported");
     }
    /**
     * @brief 
     * Get user input for number to be convert
     */
    

    // TODO:
    int con;
    int temp=0;
    int count=countnum(num);
    printf("%s", msg_prompt_current_number_system);
    
    scanf("%d",&con);
    if(con!=3&&con!=12&&con!=10){printf("%s",error_msg_unsupported_system);return 0;}
    char cleck;
    for (int i=0;i<count;i++){
        switch (num[i]){
            case 'A':cleck=10;break;
            case 'B':cleck=11;break;
            default:
            cleck=(int)(num[i]-'0');
        }
        if (cleck>=con){
            switch (con){
                case 3:printf("%s",error_msg_trinary);break;
                case 10:printf("%s",error_msg_decimal);break;
                defualt:
                    printf("%s",error_msg_duodecimal);
            }
            return 0;
        }}
            
      
        for (int i=0;i<count;i++){
        
            temp+=((int)num[i]-48)*(poo(con,(count-i-1)));
        }
    
    
        /**
     * @brief 
     * Get user input for current number system
     */
    
    
    // TODO:
    char fin[64]={};
    char finn[64]={};
    int i=0;
    printf("%s", msg_prompt_number_system_to_convert);
    int cur;
    scanf("%d",&cur);
    if (cur!=3 && cur!=10 && cur!=12)
    return 0;

    while ( temp>=cur ){
        switch (temp%cur){
            case 10:fin[i]='A';break;
            case 11:fin[i]='B';break;
            default:
            fin[i]=(char)(temp%cur+'0');
        }
        temp/=cur;
        i++;
    }
    switch (temp){
            case 10:fin[i]='A';break;
            case 11:fin[i]='B';break;
            default:
            fin[i]=(char)(temp+'0');
        }
    
    int ttt=countnum(fin);
    for (int h=0;h<ttt;h++){
        finn[h]=fin[ttt-h-1];
    }
    printf("%s%s",msg_output,finn);
    /**
     * @brief 
     * Get user input for the number system for conversion.
     * Print converted number in format of "Output=12", e.g Output=ABCDEF
     * No space should be inserted in the asnwer "Output=XXX".
     * In case of wrong number system for conversion, please use the above error msgs.
     */

    // TODO:
  


    return 0;
}
// C programmers never die. They are just cast into void.
