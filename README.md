#include<stdio.h>
#include<stdlib.h>
#include<stdbool.h>
void main(){

    char tempLine[100] , location[200] ;
    FILE *fpoint ;

    if( (fpoint = fopen( "SampleCode.txt" , "r" ) ) == NULL ){
        printf("ERROR! opening file");
        exit(0);
    }

    int i , line = 0 , len ;

    char keywords[][10] = {
    "auto", "break", "case", "char", "continue", "do", "default", "const",
    "double", "else", "enum", "extern", "for", "if", "goto", "float", "int",
    "long", "register", "return", "signed", "static", "sizeof", "short",
    "struct", "switch", "typedef", "union", "void", "while", "volatile", "unsigned"};

    char Operator[][2] = {
        "+", "-", "*", "/", "%","="
    };
    char Relational[][3] = {
        "==", ">", "<", "!=", "<=", ">="
    };

    char Other[][2] = { "{", ")" , "(" , "}" , "[" , "]" };


    len = (int)sizeof(keywords)/sizeof(keywords[0]);
    printf("\nKeywords: ");
    while(1){
        fgets( tempLine , sizeof(tempLine) , fpoint );
        for( i = 0 ; i < len ; i++ ){
            if( strstr( tempLine , keywords[i] ) ){
                printf("%s, " , keywords[i] );
                break;
            }
        }

        if( feof(fpoint) ){
            break ;
        }
    }

    printf("\n");
    fclose(fpoint);

    if( (fpoint = fopen( "SampleCode.txt" , "r" ) ) == NULL ){
        printf("ERROR! opening file");
        exit(0);
    }

    len = (int)sizeof(Operator)/sizeof(Operator[0]);
    printf("\nOperator: ");
    while(1){
        fgets( tempLine , sizeof(tempLine) , fpoint );
        for( i = 0 ; i < len ; i++ ){
            if( strstr( tempLine , Operator[i] ) ){
                printf("%s, " , Operator[i] );
                break;
            }
        }
        if( feof(fpoint) ){
            break ;
        }
    }

    printf("\n");
    fclose(fpoint);

    if( (fpoint = fopen( "SampleCode.txt" , "r" ) ) == NULL ){
        printf("ERROR! opening file");
        exit(0);
    }

    len = (int)sizeof(Operator)/sizeof(Operator[0]);
    printf("\nRelational: ");
    while(1){
        fgets( tempLine , sizeof(tempLine) , fpoint );
        for( i = 0 ; i < len ; i++ ){
            if( strstr( tempLine , Relational[i] ) ){
                printf("%s, " , Relational[i] );
                break;
            }
        }
        if( feof(fpoint) ){
            break ;
        }
    }

    printf("\n");
    fclose(fpoint);

    if( (fpoint = fopen( "SampleCode.txt" , "r" ) ) == NULL ){
        printf("ERROR! opening file");
        exit(0);
    }

    len = (int)sizeof(Other)/sizeof(Other[0]);
    printf("\nOthers: ");
    while(1){
        fgets( tempLine , sizeof(tempLine) , fpoint );
        for( i = 0 ; i < len ; i++ ){
            if( strstr( tempLine , Other[i] ) ){
                printf("%s, " , Other[i] );
                break;
            }
        }
        if( feof(fpoint) ){
            break ;
        }
    }

    printf("\n");
    return 0 ;
}
