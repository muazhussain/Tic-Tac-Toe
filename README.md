# Tic-Tac-Toe
Tic-Tac-Toe is a pencil-and-paper game for two players, X and O, who take turns marking the spaces in a 3*3 grid. The player who succeeds in placing three respective marks in a horizontal, vertical or diagonal row wins the game.
This program is a game program, Tic-Tac-Toe. Most of us have played this game in our leisure time, and I have made a C++ program on it.
This program uses a board to control players in each turn players enter a number and choose a move. This program assumes that player one always moves first and uses X's. Player two moves at the second position and uses O's.

Program Structure:

The program consists of four steps:

* Get input of two players name
* Display board
* Get player move
* Cheak for game end
```cpp
//*******************//
/* Tic Tac Toe Game  */
//*******************//


#include<bits/stdc++.h>

using namespace std;

// Global variables //

char matrix [3][3] = {{'1', '2', '3'}, {'4', '5', '6'}, {'7', '8', '9'}}; 

string player1, player2;

// Global functions //

int cheak_win(); // Function for cheaking if any player have won

void draw_board(); // Function for drawing board

int main(){
    
    cout << "Player 1 Name: ";
    getline(cin, player1);
    
    cout << "Player 2 Name: ";
    getline(cin, player2);
    
    int player{1}, status{};
    string name;
    
    do{
        
        draw_board();
        
        player = (player % 2 == 0) ? 2 : 1;
        
        name = (player == 1) ? player1 : player2;
        
        char mark;
        mark = (player == 1) ? 'X' : 'O';
        
        cout << player1 << " (X) - " << player2 << " (O)" << endl;
        
        int choice{};
        cout << name << ", your turn. \nEnter position: ";
        cin >> choice;
        
        // Cheak for  valid input
        
        if(choice == 1 && matrix[0][0] == '1'){
        matrix[0][0] = mark;
        }
        else if(choice == 2 && matrix[0][1] == '2'){
            matrix[0][1] = mark;
        }
        else if(choice == 3 && matrix[0][2] == '3'){
            matrix[0][2] = mark;
        }
        else if(choice == 4 && matrix[1][0] == '4'){
            matrix[1][0] = mark;
        }
        else if(choice == 5 && matrix[1][1] == '5'){
            matrix[1][1] = mark;
        }
        else if(choice == 6 && matrix[1][2] == '6'){
            matrix[1][2] = mark;
        }
        else if(choice == 7 && matrix[2][0] == '7'){
            matrix[2][0] = mark;
        }
        else if(choice == 8 && matrix[2][1] == '8'){
            matrix[2][1] = mark;
        }
        else if(choice == 9 && matrix[2][2] == '9'){
            matrix[2][2] = mark;
        }
        else{
            cout << "Invalid move!" << endl;
            player--;
            cin.ignore();
            cin.get();
        }
    status = cheak_win();
    
    player++;
    }while(status == -1);
    
    draw_board();
    
    if(status == 1){
        cout << name << " win!" << endl;
    }
    else{
        cout << "No result!" << endl;
    }
    
    return 0;
}

int cheak_win(){
    
    if(matrix[0][0] == matrix[0][1] && matrix[0][1] == matrix[0][2]){
        return 1;
    }
    else if(matrix[1][0] == matrix[1][1] && matrix[1][1] == matrix[1][2]){
        return 1;
    }
    else if(matrix[2][0] == matrix[2][1] && matrix[2][1] == matrix[2][2]){
        return 1;
    }
    else if(matrix[0][0] == matrix[1][0] && matrix[1][0] == matrix[2][0]){
        return 1;
    }
    else if(matrix[0][1] == matrix[1][1] && matrix[1][1] == matrix[2][1]){
        return 1;
    }
    else if(matrix[0][2] == matrix[1][2] && matrix[1][2] == matrix[2][2]){
        return 1;
    }
    else if(matrix[0][0] == matrix[1][1] && matrix[1][1] == matrix[2][2]){
        return 1;
    }
    else if(matrix[0][2] == matrix[1][1] && matrix[1][1] == matrix[2][0]){
        return 1;
    }
    else if (matrix[0][0] != '1' && matrix[0][1] != '2' && matrix[0][2] != '3' 
            && matrix[1][0] != '4' && matrix[1][1] != '5' && matrix[1][2] != '6'
            && matrix[2][0] != '7' && matrix[2][1] != '8' && matrix[2][2] != '9'){
        return 0;
    }
    else{
        return -1;
    }
}

void draw_board(){
    
    cout << "     |     |     " << endl;
	cout << "  " << matrix[0][0] << "  |  " << matrix[0][1] << "  |  " << matrix[0][2] << endl;

	cout << "_____|_____|_____" << endl;
	cout << "     |     |     " << endl;

	cout << "  " << matrix[1][0] << "  |  " << matrix[1][1] << "  |  " << matrix[1][2] << endl;

	cout << "_____|_____|_____" << endl;
	cout << "     |     |     " << endl;

	cout << "  " << matrix[2][0] << "  |  " << matrix[2][1] << "  |  " << matrix[2][2] << endl;

	cout << "     |     |     " << endl << endl;
}



```
