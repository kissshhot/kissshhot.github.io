---
title: 堆 | LeetCode Hot 100
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

# ⛰️ 堆

> 优先队列（堆）用于动态维护最大 / 最小值，TopK 问题的标准解法。

**3 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×2</span> &nbsp;<span class="badge hard">困难 ×1</span>

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
      <td class="num">215</td>
      <td><a href="https://leetcode.cn/problems/kth-largest-element-in-an-array/" target="_blank">数组中的第 K 个最大元素</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">347</td>
      <td><a href="https://leetcode.cn/problems/top-k-frequent-elements/" target="_blank">前 K 个高频元素</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">295</td>
      <td><a href="https://leetcode.cn/problems/find-median-from-data-stream/" target="_blank">数据流的中位数</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **第 K 大元素**：维护大小为 K 的最小堆，堆顶即第 K 大；也可用快速选择（平均 O(n)）。
- **前 K 个高频元素**：先统计频率，再用大小为 K 的最小堆（按频率排序）保留频率最高的 K 个元素。
- **数据流的中位数**：大根堆存较小的一半，小根堆存较大的一半，保持两堆大小差不超过 1；中位数由堆顶推导。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/stack/">← 栈</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/greedy/">贪心算法 →</a>
</div>
