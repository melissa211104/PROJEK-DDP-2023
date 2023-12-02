# PROJEK-DDP-2023
Bismillah lancar jaya
maap blm semua kak masih mentah><

kode game=
#include <iostream>

using namespace std;

//declaration of methods implemented after the main method
void printBoard(char board[3][3]);
void makeMove(char (&board)[3][3], char move);
bool checkWin (char board[3][3], char player);
void clearBoard(char (&board)[3][3]);
bool full(char board[3][3]);

int main (){

  //the board is a two dimensional array
  char board[3][3];
  //local variables
  bool playing = true;
  bool game = true;
  int xwins = 0;
  int owins = 0;
  char ans[2];
  //loop for while running the game, once code exits this loop, the user is done playing the game, and the program stops
  while(playing){
    //setting up the initial clear board
    clearBoard(board);
    printBoard(board);
    //while in a single game
    while(game){
      //x can make a move first, then show it up
      makeMove(board,'X');
      printBoard(board);
      //check for x wins and ties, keep track of wins
      if(checkWin(board, 'X')){
	cout << "X won!" << endl;
	xwins++;
	break;
      }
      if(full(board)){
	cout << "Tie!" << endl;
	break;
      }
      //o makes a move next
      makeMove(board,'O');
      printBoard(board);
      //check for o wins and ties, keep track of wins
      if(checkWin(board, 'O')){
	  cout << "O won!" << endl;
	  owins++;
	  break;
	}
      if(full(board)){
	cout << "Tie!" << endl;
	break;
      }
      }
    //after a game, print out number of wins and ask if they want to play again
    cout << "X won " << xwins << " times and O won " << owins << " times. would you like to play again? type yes or no" << endl;
    cin >> ans;
    //check for n (no) and if they said no, exit the playing loop
    if(ans[0] == 'n' || ans[0] == 'N'){
      playing = false;
    }
  }
  return 0;

}
//method to check for a full board (tie)
bool full(char board[3][3]){
  //cycle through the whole array, and check for an empty square
  for(int a = 0; a < 3; a ++){
    for(int b = 0; b < 3; b++){
      if(board[a][b] == ' '){
	return false;
      }
    }
  }
  return true;
}
//clear the board
void clearBoard(char (&board)[3][3]){
  // set all the slots in the array to empty (space)
  board[0][0] = ' ';
  board[1][0] = ' ';
  board[2][0] = ' ';
  board[0][1] = ' ';
  board[1][1] = ' ';
  board[2][1] = ' ';
  board[0][2] = ' ';
  board[1][2] = ' ';
  board[2][2] = ' ';
}
//check for the win of a given player
  bool checkWin (char board[3][3], char player){
    //if any given sequence has 3 Xs or Os, it's a win 
  int count = 0;
  //vertical
  for(int a = 0; a < 3 ; a++){
    count = 0;
    for(int b = 0; b < 3; b++){
      if(board[a][b] == player){
	count++;
      }
    }
    if(count==3){
      return true;
    }
  }
  //horizontal
  for(int a = 0; a < 3 ; a++){
    count = 0;
    for(int b = 0; b < 3; b++){
      if(board[b][a] == player){
	count++;
      }
    }
    if(count==3){
      return true;
    }
  }
  //check for first diagonal
  if(board[0][0] == player){
    if(board[1][1] == player){
      if(board[2][2] ==  player){
	return true;
      }
    }
  }
  //check for second diagonal
  if(board[2][0] == player){
    if(board[1][1] == player){
      if(board[0][2] ==  player){
	return true;
      }
    }
  }
  return false;
}
//update the board to show the move, if it's valid
void makeMove (char (&board)[3][3], char move){

  char input[2];
  cout << "input a move (number followed by a letter)" << endl;
  cin >> input;
  //convert acii of a,b,c to 1,2,3
  int numletter = input[1]-64;
  //convert acii of 1,2,3 to 1,2,3
  int numnum = input[0]-48;
  int x;
  int y;
  //check for lowercase and uppercase to make sure user entered a, b, or c
  if(numletter == 1 || numletter == 33){
    y = 0;
  }
  else if(numletter == 2 || numletter == 34){
    y = 1;
  }
  else if(numletter == 3 || numletter == 35){
    y = 2;
  }
  //if it's not a,b, or c, tell the user, then let them enter a new value
  else{
    cout << "sorry, invalid move, bad letter" << endl;
    makeMove(board, move);
    return;
  }
  //check if the number isn't 1,2,or 3
  if(numnum > 3 || numnum < 1){
    //tell the user it's invalid, and let them enter a new value
    cout << "sorry, invalid move, bad num: " << numnum << endl;
    makeMove(board, move);
    return;
  }
  //make 1,2,3 to array indexes (0,1,2)
  x = numnum-1;
  //check if the space is empty, then fill it with 'X' or 'O'
  if(board[x][y] == ' '){
    board[x][y] = move;
  }
  //if it's not empty, have the user enter a new value
  else{
    cout << "sorry, invalid move, full" << endl;
    makeMove(board, move);
    return;
  }
  
}
//print out each element of the board
void printBoard(char board[3][3]){

  cout << "  1 2 3" << endl;
  cout << "a "<<board[0][0]<<" "<<board[1][0]<<" "<<board[2][0] << endl;
  cout << "b "<<board[0][1]<<" "<<board[1][1]<<" "<<board[2][1] << endl;
  cout << "c "<<board[0][2]<<" "<<board[1][2]<<" "<<board[2][2] <<endl;
}
