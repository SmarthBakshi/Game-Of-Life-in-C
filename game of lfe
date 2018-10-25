#include<stdio.h>
#include<conio.h>
#define HEIGHT 10
#define WIDTH 10

/*Used to Display the grid or workspace and setting all the elements of each Generation as zero initially.*/
void clearscreen(char tableA[HEIGHT][WIDTH], char tableB[HEIGHT][WIDTH])
 { int height, width;
   for(height=0; height<HEIGHT; height++)
     { for(width=0; width<WIDTH; width++)
       { tableA[height][width]=0;
         tableB[height][width]=0;
       }
     }
   for(height=0; height<HEIGHT; height++)
     { for(width=0; width<WIDTH; width++)
        { printf("-");
        }
        printf("\n");
     }
 }
 
/*Used to take no. of live organisms and their coordinates*/
void takeuser(char tableA[HEIGHT][WIDTH])
 { int n;
   int i;
   int height=0;
   int width=0;
   printf("Enter the number of living organisms in the initial generation:");
   scanf("%d",&n);
   for( i=0; i<n; i++)
  { 
   printf("Enter the (x y) coordinate where %d organism will live", i+1);
   scanf("%d", &height); 
   scanf("%d", &width);
   if(height>=HEIGHT || width>=WIDTH)
   { printf("Invalid coordinates\n");
   }
   else
   { tableA[height][width]=1;
   }
  }
 }
  
/*Used to display the grid*/
void display(char tableA[HEIGHT][WIDTH])
 {  int height;
    int width;
    for(height=0; height<HEIGHT; height++)
      { for(width=0; width<WIDTH; width++)
         { if(tableA[height][width]==1)
            { printf("$");
            }
           else
            { printf("*");
            }
         }
         printf("\n");
      }
 }     

/*Used to calculate the no. of live neighbors*/ 
void calculate(char tableA[HEIGHT][WIDTH],char tableB[HEIGHT][WIDTH])
 { 
   int height;
   int width;
   for(height=0; height<HEIGHT; height++)
    { for(width=0; width<WIDTH; width++)
       { int neighbor=0;                   // neighbor variable is used to calculate the number of live cells in surroundings.
         if( height==0 || width==0 || height==height-1 || width==width-1)
    {     tableA[height][width]=0;
    }
         else
     {    if (tableA[height - 1][width - 1] == 1) {
            neighbor++;
         }

         if (tableA[height - 1][width] == 1) {
            neighbor++;
         }

         if (tableA[height - 1][width + 1] == 1) {
            neighbor++;
         }

         if (tableA[height][width - 1] == 1) {
            neighbor++;
         }

         if (tableA[height][width + 1] == 1) {
            neighbor++;
         }
         if (tableA[height + 1][width - 1] == 1) {
            neighbor++;
         }
         if (tableA[height + 1][width] == 1) {
            neighbor++;
       }
         if (tableA[height + 1][width + 1] == 1) {
            neighbor++;
         }
         if (tableA[height][width] == 1 && neighbor < 2) {
            tableB[height][width] = 0;
         }
         else if (tableA[height][width] == 1 && neighbor > 3) {
            tableB[height][width] = 0;
         }
         else if (tableA[height][width] == 1 && (neighbor == 2 || neighbor == 3)) {
            tableB[height][width] = 1;
         }         else if (tableA[height][width] == 0 && neighbor == 3) {
            tableB[height][width] = 1;
         }
     }
  }
    }
}
  
/*Used to swap the current and next generation*/     
void swap(char tableA[HEIGHT][WIDTH],char tableB[HEIGHT][WIDTH])
 { int c;
   int height;
   int width;
   for(height=0; height<HEIGHT; height++)
    { for(width=0; width<WIDTH; width++)
        { c=tableA[height][width];
          tableA[height][width]=tableB[height][width];
          tableB[height][width]=tableA[height][width];
        }
    }
 } 
 
int main()
{  
   clrscr();
   char tableA[HEIGHT][WIDTH];
   char tableB[HEIGHT][WIDTH];
   int end;
   clearscreen(tableA, tableB);
   takeuser(tableA);
   printf("First Generation\n");
   display(tableA);
   end=1;
   
   while(end!=0)
 {  calculate(tableA,tableB);
    swap(tableA,tableB);
    printf("Next Generation\n");
    display(tableA);
    printf("Enter 0 to quit\nPress 1 to continue ");
    scanf("%d",&end);
 }
  return 0;
  getch();
}
