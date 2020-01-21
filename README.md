# C-Developer---NanoDegree
# Introduction to C++ language
Learning to be a C++ Developer from Udacity Nano-degree


## First Code in C++ 

```
# include <iostream>
using std::cout; 

int main() {
    cout << "Hello World"<<"\n";
}
```

1. The **# include** is a preprocessed command which is executed before the code is complied. 
2. The **iostream** containts declerations of input/output objects.
3. The **using std::** containts all the standard librabries used in  C++ 
4. The **cout** is the command given to output on the user screen. 

## Sending Output to the Console 

1. **g++ [name of the file.cpp] **
2. **./a.out **

## Variable Types 

```
# include <iostream>
# include <string>
using std::cout; 
using std::string;

int main() {
    int a = 10;
    string b = "C++ is awesome";
    cout << a << "\n";
    cout << b << "\n";
}
```
## Vector - Most Common data Structure in C++ 
### 1-D Vector 
```
# include <iostream>
# include <string>
# include <vector> 
using std::cout; 
using std::string;
using std::vector;

int main() {
    vector <int> v1 = {1,2,3};
    for(int i:v1){
       cout <<  i <<",";
    }
    
}
```
### 2-D Vector 
```

# include <iostream>
# include <string>
# include <vector> 
using std::cout; 
using std::string;
using std::vector;

int main() {
    vector<vector<int>> v1 = {{1,2,3},{3,4,5}};
    for(auto i:v1){
        for(auto j:i){
       cout <<  j ;
    }
  }
}
```
## Store a Grid in your Program 
```
#include <iostream>
#include <vector>
using std::cout;
using std::vector;


int main() {
  vector<vector<int>> board {{0, 1, 0, 0, 0, 0},
{0, 1, 0, 0, 0, 0},
{0, 1, 0, 0, 0, 0},
{0, 1, 0, 0, 0, 0},
{0, 0, 0, 0, 1, 0}};
  
  cout << "Hello!" << "\n";
}
```
## For Loops 
```
#include <iostream>
#include <vector>
using std::cout;
using std::vector;


int main() {
  for(int i = 0; i<= 10; i++){
      cout << i << "\n";
  }
  
  
}
```
```
#include <iostream>
#include <vector>
using std::cout;
using std::vector;


int main() {
  for(int i = -3; i<= 10; i++){
      cout << i << "\n";
  }
  
  
}
```
## Functions 
```
#include <iostream>
using std::cout;

int AddFun(int i, int j){
    return i+j; 
}

int main() {
    int a = 10; 
    int b = 20; 
    
   cout << AddFun(a,b);
}
```
```
#include <iostream>
#include <vector>
using std::cout;
using std::vector;

int AddFun(vector<int> v1){
    int sum = 0;
    for(auto i:v1){
        sum = sum + i;
        
    }
    return sum;
}

int main() {
    
    vector<int> v1 = {10,20,30};
    
   cout << AddFun(v1);
}

```
## Print the Board 
```
#include <iostream>
#include <vector>
using std::cout;
using std::vector;

void PrintBoard(vector<vector<int>> board){
    for(int i = 0;i<board.size();i++){
        for(int j = 0;j<board[i].size();j++){
            cout<<board[i][j];
        }
        cout <<"\n";
    }
}

int main(){
     vector<vector<int>> board{{0, 1, 0, 0, 0, 0},
                            {0, 1, 0, 0, 0, 0},
                            {0, 1, 0, 0, 0, 0},
                            {0, 1, 0, 0, 0, 0},
                            {0, 0, 0, 0, 1, 0}};
    PrintBoard(board);
}
```
## If Statement 
```
#include <iostream>
#include <vector>

using std::cout;
using std::vector;

int main(){
    int a = 10; 
    if(a>5){
        cout <<"a is Greater than 5"<<"\n";
    }else{
        cout <<"a is not Greater than 5"<<"\n";
    }
}
```
 ## While Loop 
 ```
 #include <iostream>
#include <vector>

using std::cout;
using std::vector;

int main(){
    auto i =0;
    while (i<5){
        cout<<i<<"\n";
        i++;
    }
}
```
## Practice - While Loop and If Statement 
In the following code cell, you will combine a while loop with an if statement to print every other number. Write a while loop to iterate over the integers from 1 to 10. If the integer is even, print it out.

Hint: you can tell if an integer is even by looking at its remainder after dividing by two. In C++, the remainder operator is %. In other words, for a given int i, you have remainder = i % 2. If remainder equals 0, the number is even.
```
#include <iostream>
using std::cout; 

int main(){
    auto i = 0; 
    while (i<=10){
        if(i%2==0){
            cout<<i<<"\n";
        }
        i++;
        
    }
}
```
## Reading a File 
```
#include <iostream>
#include <fstream>
#include <string>
using std::cout; 
using std::ifstream;
using std::string;

int main(){
    ifstream my_file;
  my_file.open("files/1.board");
    if (my_file) {
      cout << "The file stream has been created!" << "\n";
    }    
}
```
## Read the Board from a File 
```
void ReadBoardFile(string filepath){
  ifstream board_file;
  board_file.open(path);
  if(board_file){
    cout<<"works"<<"\n";
    string line;
    while(getline(board_file,line)){
      cout<<line<<"\n";
    }
  }
}
```
## Processing string - istringstream 

```
#include <iostream>
#include <fstream>
#include <string>
#include <vector> 
#include <sstream>
using std::cout; 
using std::ifstream;
using std::string;
using std::vector;
using std::istringstream;

int main(){
    string a = "123 3 454"; 
    istringstream myfile(a);
    int n;
    myfile>>n;
    cout<<n<<"\n";
}
```
```
#include <iostream>
#include <fstream>
#include <string>
#include <vector> 
#include <sstream>
using std::cout; 
using std::ifstream;
using std::string;
using std::vector;
using std::istringstream;

int main(){
    string a = "123 3 454"; 
    istringstream myfile(a);
    int n;
    while(myfile){
        myfile >>n;
        if(myfile){
            cout<<"Was successful:"<<n<<"\n";
        }else{
            break;
        }
    }
}

```
#include <iostream>
#include <fstream>
#include <string>
#include <vector> 
#include <sstream>
using std::cout; 
using std::ifstream;
using std::string;
using std::vector;
using std::istringstream;

int main(){
    string a = "123 3 454"; 
    istringstream myfile(a);
    int n;
    while(myfile >>n){
        if(myfile){
            cout<<"Was successful:"<<n<<"\n";
        }else{
            break;
        }
    }
}
```
#include <iostream>
#include <fstream>
#include <string>
#include <vector> 
#include <sstream>
using std::cout; 
using std::ifstream;
using std::string;
using std::vector;
using std::istringstream;

int main(){
    string a = "123, 3, 454"; 
    istringstream myfile(a);
    int n;
    char j;
    while(myfile >>n>>j){
        if(myfile){
            cout<<"Was successful:"<<n<<j<<"\n";
        }else{
            break;
        }
    
    }
}
```
## Adding Data into String
```
#include <iostream>
#include <fstream>
#include <string>
#include <vector> 
#include <sstream>
using std::cout; 
using std::ifstream;
using std::string;
using std::vector;
using std::istringstream;

int main(){
    vector<int> v = {1,2,3}; 
    for(int i =0;i<v.size();i++){
        
    }
    v.push_back(4);
    for(int i =0;i<v.size();i++){
        cout<<v[i];
    }
}
```
## Code:
Write a vector<int> ParseLine function which accepts a string as an argument. Use std::istringstream to parse the line by comma chars, and store the ints in a vector<int>. ParseLine should return the vector after parsing.
```
#include <fstream>
#include <iostream>
#include <string>
#include <vector>
#include <sstream>
using std::cout;
using std::ifstream;
using std::string;
using std::vector;
using std::istrngstream;

vector<int> ParseLine(string line){
  istringstream mystring(line);
  int n;
  char j;
  vector<int> row;
  while(mystring >>n>>j && j ==","){
    row.push_back(n);
  }
  return row;
}
```

## Code : 
Update ReadBoardFile to use ParseLine and return the board as a vector<vector<int>>. You can read the TODO comments in the code for step by step instructions.
Update the main function to pass the results of ReadBoardFile to the PrintBoard function.
```
#include <fstream>
#include <iostream>
#include <string>
#include <sstream>
#include <vector>
using std::cout;
using std::ifstream;
using std::istringstream;
using std::string;
using std::vector;


vector<int> ParseLine(string line) {
    istringstream sline(line);
    int n;
    char c;
    vector<int> row;
    while (sline >> n >> c && c == ',') {
      row.push_back(n);
    }
    return row;
}

// TODO: Change the return type of ReadBoardFile.
vector<vector<int>> ReadBoardFile(string path) {
  ifstream myfile (path);
  vector<vector<int>> v = {};
  // TODO: Declare an empty board variable here with
  // type vector<vector<int>>.
  if (myfile) {
    string line;
    while (getline(myfile, line)) {
      // TODO: Replace the "cout" code with a call to ParseLine for each line and push the results of ParseLine to the back of the board.
      vector<int> row = ParseLine(line);
      v.push_back(row);
    }
  }
  // TODO: Return the board variable.
  return v;
}

void PrintBoard(const vector<vector<int>> board) {
  for (int i = 0; i < board.size(); i++) {
    for (int j = 0; j < board[i].size(); j++) {
      cout << board[i][j];
    }
    cout << "\n";
  }
}

int main() {
   
  // TODO: Store the output of ReadBoardFile in the "board" variable.
  auto board = ReadBoardFile("1.board");
  // TODO: Uncomment PrintBoard below to print "board".
   PrintBoard(board);
}


## Code:
Write a function CellString which accepts aState as input and returns the following string:
"⛰️ " if the input equals a kObstacle
"0 " otherwise.
```
#include <fstream>
#include <iostream>
#include <sstream>
#include <string>
#include <vector>
using std::cout;
using std::ifstream;
using std::istringstream;
using std::string;
using std::vector;

enum class State {kEmpty, kObstacle};

vector<int> ParseLine(string line) {
    istringstream sline(line);
    int n;
    char c;
    vector<int> row;
    while (sline >> n >> c && c == ',') {
      row.push_back(n);
    }
    return row;
}

vector<vector<int>> ReadBoardFile(string path) {
  ifstream myfile (path);
  vector<vector<int>> board{};
  if (myfile) {
    string line;
    while (getline(myfile, line)) {
      vector<int> row = ParseLine(line);
      board.push_back(row);
    }
  }
  return board;
}

// TODO: Create the CellString function here,
// using the following return strings:
// "⛰️   "
// "0   "

string CellString(State cell){
  switch (cell){
      case State::kObstacle: return "⛰️   ";
    default: return "0   "; 
  }
}
      

void PrintBoard(const vector<vector<int>> board) {
  for (int i = 0; i < board.size(); i++) {
    for (int j = 0; j < board[i].size(); j++) {
      cout << board[i][j];
    }
    cout << "\n";
  }
}

int main() {
  auto board = ReadBoardFile("1.board");
  PrintBoard(board);
}
```
## Code: 
Follow the TODO comments in the main file below, and update the program to store a board of State variables. When you are done, the board should print as in the image above. Note that you will need to call CellString on each object in the board before printing: CellString(board[i][j]).
```
#include <fstream>
#include <iostream>
#include <sstream>
#include <string>
#include <vector>
using std::cout;
using std::ifstream;
using std::istringstream;
using std::string;
using std::vector;

enum class State {kEmpty, kObstacle};

// TODO: Change the return type to use auto or
// explicitly indicate vector<State>

vector<State> ParseLine(string line) {
    istringstream sline(line);
    int n;
    char c;
    // TODO: Change the variable type for row
    // to be a vector<State>
    vector<State> row;
    while (sline >> n >> c && c == ',') {
      // TODO: Modify the line below to push_back
      // a State::kEmpty if n is 0, and push_back
      // a State::kObstacle otherwise.
      if(n==0){
        row.push_back(State::kEmpty);
        }
      else{
        row.push_back(State::kObstacle);
      }
     
    }
    return row;
}

// TODO: Modify the return type here as well. Just
// as above, the board will contain State objects
// instead of ints.
vector<vector<State>> ReadBoardFile(string path) {
  ifstream myfile (path);
  // TODO: Modify the board declarationto store 
  // State objects instead of ints.
  vector<vector<State>> board{};
  if (myfile) {
    string line;
    while (getline(myfile, line)) {
      // TODO: Modify the row type to use State
      // objects instead of ints.
      vector<State> row = ParseLine(line);
      board.push_back(row);
    }
  }
  return board;
}

// TODO: Modify the function signature below to accept
// cells with State type instead of int type.
string CellString(State cell) {
  switch(cell) {
    case State::kObstacle: return "⛰️   ";
    default: return "0   "; 
  }
}

void PrintBoard(const vector<vector<State>> board) {
  for (int i = 0; i < board.size(); i++) {
    for (int j = 0; j < board[i].size(); j++) {
      // TODO: Modify the line below to call CellString
      // on each element of the board before streaming to cout.
      cout <<CellString(board[i][j]);
    }
    cout << "\n";
  }
}

int main() {
  auto board = ReadBoardFile("1.board");
  PrintBoard(board);
}
```


