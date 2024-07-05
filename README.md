#include<stdio.h>
void solve(int n, int m, int path[][],int next_row,int next_col)
{
    if(next_row == n-1 && next_col== m-1)
    {
        printf("%d ",path)
        retun;
    }
    else
    {
        for(next_col=0;next_col<=m-1;next_col++)
        {
            path[next_row][next_col] == 1;
        }
    }
     else
    {
        for(next_row=0;next_row<=m-1;next_row++)
        {
            path[next_row][next_col] == 1;
        }
    }
    path[next_row][next_col] == 0;
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
