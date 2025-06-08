# APCS
## 2024.01(p3) 邏輯電路
* 拓樸排序 Topological Sort
    * 每次都找 in degree=0 的node 然後把node刪掉（相當於把後節點的 in degree 減一）
    * 找到的node順序就會是拓樸排序

* 什麼時候用拓排？
    * 判斷graph有沒有環
    * 依賴*順序*    
        * 資料流傳順序
        * 課程規劃

* 圖可以用 adjacency list 或 adjacency matrix 存
    * Adjacency list 就是紀錄每個node的前節點們（或後節點們）有誰，適用於無權邊

* 拓樸排序的過程相當於維護一個queue (BFS的概念) 但我們可以用head來取代pop(0)

* DAG 才能拓排 <-> 能拓排必是 DAG
    * DAG: Directed Acylcic Graph 有向無環圖

## 2017.10(p3) 邏輯電路
* 樹的基本定義
    * 無環的連通圖
    * 節點數 = 邊數 + 1
    * 有唯一一條 simple path 連接任意兩點

| 術語         | 定義                        |
| ---------- | ------------------------- |
| 根（root）    | 樹的起點，父節點數量=0 |
| 葉（leaf）    | 沒有子節點的節點                  |
| 深度（depth）  | 根到某節點所經過的邊數               |
| 高度（height） | 該節點到最深葉子的最長距離（通常從葉子往上遞推）  |
| 子樹 (subtree) | 某節點為根的那棵部分樹               |

* 樹的常見表示法
    * Adjacency list：children[u] = [v1, v2, ...]
    * Parent array：parent[v] = u
    * Edge list（不推薦直接用於 DFS）

* 深度優先搜尋 DFS (Depth First Search)
* DFS 的基本流程（遞迴版本）
```python
def dfs(node):
    for child in children[node]:
            dfs(node)
```
| 功能              | 說明                            |
| --------------- | ----------------------------- |
| 樹的遍歷            | 列印節點、計數、處理結構                  |
| 計算節點高度 / 深度     | 搭配參數傳遞或遞迴回傳                   |
| 樹的動態規劃（Tree DP） | 自下而上計算節點的狀態，例如子樹大小、高度         |
| LCA（最近公共祖先）處理   | 樹上重要操作之一，DFS 建 pre/post order |
