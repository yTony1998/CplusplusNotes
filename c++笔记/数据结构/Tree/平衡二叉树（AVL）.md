# 高度平衡的二叉树 
1. 平衡因子 `height(left subtree) - height(right subtree)` <=1
2. 证明效率是对数阶的
	![[AVL证明1.png]]
	![[AVL证明2.png]]
3. 插入或者删除将导致AVL树的形态发生变化，解决步骤如下：
	1. 插入或者删除之后通过节点by节点回溯到根节点
	2. 如果平衡因子大于2或者小于-2，调整树（旋转，将节点调整）存在四种情况
	3. Outside Case(需要单个旋转) 
		- 在左子树插入左节点（LL）right rotation	
			![[AVLPictcure3.png]]
			![[AVLPicutre4.png]] 
		- 在右子树插入右节点（LR）left rotation
			![[RR2.png]]![[RR3.png]]
			
	
	4. Inside Case(需要两次旋转)
		-  在左子树插入右节点(LR) 
			![[LR1.png]]
			![[LR2.png]]
			![[LR3.png]]
			![[LR4.png]] ![[LR5.png]] 
		-  在右子树插入左节点
			![[RL1.png]] ![[RL2.png]]
			