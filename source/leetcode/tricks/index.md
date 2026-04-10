---
title: 技巧 | LeetCode Hot 100
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

# ✨ 技巧

> 位运算、排序 + 计数等巧妙手法，往往能将复杂问题化为一行解法。

**5 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×2</span> &nbsp;<span class="badge medium">中等 ×3</span>

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
      <td class="num">136</td>
      <td><a href="https://leetcode.cn/problems/single-number/" target="_blank">只出现一次的数字</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">169</td>
      <td><a href="https://leetcode.cn/problems/majority-element/" target="_blank">多数元素</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">75</td>
      <td><a href="https://leetcode.cn/problems/sort-colors/" target="_blank">颜色分类</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">31</td>
      <td><a href="https://leetcode.cn/problems/next-permutation/" target="_blank">下一个排列</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">287</td>
      <td><a href="https://leetcode.cn/problems/find-the-duplicate-number/" target="_blank">寻找重复数</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **只出现一次的数字**：所有数异或，相同的数两两抵消，最终剩下只出现一次的数。
- **多数元素**：Boyer-Moore 投票算法，维护候选数和计数；遇到相同则加一，不同则减一，减到 0 更换候选。
- **颜色分类**：荷兰国旗问题，三指针（low、mid、high）一次遍历原地分类。
- **下一个排列**：从右找第一个下降点 i，再从右找第一个大于 `nums[i]` 的数交换，最后翻转 `i+1` 到末尾。
- **寻找重复数**：将数组视为链表（`i → nums[i]`），用快慢指针找环入口（Floyd 判环），O(1) 空间且不修改数组。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/multi-dp/">← 多维动态规划</a>
  <a href="/leetcode/">返回总览</a>
</div>
