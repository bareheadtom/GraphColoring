# GraphColoring
Tabu Search Algorithm: A Case Study on Graph Coloring realized by Python and C++
# 基于禁忌搜索算法进行的图着色，分别使用了c++和python实现。
# 局部搜索的思想就是快速找出一个初始解，然后不断改进。并且加入了禁忌表，使我们避免的进入到局部最优的情况。
# data:
##   存放算例，
# readMe：
##   有第一列为算例文件，第二列为算例的输出结果，第三列为实际该算例成功着色的迭代次数，第四列为运算时间
# 函数python版：
###   def initialSolution(sol,k,n):初始化图着色
###   def initializeAdjacentColorTable(adjacent_Color_Table,edges,sol):根据边和当前图着色情况生成邻接着色表
###   def calculateFValueAndConfilictPares(edges,sol):计算当前着色情况的f值和冲突边
###   def getAdjacentVertices(edges,vertice):获得指定节点的相邻节点
###   def findMove(adjacent_Color_Table,sol,n,k,taBuTenureTable,iterCur):找到一次最优移动
###   def makeMove(adjacent_Color_Table,sol,bestMove,bestdeltValue,taBuTenureTable,iterCur):执行最优移动
# 运算结果python版：
   算例文件名 |   最少着色颜色数      |     迭代次数 |  运算时间 
   ------------|-----------------|----------------|--------------
   DSJC125.1	    |         5      |          1064 |22s  
   DSJC125.5	    |         17       |          12972 |207.9s
   DSJC125.9	     |        44      |           13333  | 305.3s  
   DSJC250.1	     |        8      |            14835  |  202s
   DSJC250.5	      |       28
   DSJC250.9	       |      72
   DSJC500.1	      |       12
   DSJC500.5	       |      49,48,47
# 函数c++版：
###   int* initialSolution(int* sol, int k, int n)初始化图着色
###   void initializeAdjacentColorTable(int **Adjacent_Color_Table, vector<vector<string>> &edges, int *sol)根据边和当前图着色情况生成邻接着色表
###   int calculateFValue(vector<vector<string>> &edges, int* sol)计算当前着色情况的f值和冲突边
###   vector<int> getAdjacentVertices(int node, vector<vector<string>> &edges)获得指定节点的相邻节点
###   int findMove(int **Adjacent_Color_Table, int *sol,int n,int k, int **TaBuTenureTable,int &node,int &color,int best_f,int f,int currIter)找到一次最优移动
###   void makeMove(int &f,int delt,int &best_f,int node,int color,int *sol, int **TaBuTenureTable,int currIter, int **Adjacent_Color_Table, vector<vector<string>> &edges)执行最优移动
# 运算结果c++版：
   算例文件名 |   最少着色颜色数      |     迭代次数 |  运算时间 
   ------------|-----------------|----------------|--------------
   DSJC125.1	    |         5      |          6340 |239  
   DSJC125.5	    |         17       |          129331 |14758s
   DSJC125.9	     |        44      |           2119  | 1047  
   DSJC250.1	     |        8      |            21622  |  2541
   DSJC250.5	      |       28
   DSJC250.9	       |      72
   DSJC500.1	      |       12
   DSJC500.5	       |      49,48,47

# 感想
通过这次图着色算法，使我初步了解了启发式优化。发现实现过程还是十分有趣的，比如中间也遇到过一些问题，在禁忌搜索过程中，遇到禁忌移动和非禁忌移动，当没有非禁忌移动时，却不满足禁忌解除的条件时，我们的解决方法有适当把禁忌长度设置短一点，或者直接选择最好的禁忌移动即可。相信自己有能力并且能一直能在这个方向做下去。
