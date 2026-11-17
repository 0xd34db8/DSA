### create adjacency list

```cpp
    void prepareAdj(  unordered_map<int, list<int>> &AdjList,    vector<pair<int, int>> &edges  ){

        // loop through the array of connected nodes (edges)
        for(int i = 0; i<edges.size(); ++i){
            // extract individual nodes
            int u = edges[i].first;
            int v = edges[i].second;

            // write the connection in adjacency list
            AdjList[u].push_back(v);
            AdjList[v].push_back(u);
        }
    }
```

### BFS

```cpp
vector<int> BFS(int vertex, vector<pair<int, int>> edges)
{
    // define the adjacency list & visited array
    unordered_map<int, list<int>> AdjList;
    unordered_map<int, bool> visited;

    // create adjacency list
    prepareAdjList(AdjList, edges);

}

```

(incomplete)
