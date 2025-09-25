# Ex2 Conversion of the infix expression into postfix expression
## DATE:
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Start the program.
2. Define the push() and pop() functions to add and remove elements from the stack.
3. Define the priority() function to assign priorities to operators.
4. Traverse the expression in the IntoPost() function, handling operands, parentheses, and operators.
5.  After processing the expression, pop and print any remaining operators from the stack. 6.End the program. 

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: MADESWARAN M
RegisterNumber:  212223040106
*/
#include<stdio.h> 
#include<ctype.h> 
 
char stack[100]; 
int top = -1; 
void push(char x) 
{ 
stack[++top]=x; 
 
} 
 
char pop() 
{ 
if(top==-1) 
return 0; 
else 
return stack[top--]; 
} 
int priority(char x) 
{ 
if(x=='(') 
  
  
{ 
return 0; 
} 
if(x=='&'||x=='|') 
{ 
return 1; 
} 
if(x=='+'||x=='-') 
{ 
return 2; 
} 
if(x=='*'||x=='/'||x=='%') 
{ 
return 3; 
} 
if(x=='^') 
{ 
return 4; 
} 
return 0; 
} 
char IntoPost(char *exp) 
{ 
char *e,x; 
e=exp; 
while(*e!='\0') 
{ 
if(isalnum(*e)) 
{ 
printf("%c ",*e); 
} 
else if(*e=='(') 
{ 
push(*e); 
} 
else if(*e==')') 
{ 
while((x=pop())!='(') 
printf("%c ",x); 
} 
else 
{ 
while(priority(stack[top])>=priority(*e)) 
printf("%c ",pop()); 
push(*e); 
} 
e++; 
} 
while(top != -1) 
{ 
printf("%c ",pop()); 
}return 0; 
} 
int main() 
{ 
char exp[100]="3%2+4*(A&B)"; 
IntoPost(exp); 
return 1; 
}

```

## Output:

<img width="560" height="184" alt="437888976-46e7f45d-c6ce-4751-a244-b824692e49e3" src="https://github.com/user-attachments/assets/3eab23bd-d091-4952-82b8-5a8132a01f94" />


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
