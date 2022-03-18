# bfs
#include<stdio.h>
#define max 20
int visited[max];
int graph[max][max];
int que[100];
int n,i,x,j,front=0,rear=0;
void readgraph()
{
    printf("enter the size of adjacent matrix");
    scanf("%d",&n);
    printf("enter the adjacent value");
    for(int i=0;i<=n;i++)
    {
        for(int j=0;j<=n;j++)
        {
            scanf("%d",&graph[i][j]);
        }
    }
}

void enque()
{
    if(rear==n-1)
    {
        printf("ques is empty");
    }
    else
    {
        printf("enter the value");
        scanf("%d",&x);
        que[rear]=x;
        rear++;
    }
}
int dequeue()
{
    if(front==rear)
    {
       return que[x];
       // printf("ques is full");
    }
    else
    {
        printf("enter the value to enqueue %d\n",que[front]);
        front++;
        return que[x];
    }
}
void bfs(int v)
{
    visited [v]=1;
    scanf("%d",v);
    while(1)
    {
    for(int i=0;i<=n;i++)
    {
        if(visited[i]==0&&graph[v][i]==1)
        {
            enque(i);
            visited[i]=1;
        }
    }
    v=dequeue();
    if(v==-1)
    {
        break;
    }
    else
    {
        printf("%d",v);
    }
    }
    printf("\n");
}
void main()
{
    readgraph();
    printf("first search");
    for(int j=0;j<=n;j++)
    {
    printf("started at vertex %d\n",j);
    for(int i=0;i<=n;i++)
    {
        visited[i]=0;
    }
    bfs(j);
    }
}

