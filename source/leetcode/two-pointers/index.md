---
title: 双指针 | LeetCode Hot 100
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

# 👆 双指针

> 使用两个指针在序列中协同移动，通常用于有序数组或需要同时维护两端信息的场景，可将 O(n²) 降至 O(n)。

**4 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×1</span> &nbsp;<span class="badge medium">中等 ×2</span> &nbsp;<span class="badge hard">困难 ×1</span>

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
      <td class="num">283</td>
      <td><a href="https://leetcode.cn/problems/move-zeroes/" target="_blank">移动零</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">11</td>
      <td><a href="https://leetcode.cn/problems/container-with-most-water/" target="_blank">盛最多水的容器</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">15</td>
      <td><a href="https://leetcode.cn/problems/3sum/" target="_blank">三数之和</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">42</td>
      <td><a href="https://leetcode.cn/problems/trapping-rain-water/" target="_blank">接雨水</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **移动零**：快慢指针，慢指针指向下一个非零元素应填入的位置，快指针扫描非零元素依次覆盖。
- **盛最多水的容器**：左右指针从两端收缩，每次移动较短的那侧（因为移动较长侧不可能增大面积）。
- **三数之和**：排序后固定第一个数，用左右双指针在剩余区间找两数之和等于其相反数；注意去重。
- **接雨水**：左右指针维护 `maxLeft` 和 `maxRight`，当前短板决定该侧能接的水量。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/hash/">← 哈希</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/sliding-window/">滑动窗口 →</a>
</div>
