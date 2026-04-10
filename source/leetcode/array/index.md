---
title: 普通数组 | LeetCode Hot 100
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

# 📊 普通数组

> 数组基础操作与区间处理，涵盖前缀积、区间合并、原地修改等常见技巧。

**5 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×4</span> &nbsp;<span class="badge hard">困难 ×1</span>

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
      <td class="num">53</td>
      <td><a href="https://leetcode.cn/problems/maximum-subarray/" target="_blank">最大子数组和</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">56</td>
      <td><a href="https://leetcode.cn/problems/merge-intervals/" target="_blank">合并区间</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">189</td>
      <td><a href="https://leetcode.cn/problems/rotate-array/" target="_blank">轮转数组</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">238</td>
      <td><a href="https://leetcode.cn/problems/product-of-array-except-self/" target="_blank">除自身以外数组的乘积</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">41</td>
      <td><a href="https://leetcode.cn/problems/first-missing-positive/" target="_blank">缺失的第一个正数</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **最大子数组和**：Kadane 算法，`dp[i] = max(nums[i], dp[i-1] + nums[i])`，维护当前最大值。
- **合并区间**：按区间起点排序后线性扫描，当前区间与上一个区间有重叠则合并（取右端点较大值）。
- **轮转数组**：三次翻转法：整体翻转 → 前 k 个翻转 → 后 n-k 个翻转，O(1) 空间。
- **除自身以外数组的乘积**：先从左到右计算前缀积，再从右到左累乘后缀积，不使用除法，O(1) 空间。
- **缺失的第一个正数**：利用数组本身作哈希表，将每个正整数 x（1≤x≤n）放到 `nums[x-1]` 位置，再扫描找第一个不在位的下标。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/substring/">← 子串</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/matrix/">矩阵 →</a>
</div>
