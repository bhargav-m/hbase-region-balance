"# hbase-region-balance" 
 *  hbase region balance 方案只能保证region均匀分配到region server
 *  优化策略 : 在table级别，对多于平局值部分的region，采用最少region节点分配策略，替代 admin.balancer();
 *  最终效果 : 在table级别，每个regionServer的region个数都在平均值上下
 *  
 *  Table level regional balance, the number of regions allocated by each region server in the vicinity of the average