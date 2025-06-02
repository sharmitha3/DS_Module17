# Ex24 Topological Sort
## DATE:
## AIM:
To compose the code to determine whether the topological ordering for the following graph is possible or not.

![image](https://github.com/user-attachments/assets/c74a7111-9b59-475c-aad4-9baf23d50ec0)


## Algorithm
1.Calculate indegree of each vertex and enqueue vertices with indegree 0
2.While queue is not empty, dequeue vertex v and add it to topological order
3.For each neighbor of v, remove edge v->neighbor and decrement indegree of neighbor
4.If indegree of neighbor becomes 0, enqueue neighbor
5.If all vertices processed, print topological order; else, report cycle   

## Program:
```

Program to determine whether the topological ordering for the following graph is possible or not
Developed by: Sharmitha V
RegisterNumber: 212223110048

//#include<stdio.h>
//#include<stdlib.h>

//#define MAX 5

//int n;    
//int adj[MAX][MAX]; 
//void create_graph();

//int queue[MAX], front = -1,rear = -1;
//void insert_queue(int v);
//int delete_queue();
//int isEmpty_queue();

//int indegree(int v);

int main()
{
        int i,v,count,topo_order[MAX],indeg[MAX];

        create_graph();

        /*Find the indegree of each vertex*/
        for(i=0;i<n;i++)
        {
                indeg[i] = indegree(i);
                if( indeg[i] == 0 )
                        insert_queue(i);
        }

        count = 0;

        while(  !isEmpty_queue( ) && count < n )
        {
                v = delete_queue();
        topo_order[++count] = v; 
                for(i=0; i<n; i++)
                {
                        if(adj[v][i] == 1)
                        {
                                adj[v][i] = 0;
                                indeg[i] = indeg[i]-1;
                                if(indeg[i] == 0)
                                        insert_queue(i);
                        }
                }
        }

        if( count < n )
        {
                printf("No topological ordering possible, graph contains cycle\n");
                exit(1);
        }
        printf("Vertices in topological order are :\n");
        for(i=1; i<=count; i++)
                printf( "%d ",topo_order[i] );
        printf("\n");

        return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/94d0b896-aa28-45ef-8e8d-735837b72bbd)


## Result:
Thus, the C program for determining whether the topological ordering for the following graph is possible or not, is implemented successfully.
