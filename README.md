# Snake-Game
Re-creation of the age old, simple &amp; fun snake game :)
(Command-line based)

[Snake Game.zip](https://github.com/decapacitator/Snake-Game/files/8633276/Snake.Game.zip)

/*

#include <iostream>
#include <conio.h>
#include <windows.h>
using namespace std;

bool gameOver;
const int width = 20;
const int height = 20;
int x, y, fruitX, fruitY, score;
enum eDirection {STOP=0 , LEFT , RIGHT , UP , DOWN};
eDirection dir;
int tailX[100], tailY[100];
int nTail;

void Setup()
{
    gameOver = false;
    dir = STOP;
    x = width / 2;
    y = height / 2;
    fruitX = rand() % width;
    fruitY = rand() % height;
    score = 0;
}
void Draw()
{
    system("cls");
    //Starting border (top wall)
    for(int i = 0; i < width+2; i++)
        cout<<"#";
    cout<<endl;
    //Printing the map
    for(int i = 0; i < height; i++)
    {
        for(int j = 0; j < width+2; j++)
        {
            if(j==0)
                cout<<"#";
            //snake head
            if( i == y && j == x)
                cout<<"O";
            //fruit
            else if(i == fruitY && j == fruitX)
                cout << "F";
            else
            {
                bool print = false;
                for (int k = 0; k < nTail; k++)
                {
                    if(tailX[k] == j && tailY[k] == i)
                    {
                        cout<<"o";
                        print = true;
                    }  
                }
                if(!print)
                    cout<<" ";   
            }
            if(j==width-1)
                cout<<"#";
        }
        cout<<endl;
    }
    //Lower border (bottom wall)
    for( int i = 0; i < width+2 ; i++)
        cout<<"#";
    cout<<endl;
    cout<< "Score: "<< score << endl;
}
void Input()
{
    //if any key pressed
    if( _kbhit())
    {
        //take input
        switch (_getch())
        {
        case 'a':
            dir = LEFT ;
            break;
        case 'd':
            dir = RIGHT ;
            break;
        case 'w':
            dir = UP ;
            break;
        case 's':
            dir = DOWN ;
            break;
        case 'x':
             gameOver = true ;
        default:
            break;
        }
    }
}
void Logic()
{
    int prevX = tailX[0];
    int prevY = tailY[0];
    int prev2X, prev2Y;
    tailX[0] = x;
    tailY[0] = y;
    for(int i = 1; i< nTail; i++)
    {
        prev2X = tailX[i];
        prev2Y = tailY[i];
        tailX[i] = prevX;
        tailY[i] = prevY;
        prevX = prev2X;
        prevY = prev2X;
    }
    switch (dir)
    {
    case LEFT:
        x--;
        break;
    case RIGHT:
        x++;
        break;
    case UP:
        y--;
        break;
    case DOWN:
        y++;
        break;
    default:
        break;
    }
    //CAN ENABLE EITHER 1 OR 2
//1  //if border touched or -ve values                     //          <----- can choose this too
     //game over
  
    /*
    if( x > width || x < 0 || y > height || y < 0 )
        gameOver = true ;
        */
                                                 
//2  //if border crossed, would enter                      //           <---- enabled now 
     //box from other side
    if(x >= width) x=0; else if(x < 0) x = width-1;
    if(y >= height) y=0; else if(y < 0) y = height-1;
    //increase tail length 
    //everytime fruit coordinates matched
    for(int i = 0; i< nTail; i++)
    if( tailX[i]==x && tailY[i]==y )
        gameOver = true;
    if( x==fruitX && y==fruitY)
    {
        score += 10;
        fruitX = rand() % width ;
        fruitY = rand() % height ;
        nTail++;
    }
}
int main()
{
    Setup();
    while(!gameOver)
    {
        Draw();
        Input();
        Logic();
        Sleep(40); //sleep (windows.h library function)
    }
    return 0;
}
    
*/
