# 定义
 1. 对于非终端节点的关键点的个数比其子节点少一个，并且子树有序
 2. 所有的叶子都在相同的高度
 3. 非终端节点至少有$[m/2]$ 个子节点
 4. 根节点的子节点个数在$[2-m]$之间
 5. 叶子节点的关键数的个数最多$m-1$个
	![[BTree1.png]]

# 插入
	1. 尝试将一个新的关键值插入到叶节点
	2. 如果叶子节点太大，则将叶子节点一分为二，并将中间的节点放到双亲节点
	3. 如果双亲节点过大，则将双亲节点分裂，同样把中间的节点向上传递
	4. 重复上述操作之后到顶点，根节点也可以一分为二
# 删除
1. 简单的叶子节点删除。 直接删除
2. 如果关键值不在叶子节点中。  用前驱或者后继节点去替代该值，然后删除非叶子节点的关键值的位置
		![[BTree2.png]] ![[BTree3.png]]
 
3. 如果叶子节点少于的关键点数少于最小个数，那么我们将其中一个值合并到双亲节点并把双亲节点的作为我们缺少的叶子
		 ![[BTree6.png]] ![[BTree7.png]]
1. 如果每个节点都很少，不能向兄弟节点借值。那么将缺少的叶子和其中一个兄弟节点和双亲节点合并
		![[BTree4.png]] ![[BTree5.png]]