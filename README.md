# Ex. No : 1	
# IMPLEMENTATION OF SYMBOL TABLE 

## Register Number : 212222040046
## Date : 13/09/2024

## AIM   
To write a C program to implement a symbol table.
@@ -17,9 +17,72 @@ To write a C program to implement a symbol table.
 
## PROGRAM
    #include <stdio.h>
    #include <ctype.h>
    #include <string.h>
    #include <stdlib.h> 
    #define MAX_EXPRESSION_SIZE 100

    int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    void *add[5];
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0'; 
    n = i - 1;  

    printf("Given Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\taddr\ttype\n");

    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) {
            if (j == n || b[j + 1] == '+' || b[j + 1] == '-' || b[j + 1] == '*' || b[j + 1] == '=') {
                void *p = malloc(sizeof(char));
                if (p == NULL) {
                    printf("Memory allocation failed\n");
                    return 1;
                }
                add[x] = p;
                d[x] = c;
                printf("%c\t%p\tidentifier\n", c, p);
                x++;
            }
        }
    }

    printf("\nThe symbol to be searched: ");
    getchar(); 
    srch = getchar();

    for (i = 0; i < x; i++) { 
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("%c@address %p\n", srch, add[i]);
            flag = 1;
            break; 
        }
    }

    if (flag == 0)
        printf("Symbol Not Found\n");

    for (i = 0; i < x; i++) { 
        free(add[i]);
    }

    return 0;
    }

## OUTPUT 
    ![Screenshot 2024-09-13 194619](https://github.com/user-attachments/assets/31c195e9-6d90-4596-a391-d4bc206d148f)

## RESULT
The program to implement a symbol table is executed and the output is verified.

