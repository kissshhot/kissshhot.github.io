---
title: 链表 | LeetCode Hot 100
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

# 🔗 链表

> 链表是高频考点，涵盖指针操作、快慢指针、归并排序、LRU 缓存等经典题型。

**14 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×5</span> &nbsp;<span class="badge medium">中等 ×7</span> &nbsp;<span class="badge hard">困难 ×2</span>

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
      <td class="num">160</td>
      <td><a href="https://leetcode.cn/problems/intersection-of-two-linked-lists/" target="_blank">相交链表</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">206</td>
      <td><a href="https://leetcode.cn/problems/reverse-linked-list/" target="_blank">反转链表</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">234</td>
      <td><a href="https://leetcode.cn/problems/palindrome-linked-list/" target="_blank">回文链表</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">141</td>
      <td><a href="https://leetcode.cn/problems/linked-list-cycle/" target="_blank">环形链表</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">21</td>
      <td><a href="https://leetcode.cn/problems/merge-two-sorted-lists/" target="_blank">合并两个有序链表</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">142</td>
      <td><a href="https://leetcode.cn/problems/linked-list-cycle-ii/" target="_blank">环形链表 II</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">2</td>
      <td><a href="https://leetcode.cn/problems/add-two-numbers/" target="_blank">两数相加</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">19</td>
      <td><a href="https://leetcode.cn/problems/remove-nth-node-from-end-of-list/" target="_blank">删除链表的倒数第 N 个结点</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">24</td>
      <td><a href="https://leetcode.cn/problems/swap-nodes-in-pairs/" target="_blank">两两交换链表中的节点</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">138</td>
      <td><a href="https://leetcode.cn/problems/copy-list-with-random-pointer/" target="_blank">随机链表的复制</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">148</td>
      <td><a href="https://leetcode.cn/problems/sort-list/" target="_blank">排序链表</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">146</td>
      <td><a href="https://leetcode.cn/problems/lru-cache/" target="_blank">LRU 缓存</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">25</td>
      <td><a href="https://leetcode.cn/problems/reverse-nodes-in-k-group/" target="_blank">K 个一组翻转链表</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
    <tr>
      <td class="num">23</td>
      <td><a href="https://leetcode.cn/problems/merge-k-sorted-lists/" target="_blank">合并 K 个升序链表</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **相交链表**：两指针各自走完自己的链表后切换到对方，相遇点即为交点（路径等长）。
- **环形链表 I / II**：快慢指针判环；找入环点时将一指针重置到头节点，两指针同速前进再次相遇即入环点。
- **反转链表**：迭代三指针或递归。
- **回文链表**：快慢指针找中点 → 反转后半段 → 比较。
- **删除倒数第 N 个节点**：双指针，快指针先走 N 步，再同步前进直到快指针到尾。
- **随机链表复制**：哈希表映射旧节点到新节点，两次遍历分别建节点和连接 next/random。
- **排序链表**：归并排序，快慢指针找中点后递归，O(n log n)，O(log n) 空间。
- **LRU 缓存**：哈希表 + 双向链表，O(1) 实现 get 和 put。
- **合并 K 个升序链表**：最小堆（每次取堆顶合并）或分治归并。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/matrix/">← 矩阵</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/binary-tree/">二叉树 →</a>
</div>
