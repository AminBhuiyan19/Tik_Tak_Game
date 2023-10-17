#include <stdio.h>

char value_box[10] = {'0', '1', '2', '3', '4', '5', '6', '7', '8', '9'};
int check_winner();
void main_board();

int main() {
    int player = 1, i, choice;
    char mark;

    do {
        main_board();
        player = (player % 2) ? 1 : 2;
        printf("Player %d, Enter your choice: ", player);
        mark = (player == 1) ? 'X' : 'O';
        scanf("%d", &choice);
        if(choice==1&&value_box[1]=='1'){
           value_box[1]=mark;
        }
        else if(choice==2&&value_box[2]=='2'){
           value_box[2]=mark;
        }
        else if(choice==3&&value_box[3]=='3'){
        value_box[3]=mark;
        }
        else if(choice==4&&value_box[4]=='4'){
            value_box[4]=mark;
        }
        else if(choice==5&&value_box[5]=='5'){
            value_box[5]=mark;
        }
        else if(choice==6&&value_box[6]=='6'){
           value_box[6]=mark;
        }
        else if(choice==7&&value_box[7]=='7'){
            value_box[7]=mark;
        }
        else if(choice==8&&value_box[8]=='8'){
            value_box[8]=mark;
        }
        else if(choice==9&&value_box[9]=='9'){
            value_box[9]=mark;
        }
        else{
            printf("Invalid Option!");
            player--;
            getch();
        }

        i = check_winner();
        player++;
    } while (i == -1);

    main_board();

    if (i == 1) {
        printf("==>Player %d is the Winner!!", --player);
    } else {
        printf("==>GAME OVER!");
    }

    return 0;
}

int check_winner() {
    if (value_box[1] == value_box[2] && value_box[2] == value_box[3])
        return 1;
    else if (value_box[4] == value_box[5] && value_box[5] == value_box[6])
        return 1;
    else if (value_box[7] == value_box[8] && value_box[8] == value_box[9])
        return 1;
    else if (value_box[1] == value_box[4] && value_box[4] == value_box[7])
        return 1;
    else if (value_box[2] == value_box[5] && value_box[5] == value_box[8])
        return 1;
    else if (value_box[3] == value_box[6] && value_box[6] == value_box[9])
        return 1;
    else if (value_box[3] == value_box[5] && value_box[5] == value_box[7])
        return 1;
    else if (value_box[1] == value_box[5] && value_box[5] == value_box[9])
        return 1;
    else if (value_box[1] != '1' && value_box[2] != '2' && value_box[3] != '3' && value_box[4] != '4' &&value_box[5] != '5' && value_box[6] != '6' && value_box[7] != '7' && value_box[8] != '8' && value_box[9] != '9')
        return 0;
    else
        return -1;
}

void main_board() {
    system("cls");
    printf("\n\n\t========TIC TAC TOE=========\n\n");
    printf("PLAYER-1(X)  Vs   PLAYER-2(O)\n\n\n");
    printf("     |     |     \n");
    printf("  %c  |  %c  |  %c  \n", value_box[1], value_box[2], value_box[3]);
    printf("_____|_____|_____\n");
    printf("     |     |     \n");
    printf("  %c  |  %c  |  %c  \n", value_box[4], value_box[5], value_box[6]);
    printf("_____|_____|_____\n");
    printf("     |     |     \n");
    printf("  %c  |  %c  |  %c  \n", value_box[7], value_box[8], value_box[9]);
    printf("     |     |     \n");
}

