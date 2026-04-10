---
title: 二分查找 | LeetCode Hot 100
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

# 🎯 二分查找

> 在有序或部分有序结构中以 O(log n) 定位目标，边界处理是关键（左闭右闭 vs 左闭右开）。

**6 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×1</span> &nbsp;<span class="badge medium">中等 ×4</span> &nbsp;<span class="badge hard">困难 ×1</span>

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
      <td class="num">35</td>
      <td><a href="https://leetcode.cn/problems/search-insert-position/" target="_blank">搜索插入位置</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">74</td>
      <td><a href="https://leetcode.cn/problems/search-a-2d-matrix/" target="_blank">搜索二维矩阵</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">34</td>
      <td><a href="https://leetcode.cn/problems/find-first-and-last-position-of-element-in-sorted-array/" target="_blank">在排序数组中查找元素的第一个和最后一个位置</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">33</td>
      <td><a href="https://leetcode.cn/problems/search-in-rotated-sorted-array/" target="_blank">搜索旋转排序数组</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">153</td>
      <td><a href="https://leetcode.cn/problems/find-minimum-in-rotated-sorted-array/" target="_blank">寻找旋转排序数组中的最小值</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">4</td>
      <td><a href="https://leetcode.cn/problems/median-of-two-sorted-arrays/" target="_blank">寻找两个正序数组的中位数</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **搜索插入位置**：标准 lower_bound，返回第一个 `≥ target` 的位置。
- **搜索二维矩阵**：将矩阵展开为一维（`mid / n` 行，`mid % n` 列）做标准二分。
- **查找第一个和最后一个位置**：两次二分分别求左边界和右边界。
- **搜索旋转排序数组**：每次判断左半段或右半段是否有序，再确定 target 在哪侧收缩。
- **旋转数组最小值**：与右端点比较：`nums[mid] > nums[right]` 则最小值在右半，否则在左半（含 mid）。
- **两个正序数组的中位数**：在较短数组上二分划分点，保证两侧元素各占一半，O(log(min(m,n)))。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/backtracking/">← 回溯</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/stack/">栈 →</a>
</div>
