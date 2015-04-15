# Pro.1.0
Sudoku


#include <iostream>
#include <stdlib.h>
#include <cstdlib>
#include <string>
#include <unistd.h> //Sleep
#include <vector>

using namespace std;

 int Sudoku(){
     int x, columna, numero;
     int f1 [10] = { 0, 0, 0, 0, 3, 9, 0, 0, 1, 0 };
     int f2 [10] = { 0, 5, 0, 1, 0, 0, 0, 0, 4, 0 };
     int f3 [10] = { 0, 9, 0, 0, 7, 0, 0, 5, 0, 0 };
     int f4 [10] = { 0, 6, 0, 2, 5, 3, 0, 0, 7, 0 };
     int f5 [10] = { 0, 0, 0, 0, 0, 7, 0, 0, 0, 8 };
     int f6 [10] = { 0, 7, 0, 0, 8, 0, 0, 9, 0, 3 };
     int f7 [10] = { 0, 8, 0, 3, 0, 1, 0, 0, 9, 0 };
     int f8 [10] = { 0, 1, 9, 0, 2, 0, 6, 0, 0, 7 };
     int f9 [10] = { 0, 4, 0, 0, 0, 0, 3, 0, 6, 1 };
     
     int f11 [10] = { 0, 2, 4, 8, 3, 9, 5, 7, 1, 6 };
     int f21 [10] = { 0, 5, 7, 1, 6, 2, 8, 3, 4, 9 };
     int f31 [10] = { 0, 9, 3, 6, 7, 4, 1, 5, 8, 2 };
     int f41 [10] = { 0, 6, 8, 2, 5, 3, 9, 1, 7, 4 };
     int f51 [10] = { 0, 3, 5, 9, 1, 7, 4, 6, 2, 8 };
     int f61 [10] = { 0, 7, 1, 4, 8, 6, 2, 9, 5, 3 };
     int f71 [10] = { 0, 8, 6, 3, 4, 1, 7, 2, 9, 5 };
     int f81 [10] = { 0, 1, 9, 5, 3, 8, 6, 4, 3, 7 };
     int f91 [10] = { 0, 4, 2, 7, 9, 5, 3, 8, 6, 1 };
     string done, ans;
     char fila;
 	system( "Color 01" );//ansi codes c++

 	do{

 	cout <<"  |  1  |  2  |  3  ||  4  |  5  |  6  ||  7  |  8  |  9  |  "<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"A |  "<<f1 [1]<<"  |  "<<f1 [2]<<"  |  "<<f1 [3]<<"  ||  3  |  9  |  "<<f1 [6]<<"  ||  "<<f1 [7]<<"  |  1  |  "<<f1 [9]<<"  | A"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"B |  5  |  "<<f2 [2]<<"  |  1  ||  "<<f2 [4]<<"  |  "<<f2 [5]<<"  |  "<<f2 [6]<<"  ||  "<<f2 [7]<<"  |  4  |  "<<f2 [9]<<"  | B"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
  	cout <<"C |  9  |  "<<f3 [2]<<"  |  "<<f3 [3]<<"  ||  7  |  "<<f3 [5]<<"  |  "<<f3 [6]<<"  ||  5  |  "<<f3 [8]<<"  |  "<<f3 [9]<<"  | C"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"D |  6  |  "<<f4 [2]<<"  |  2  ||  5  |  3  |  "<<f4 [6]<<"  ||  "<<f4 [7]<<"  |  7  |  "<<f4 [9]<<"  | D"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"E |  "<<f5 [1]<<"  |  "<<f5 [2]<<"  |  "<<f5 [3]<<"  ||  "<<f5 [4]<<"  |  7  |  "<<f5 [6]<<"  ||  "<<f5 [7]<<"  |  "<<f5 [8]<<"  |  8  | E"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"F |  7  |  "<<f6 [2]<<"  |  "<<f6 [2]<<"  ||  8  |  "<<f6 [5]<<"  |  "<<f6 [6]<<"  ||  9  |  "<<f6 [8]<<"  |  3  | F"<< endl;
  	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"G |  8  |  "<<f7 [2]<<"  |  3  ||  "<<f7 [4]<<"  |  1  |  "<<f7 [6]<<"  ||  "<<f7 [7]<<"  |  9  |  "<<f7 [9]<<"  | G"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"H |  "<<f8 [1]<<"  |  9  |  "<<f8 [3]<<"  ||  2  |  "<<f8 [5]<<"  |  6  ||  "<<f8 [7]<<"  |  "<<f8 [8]<<"  |  7  | H"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"I |  4  |  "<<f9 [2]<<"  |  "<<f9 [3]<<"  ||  "<<f9 [4]<<"  |  "<<f9 [5]<<"  |  3  ||  "<<f9 [7]<<"  |  6  |  1  | I"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"  |  1  |  2  |  3  ||  4  |  5  |  6  ||  7  |  8  |  9  |  "<< endl;

        cout << "Add a new number?" << endl;
 	cin >> ans;
 	if (ans == "yes" || ans == "YES" || ans == "Yes"){
 	cout << "Print yuor letter " << endl;
 	cin >> fila;
 	cout << "print the column number" << endl;
 	cin >> columna;
 	cout << "your number between 1 an 9" << endl;
 	cin >> numero;
        
        switch ( fila ){
        
            case('a'):
                f1 [columna] = numero;
                break;
                
            case('b'):
                f2 [columna] = numero;
                break;
                
            case('c'):
                f3 [columna] = numero;
                break;
                
            case('d'):
                f4 [columna] = numero;
                break;
                
            case('e'):
                f5 [columna] = numero;
                break;
                
            case('f'):
                f6 [columna] = numero;
                break;
                
            case('g'):
                f7 [columna] = numero;
                break;
                
            case('h'):
                f8 [columna] = numero;
                break;
                
            case('i'):
                f9 [columna] = numero;
                break;
                
            default:
                cout <<"You are to smart for this program, please try again"<< endl;
                break;
        
        }
        
 	done = "no";
    }
    
    else{
    done = "yes";
        if(f1 == f11 && f2 == f21 && f3 == f31 && f4 == f41 && f5 == f51 && f6 == f61 && f6 == f61 && f7 == f71 && f8 == f81){
            
            x = 1;
        }
        else{
            
            x = 0;
        }
        
        
        
    }
        
 	}while(done == "No" || done == "NO" || done == "no");

 	return x;
}

int Rules(){
	int x = 0;

	cout << "	The Basic Rules of Sudoku:" << endl;

	cout << "· There is only one valid solution to each Sudoku puzzle. The only way the puzzle can be considered solved correctly is when all 81 boxes contain numbers and the other Sudoku rules have been followed." << endl;

	cout << "· When you start a game of Sudoku, some blocks will be pre-filled for you. You cannot change these numbers in the course of the game." << endl;

	cout << "· Each column must contain all of the numbers 1 through 9 and no two numbers in the same column of a Sudoku puzzle can be the same." << endl;

	cout << "· Each row must contain all of the numbers 1 through 9 and no two numbers in the same row of a Sudoku puzzle can be the same." << endl;

	cout << "· Each block must contain all of the numbers 1 through 9 and no two numbers in the same block of a Sudoku puzzle can be the same. " << endl;
	cout << "Reference: http://www.sudokukingdom.com/rules.php" << endl;

	return 0;
}

int Give_up(){
	int x;

	cout <<"  |  1  |  2  |  3  ||  4  |  5  |  6  ||  7  |  8  |  9  |  "<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"A |  2* |  4* |  8* ||  3  |  9  |  5* ||  7* |  1  |  6* | A"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"B |  5  |  7* |  1  ||  6* |  2* |  8* ||  3* |  4  |  9* | B"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
  	cout <<"C |  9  |  3* |  6* ||  7  |  4* |  1* ||  5  |  8* |  2* | C"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"D |  6  |  8* |  2  ||  5  |  3  |  9* ||  1* |  7  |  4* | D"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"E |  3* |  5* |  9* ||  1* |  7  |  4* ||  6* |  2* |  8  | E"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"F |  7  |  1* |  4* ||  8  |  6* |  2* ||  9  |  5* |  3  | F"<< endl;
  	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"G |  8  |  6* |  3  ||  4* |  1  |  7* ||  2* |  9  |  5* | G"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"H |  1  |  9  |  5* ||  2  |  8* |  6  ||  4* |  3* |  7  | H"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"I |  4  |  2* |  7* ||  9* |  5* |  3  ||  8* |  6  |  1  | I"<< endl;
 	cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
 	cout <<"  |  1  |  2  |  3  ||  4  |  5  |  6  ||  7  |  8  |  9  |  "<< endl;

	return x;
}

int time(int x){
	int u = 5;

cout << "We are cheking your answers" << endl;

    for(int i = 0; i == u; i++){
        
sleep(5);
cout << " . ";

}

system("clear");
    if (x == 1){

cout << "Congratulations your awnsers are correct" << endl;
    }
    else{
        
        cout << "You got something wrong, please try again"<< endl;
    }
	return 0;
}

int main(){
	int ans, x = 0;
	string menu, end;

	do{

	cout <<"Welcome to the Soduku game"<< endl;
	cout << endl;
	cout << "1.- Game" << endl;
	cout << "2.- Check my work" << endl;
	cout << "3.- Give up" << endl;
	cout << "4.- Rules of the game" << endl;
	cout << "5.- Off" << endl;
	cout << endl;
	cout << "Type your number" << endl;
	cin >> ans;

	switch(ans){

		case(1):
		x = Sudoku();
		cout << "Back to the menu" << endl;
		//cin >> ;
		menu = "Si";
		break;

		case(2):
		time(x);
		break;

		case(3):
		Give_up();
		cout << "Back to the menu" << endl;
		//cin >> ;
		menu = "Si";
		break;

		case(4):
		Rules();
		cout << "Back to the menu" << endl;
		//cin >> ;
		menu = "Si";
		break;

		case(5):
		cout << "Finish the game" << endl;
		cin >> end;
		if(end == "si" || end == "yes" || end == "Yes"|| end == "YES" || end == "yea"){
			menu = "No";
		}
		else{
			menu = "si";
		}
		break;

		default:
		cout << "Your choice is not valid" << endl;
		menu = "Si";
		system( "clear" );
		cout << "Please try again" << endl;
		break;		
	}

}while(menu == "si" || menu == "Si" || menu == "SI");

	return 0;
}
