#include<stdio.h>
#include <time.h>   //TIME DELAY
#include <dos.h>    //SLEEP FUNCTION 
#include <stdlib.h> // EXIT , RANDOM FUNCTION

void winner(int*,int ,int,char []);

void winner(int *a,int i,int temp,char name[10])
{
    if(*a==100)
    {
        printf("\n\n\t\t\t\t!!!!!!!!!     %s IS THE WINNER     !!!!!!!",name);
        exit(0);
        return ;
    }
    else if (*a>100)
    {
        *a=temp;
        return;
    }
    else 
        return;

}



int main()

{
int arr[100],p;         //p-no of players


//----------------------------------- LADDERS , SNAKES AND VALUES OF BLOCK ---------------------------------------


for (int i = 1; i < 101; i++)
{
    if (i==4) 
        arr[i]=45;
    else if (i==6) 
        arr[i]=25;
    else if (i==32)     
        arr[i]=5; 
    else if (i==40)
        arr[i]=77;
    else if (i==43) 
        arr[i]=17;
    else if (i==47) 
        arr[i]=66; 
    else if (i==50) 
        arr[i]=93; 
    else if (i==52) 
        arr[i]=11; 
    else if (i==57) 
        arr[i]=24;
    else if (i==61) 
        arr[i]=98;
    else if (i==62) 
        arr[i]=22;
    else if (i==68) 
        arr[i]=87;
    else if (i==91) 
        arr[i]=51;
    else if (i==95) 
        arr[i]=76;
    else if (i==99) 
        arr[i]=10;
    
    else 
        arr[i]=i; 
}

// ----------------------------------------- SHOWING BOARD -----------------------------------------------------

for (int i = 100; i >0 ; i--)
{
    if (i%10==0)
        printf("\n");
    
    printf("| %4d |",arr[i] ) ;
}

// ---------------------------------------------- PLAYERS -----------------------------------------------------

printf("\n \n \n Enter  the number of players : ");
scanf("%d",&p);

printf("\n There are %d players : ", p);


int players[p];         // players - store place of player after every throw
char playname[p][10];     // playname - store name of player

for (int i = 1; i <= p; i++)
{
        printf("\n Enter the name of player %d : ",i);
        scanf("%s",&playname[i]);   
}



printf("\n\n Players are at place : ");

for (int i = 1; i <= p; i++)
{ 
    players[i]=0;
    printf("%d  ",players[i]);
}


//----------------------------------------- DICE THROW---------------------------------------------------------------------------------------


srand(time(0));  // Initialize random number generator.

do
{
    int i=1;

    while (i<=p)
{  
    int dice; 
    char t;
    sleep(1); 

    printf("\n \t\t\t\t\t%s will throw dice ", playname[i]);

    printf("\n......CLICK ENTER TO THROW : ");
    scanf("%c",&t);

    dice=(rand() % 6) + 1; 
    printf("\n Outcome at dice is: %d ",dice);

    int temp=players[i];

    if((players[i]==0)&&(dice==6))
        players[i]=1;

    else if (players[i]>0)
        players[i]+=dice;
    else
        printf("\n XXXXXXXXXXXXXXXXXXXXXXXXXXX NEED 6 ASAP TO START YOUR GAME XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX \n");
    

    winner(&players[i],i,temp,playname[i]);  //check if someone won the game


    printf("\n%s is at : %d \n \n ",playname[i],players[i]);

    if((players[i]!=0) && (players[i]<arr[players[i]]))
        {
            printf ("\n // // // // // // // // // // // // // // // LADDER ENCOUNTERED // // // // // // // // // // // // // // // //");
            players[i]=arr[players[i]];
            printf("\n%s is at : %d \n \n ",playname[i],players[i]);
        }

    if((players[i]!=0) && (players[i]>arr[players[i]]))
        {
            printf ("\n~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~SNAKE ENCOUNTERED~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~");
            players[i]=arr[players[i]];
            printf("\n%s is at : %d \n \n ",playname[i],players[i]);
        }
    
    i++;


}
    printf("\n \t\t\t\t\tPlayers are at place : ");
    for (int i = 1; i <= p; i++)
    {
        printf("%d  ",players[i]);
    }
    printf("\n\n");

}while (1);


return 0;

}
