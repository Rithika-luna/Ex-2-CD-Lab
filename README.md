# Ex-2-GENERATION OF LEXICAL TOKENS LEX FLEX TOOL
# AIM
## To write a lex program to implement lexical analyzer to recognize a few patterns.
# ALGORITHM

1.	Start the program.

2.	Lex program consists of three parts.

     a.	Declaration %%

     b.	Translation rules %%

     c.	Auxilary procedure.

3.	The declaration section includes declaration of variables, maintest, constants and regular definitions.
4.	Translation rule of lex program are statements of the form

    a.	P1 {action}

    b.	P2 {action}

    c.	…

    d.	…

    e.	Pn {action}

5.	Write a program in the vi editor and save it with .l extension.

6.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l $ cc lex.yy.c
7.	Compile that file with C compiler and verify the output.

# INPUT
```

int a = 10;
float b = 20;

```
# PROGRAM
```

%{
#include <stdio.h>
%}

%%
int|float|char|if|else|return    { printf("Keyword: %s\n", yytext); }
[a-zA-Z_][a-zA-Z0-9_]*          { printf("Identifier: %s\n", yytext); }
[0-9]+                          { printf("Number: %s\n", yytext); }
[+\-*/=<>]                      { printf("Operator: %s\n", yytext); }
[(){};,]                        { printf("Special Symbol: %s\n", yytext); }
[ \t\n]+                        ;
.                               { printf("Unknown: %s\n", yytext); }
%%

int main()
{
    printf("Enter the input:\n");
    yylex();
    return 0;
}

int yywrap()
{
    return 1;
}

```

# OUTPUT

<img width="1917" height="1063" alt="image" src="https://github.com/user-attachments/assets/af68be4e-7b39-4b77-b9ea-eacfcacd872a" />


# RESULT
## The lexical analyzer is implemented using lex and the output is verified.
