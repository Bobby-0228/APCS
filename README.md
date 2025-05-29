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