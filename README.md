#include<stdio.h>
#include<cs50.h>
#include<math.h>

int main(){
    float change;
    
    do{
     printf("**********an integer value is not accepted!\n**********please try to enter as float amount of money you owed; example: like 9.87 not 987\n");
     change = get_float("How much change is owed?: ");     
      
    } while( change <= 0  );
    
    int coins = round(change * 100); 
    int quarter = coins % 25; // "a" means remainder
    
    int quotient1 = 0;
    int quotient3 = 0;
    int quotient4 = 0;
    int quotient5 = 0;
  
    if ( quarter != 0 ){ // and if quotient is "0" it means that                                    
        quotient1 = coins / 25;
       printf("You have  %d quarters/quarter.\n", quotient1);
    
    } 
    //else ( quarter = 0 );{  
       //int quotient2 = coins / 25; 
      // printf("You have %d quarter", quotient2);
       
    //}  
       int dimes = quarter % 10;
       
    if ( dimes < 10 ){
         quotient3 = quarter / 10;
        printf("\nYou have %d dimes/dime.\n", quotient3);
    }

        int nickels = dimes % 5;

       if ( nickels < 5 ){
         quotient4 = dimes / 5;
        printf("\nYou have %d nickels/nickel.\n", quotient4);
       }
          int pennies = nickels % 1;
          if ( pennies == 0 ){
               quotient5 = nickels / 1;
              printf("\nYou have %d pennies/penny.\n" ,quotient5);
          }                                                 
             int quotient_tot = quotient1 + quotient3 + quotient4 + quotient5;
             printf("%i\n", quotient_tot);
    return 0;
}
