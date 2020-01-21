# C-Developer---NanoDegree
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


