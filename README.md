这是英国《每日邮报》2012年6月30日的一篇报道,最难数独。解数独用的就是深度优先搜索，有几个方面可以优化一下提高速度：1.把每个空格的可能的点先列举出来，因为深搜是把遍历的值写入sudoku矩阵再判断，如果不列举可能的值，那就只能用0-9遍历，这样效率会降低，如果空格较少的情况下，先把可能的点列举出来会使速度翻倍；2.每次把可能情况最少的点优先尝试写入值判断，这个我在程序里没有加，因为深搜的每个树节点必须是固定的，这样当退栈返回上一结点的时候才能正确返回，而我加了这个判断最优节点功能的代码中，返回的树节点不是固定的，因为随着数独空格中值的填入，矩阵也发生着变化，每个点的优先级也在同时发生着变化，这样逻辑就乱了，但我觉得还是可以加上的，这里也算一个小遗憾，希望感兴趣的大牛加上这个功能，那速度又是一番提升。
