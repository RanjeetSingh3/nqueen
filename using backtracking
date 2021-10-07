#include<iostream>
#include<bits/stdc++.h>
#define N 4

using namespace std;
//printing 4*4 matrix
void printsolution(int board[N][N])
{
    for (int i = 0; i < N; i++)
    {
        for (int j = 0; j < N; j++)
        {
            std::cout << board[i][j] ;
        }
            std::cout << "\n" ;
    }
        std::cout << "\n" ;
}
//-------------------------------------------------------
//checking if position can be filled or noreturn
//-------------------------------------------------------
bool safe_of_not(int board[N][N],int row, int col)
{
    int i,j;
    //checking that if any value filled or not in column
    for(i=0;i<N;i++)
    {
        if(board[i][col])
        return false;
    }
    //checking that if any value filled in 1st diagonal
    for(i=row,j=col;i>=0&&j>=0;i--,j--)
    {
        if(board[i][j])
        return false;
    }
    //checking that if any value filled in 2nd diagonal
    for(i=row,j=col;i>=0&&j<N;i--,j++)
    {
        if(board[i][j])
        return false;
    }
    //if all upper loops fail means position is ready for filling 
    return true;
}
//------------------------------------------------
//filling spaces with 1's and backtracking
//------------------------------------------------
bool nqueen(int board[N][N],int row)
{
    if(row==N) return true; //function will complete after row==N
    for(int col=0;col<N;col++)
    {
        if(safe_of_not(board,row,col))
        {
            board[row][col]=1;
            if(nqueen(board,row+1))
            return true;
            //if upper loop fails wrong position is filled with 1. we need to reset it to 0.
            board[row][col]=0;
        }

    }
    return false;
}
//------------------------------------
//printing solution
//------------------------------------
bool solution()
{
    int board[N][N]={{0,0,0,0},
                     {0,0,0,0},
                     {0,0,0,0},
                     {0,0,0,0},};
    if(nqueen(board,0)==false)
    {
        std::cout << "solution not exist" << std::endl;
        return false;
    }
    printsolution(board);
    return true;

}
int main(){
solution();
return 0;
}
