### Create a graph

```cpp
class graph
{
public:
    // Adjacency Matrix
    unordered_map<int, list<int>> adj;

    void addEdge(int u, int v, bool dir)
    {
        // edge u-> v
        adj[u].push_back(v);

        // If undirected, also add edge v -> u
        if (!dir)
            adj[v].push_back(u);
    }


    // Print Adjacent List

    void printAdjList()
    {
        // (i is of type "pair<const int, list<int>> i") | we use "const auto&" instead of writing this
        // i.first = vertex | i.second = the value (list of adjacent vertices, which is of type "list<int>").
        for (const auto& i : adj)
        {
            cout << i.first << "-> ";
            for (const auto& j : i.second)
                cout << j << ", ";
        }
        cout << endl;
    }
};
```

```cpp
int main()
{
    int n;
    cout << "Enter the no. of nodes";
    cin >> n;

    int m;
    cout << "Enter the no. of edges";
    cin >> m;

    graph g;

    // creating undir graph
    for (int i = 0; i < m; ++i)
    {
        int u, v;
        cin >> u >> v;
        g.addEdge(u, v, 0);
    }

    g.printAdjList();

    return 0;
}
```

### Example

```
n = 5;
m = 3;

Edges:
0 1
0 2
1 3


g.printAdjList():
0 -> 1, 2,
1 -> 0, 3,
2 -> 0,
3 -> 1,
```
