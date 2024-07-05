#Rat_path
A given n and m value creat a 2 dimensional array. your task is to print all possible path available for your rat from source index to destination index.
Note: your rat can move 2 directions onle forward and downward direction at a time.


#include<stdio.h>
void solve(int n, int m, int path[n][m],int s_row,int s_col)
{
    if(s_row == n-1 && s_col== m-1)
    {
        int row, col;
        for(row = 0;row<=n-1;row++)
        {
            for(col=0;col<=m-1;col++)
            {
                
                printf("%d ",path[row][col]);
                
            }
            printf("\n");
        }
        printf("\n");
        return ;
    }
    else
    {
        int next_row,next_col;
        next_row = s_row;
        next_col = s_col+1;
        if(next_row<=n-1 && next_col <=m-1)
        {
            path[next_row][next_col] = 1;
            solve(n,m,path,next_row,next_col);
        }
        next_row = s_row+1;
        next_col = s_col;
    
        if(next_row<=n-1 && next_col <=m-1)
        {
            path[next_row][next_col] = 1;
            solve(n,m,path,next_row,next_col);
        }
    
        path[s_row][s_col] = 0;
    }
}
int main()
{
    int n,m;
    scanf("%d %d",&n,&m);
    int path[n][m];
    int row, col;
    for(row = 0;row<=n-1;row++)
    {
        for(col=0;col<=m-1;col++)
        {
            path[row][col]=0;
        }
    }
    path[0][0]=1;
    solve(n,m,path,0,0);
    return 0;
}
