## 二叉搜索树的第k大节点

给定一棵二叉搜索树，请找出其中第k大的节点。

```

function kthLargest(root, k){
	var res;
	function dfs(head){
		if(!head) return;
		dfs(root.right);
		if(k===0) return;
		k--;
		if(k===0) res = head.val;
		dfs(root.left);
	}
	dfs(root)
	return res
}
```

## 二叉搜索树的第k小节点

```

function kthSmallest(root, k){
	var res;
	function dfs(root){
		if(root && k>0){
			dfs(root.left);
			if(--k === 0){
				res = root.val;
				return;
			}
			dfs(root.right);
		}
	}
	dfs(root);
	return res;
}
```