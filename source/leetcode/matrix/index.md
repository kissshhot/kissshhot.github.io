---
title: 矩阵 | LeetCode Hot 100
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

# 🗂️ 矩阵

> 二维数组的原地操作、模拟遍历顺序以及二维二分查找。

**4 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×4</span>

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
      <td class="num">73</td>
      <td><a href="https://leetcode.cn/problems/set-matrix-zeroes/" target="_blank">矩阵置零</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">54</td>
      <td><a href="https://leetcode.cn/problems/spiral-matrix/" target="_blank">螺旋矩阵</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">48</td>
      <td><a href="https://leetcode.cn/problems/rotate-image/" target="_blank">旋转图像</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">240</td>
      <td><a href="https://leetcode.cn/problems/search-a-2d-matrix-ii/" target="_blank">搜索二维矩阵 II</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **矩阵置零**：用第一行、第一列作为标记位，先处理其自身是否含零，再根据标记原地修改，O(1) 空间。
- **螺旋矩阵**：维护四条边界（上下左右），按顺序收缩模拟螺旋读取。
- **旋转图像**：先沿主对角线转置，再水平翻转（等价于顺时针旋转 90°），O(1) 空间原地完成。
- **搜索二维矩阵 II**：从右上角出发，当前值大于 target 则左移，小于 target 则下移，时间复杂度 O(m+n)。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/array/">← 普通数组</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/linked-list/">链表 →</a>
</div>
