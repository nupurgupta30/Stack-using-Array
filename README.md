# Stack-using-Array
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
#define max 10
struct stack
{int data[10];
int first, top;
}s;
void push()
{char ch='y';
do
{if( s.top == max-1 )
{printf("\nSTACK Overflow!!");
break;
}
else
{s.top++;
printf("\nEnter data :");
scanf("%d",&s.data[s.top]);
printf("Done");
}
printf("\tAdd More?? Y or N:");
ch=getch();
printf("%c",ch);
}while(ch=='y' || ch=='Y');
}

void pop()
{char ch = 'y';
do
{
if(s.first>s.top)
{printf("\nSTACK Underflow!!");
break;
}
else
{printf("\nItem Deleted : %d",s.data[s.top]);
s.top--;
}
printf("\tDelete More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch == 'y'||ch == 'Y');
}
void display()
{if(s.first>s.top)
printf("Empty STACK");
else
{printf("\nfirst->");
for(int i=s.first;i<=s.top;i++)
{printf("%d ",s.data[i]);
}
printf("<-top\n");
}
}

int main()
{s.first=0; s.top=-1;
int c,size,i,x=1;
do
{printf("\n------------------------------------------------------------\n");
printf("1.PUSH Value   \t2.POP Value    \t3.Display Stack\n4.Exit");
printf("\n\t\tEnter Choice :");
scanf("%d",&c);
printf("\n----------------------------------------------------------");
switch(c)
{case 1: {push(); break; }
case 2: {pop(); break; }
case 3: {display(); break; }
case 4: {x=0;break;exit(0);    }
default:{printf("\n\n\t\tError!!!!!"); break;}
}
}while(x);
return 0;
}
