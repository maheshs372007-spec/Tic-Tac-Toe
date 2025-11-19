# Tic-Tac-Toe
A simple Tic Tac Toe game created using C programming language
#include <stdio.h>

int main() {
    char ttt[9] = {' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '};
    char move = 'X';
    int pos;
    int winner = 0; 
    for (int i = 1; i <= 9; i++) {
        
        printf("Current board:\n");
        printf(" %c | %c | %c\n", ttt[0], ttt[1], ttt[2]);
        printf("---+---+---\n");
        printf(" %c | %c | %c\n", ttt[3], ttt[4], ttt[5]);
        printf("---+---+---\n");
        printf(" %c | %c | %c\n\n", ttt[6], ttt[7], ttt[8]);

        printf("Player %c, enter your move (1-9): ", move);
        scanf("%d", &pos);

       
        if (pos < 1 || pos > 9) {
            printf("Invalid position! Please enter a number between 1 and 9.\n");
            i--; 
            continue;
        }

        int idx = pos - 1; 

       
        if (ttt[idx] != ' ') {
            printf("That position is already taken! Try again.\n");
            i--; 
            continue;
        }

       
        ttt[idx] = move;

       
        if ((ttt[0] == 'X' && ttt[1] == 'X' && ttt[2] == 'X') ||
            (ttt[3] == 'X' && ttt[4] == 'X' && ttt[5] == 'X') ||
            (ttt[6] == 'X' && ttt[7] == 'X' && ttt[8] == 'X') ||
            (ttt[0] == 'X' && ttt[3] == 'X' && ttt[6] == 'X') ||
            (ttt[1] == 'X' && ttt[4] == 'X' && ttt[7] == 'X') ||
            (ttt[2] == 'X' && ttt[5] == 'X' && ttt[8] == 'X') ||
            (ttt[0] == 'X' && ttt[4] == 'X' && ttt[8] == 'X') ||
            (ttt[2] == 'X' && ttt[4] == 'X' && ttt[6] == 'X')) {
            winner = 1;
            break;
        }

       
        if ((ttt[0] == 'O' && ttt[1] == 'O' && ttt[2] == 'O') ||
            (ttt[3] == 'O' && ttt[4] == 'O' && ttt[5] == 'O') ||
            (ttt[6] == 'O' && ttt[7] == 'O' && ttt[8] == 'O') ||
            (ttt[0] == 'O' && ttt[3] == 'O' && ttt[6] == 'O') ||
            (ttt[1] == 'O' && ttt[4] == 'O' && ttt[7] == 'O') ||
            (ttt[2] == 'O' && ttt[5] == 'O' && ttt[8] == 'O') ||
            (ttt[0] == 'O' && ttt[4] == 'O' && ttt[8] == 'O') ||
            (ttt[2] == 'O' && ttt[4] == 'O' && ttt[6] == 'O')) {
            winner = 2;
            break;
        }

       
        if (move == 'X')
            move = 'O';
        else
            move = 'X';
    }

    
    printf("\nFinal board:\n");
    printf(" %c | %c | %c\n", ttt[0], ttt[1], ttt[2]);
    printf("---+---+---\n");
    printf(" %c | %c | %c\n", ttt[3], ttt[4], ttt[5]);
    printf("---+---+---\n");
    printf(" %c | %c | %c\n", ttt[6], ttt[7], ttt[8]);

   
    if (winner == 1)
        printf("\nX wins, Game Over\n");
    else if (winner == 2)
        printf("\nO wins, Game Over\n");
    else
        printf("\nIt's a draw!\n");

    return 0;
}
