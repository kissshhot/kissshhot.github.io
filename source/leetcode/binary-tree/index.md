---
title: 二叉树 | LeetCode Hot 100
date: 2026-04-10
---

<style>
.lc-table { width: 100%; border-collapse: collapse; margin: 16px 0; }
.lc-table th { background: var(--board-bg, #f5f5f5); padding: 10px 14px; text-align: left; font-size: 0.9em; color: #666; }
.lc-table td { padding: 10px 14px; border-bottom: 1px solid var(--border-color, #f0f0f0); font-size: 0.95em; }
.lc-table tr:hover td { background: var(--hover-bg, #fafafa); }
.lc-table a { text-decoration: none; }
.lc-table a:hover { text-decoration: underline; }
.badge { font-size: 0.78em; padding: 2px 9px; border-radius: 12px; font-weight: 500; white-space: nowrap; }
.easy   { background: #e6f7f4; color: #00b8a3; }
.medium { background: #fff7e6; color: #ffb800; }
.hard   { background: #fff0f3; color: #ff375f; }
.num    { color: #aaa; font-size: 0.9em; }
.nav-bar { display: flex; gap: 12px; margin-bottom: 24px; flex-wrap: wrap; }
.nav-bar a { font-size: 0.88em; padding: 4px 12px; border-radius: 6px; border: 1px solid var(--border-color, #e0e0e0); text-decoration: none; }
.nav-bar a:hover { background: var(--hover-bg, #f5f5f5); }
</style>

<div class="nav-bar">
  <a href="/leetcode/">← 返回 Hot 100 总览</a>
</div>

# 🌲 二叉树

> 树的递归、DFS/BFS、BST 性质利用，是面试中最高频的数据结构之一。

**15 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×6</span> &nbsp;<span class="badge medium">中等 ×8</span> &nbsp;<span class="badge hard">困难 ×1</span>

<table class="lc-table">
  <thead>
    <tr>
      <th>#</th>
      <th>题目</th>
      <th>难度</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="num">94</td>
      <td><a href="https://leetcode.cn/problems/binary-tree-inorder-traversal/" target="_blank">二叉树的中序遍历</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">104</td>
      <td><a href="https://leetcode.cn/problems/maximum-depth-of-binary-tree/" target="_blank">二叉树的最大深度</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">226</td>
      <td><a href="https://leetcode.cn/problems/invert-binary-tree/" target="_blank">翻转二叉树</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">101</td>
      <td><a href="https://leetcode.cn/problems/symmetric-tree/" target="_blank">对称二叉树</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">543</td>
      <td><a href="https://leetcode.cn/problems/diameter-of-binary-tree/" target="_blank">二叉树的直径</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">108</td>
      <td><a href="https://leetcode.cn/problems/convert-sorted-array-to-binary-search-tree/" target="_blank">将有序数组转换为二叉搜索树</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">102</td>
      <td><a href="https://leetcode.cn/problems/binary-tree-level-order-traversal/" target="_blank">二叉树的层序遍历</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">98</td>
      <td><a href="https://leetcode.cn/problems/validate-binary-search-tree/" target="_blank">验证二叉搜索树</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">230</td>
      <td><a href="https://leetcode.cn/problems/kth-smallest-element-in-a-bst/" target="_blank">二叉搜索树中第 K 小的元素</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">199</td>
      <td><a href="https://leetcode.cn/problems/binary-tree-right-side-view/" target="_blank">二叉树的右视图</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">114</td>
      <td><a href="https://leetcode.cn/problems/flatten-binary-tree-to-linked-list/" target="_blank">二叉树展开为链表</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">105</td>
      <td><a href="https://leetcode.cn/problems/construct-binary-tree-from-preorder-and-inorder-traversal/" target="_blank">从前序与中序遍历序列构造二叉树</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">437</td>
      <td><a href="https://leetcode.cn/problems/path-sum-iii/" target="_blank">路径总和 III</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">236</td>
      <td><a href="https://leetcode.cn/problems/lowest-common-ancestor-of-a-binary-tree/" target="_blank">二叉树的最近公共祖先</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">124</td>
      <td><a href="https://leetcode.cn/problems/binary-tree-maximum-path-sum/" target="_blank">二叉树中的最大路径和</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **层序遍历**：BFS，队列每次处理一整层（循环前记录队列大小）。
- **验证 BST**：中序遍历应严格递增；或递归传入 `(min, max)` 约束范围。
- **路径总和 III**：前缀和 + 哈希表（类似「和为 K 的子数组」的树上版本）。
- **最近公共祖先**：若 p、q 分别在左右子树则当前节点即 LCA；否则向包含两者的子树递归。
- **构造二叉树**：前序第一个是根，在中序中找根位置分割左右子树，递归建树（哈希表加速查找）。
- **最大路径和**：后序遍历，每个节点计算「经过该节点的最大贡献值」（可向上传递），维护全局最大。
- **展开为链表**：Morris 遍历思路：将左子树的最右节点接到右子树头，再把左子树移到右边，迭代处理。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/linked-list/">← 链表</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/graph/">图论 →</a>
</div>
