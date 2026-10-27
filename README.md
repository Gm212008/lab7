# lab7
strings



#include <stdio.h>
#include <string.h>
#include <ctype.h>
#include <stdbool.h>

int main(){
   char s[100];
   printf (" Enter a string : ");
   fgets (s , sizeof ( s ) , stdin );
   
   int len=strlen(s);
   if(len>0 &&  s[len - 1] == '\n') {
      s[len - 1] = '\0 ';
      len--;
   }
   
   int left=0, right=len-1;
   bool palin=true;
   while(left<right){
      while(left<right && !isalnum((unsigned char) s[left] )) left++;
      while(left<right && !isalnum((unsigned char) s[right] )) right--;
      
      if ( tolower (( unsigned char ) s [ left ]) != tolower (( unsigned char ) s [right ]) ) {
         palin = false;
         break;
         }
      left ++;
      right--;
      }
      
      if ( palin ) printf (" Palindrome \n");
      else printf ("Not a Palindrome \n");
      return 0;
}
