# Sachin Katti Solutions

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [2014](#2014)

<!-- /TOC -->

## 2014
1. To determine whether a graph is 1-connected, we can use BFS/DFS (which is O(V + E)). Then, we
  could iterate and simply try to delete an edge, perform the check, and repeat.

2. This naive algorithm would run in O(E * (E + V)) time.

3. We may be able to do something about loops. If the graph has a look, it appears to be 2-connected according to Katti's definition.
