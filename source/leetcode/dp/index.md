---
title: 动态规划 | LeetCode Hot 100
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

# 🧮 动态规划

> 将问题拆解为重叠子问题，通过记忆化或自底向上的方式避免重复计算，是算法面试最重要的专题之一。

**10 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×2</span> &nbsp;<span class="badge medium">中等 ×7</span> &nbsp;<span class="badge hard">困难 ×1</span>

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
      <td class="num">70</td>
      <td><a href="https://leetcode.cn/problems/climbing-stairs/" target="_blank">爬楼梯</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">118</td>
      <td><a href="https://leetcode.cn/problems/pascals-triangle/" target="_blank">杨辉三角</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">198</td>
      <td><a href="https://leetcode.cn/problems/house-robber/" target="_blank">打家劫舍</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">279</td>
      <td><a href="https://leetcode.cn/problems/perfect-squares/" target="_blank">完全平方数</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">322</td>
      <td><a href="https://leetcode.cn/problems/coin-change/" target="_blank">零钱兑换</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">139</td>
      <td><a href="https://leetcode.cn/problems/word-break/" target="_blank">单词拆分</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">300</td>
      <td><a href="https://leetcode.cn/problems/longest-increasing-subsequence/" target="_blank">最长递增子序列</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">152</td>
      <td><a href="https://leetcode.cn/problems/maximum-product-subarray/" target="_blank">乘积最大子数组</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">416</td>
      <td><a href="https://leetcode.cn/problems/partition-equal-subset-sum/" target="_blank">分割等和子集</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">32</td>
      <td><a href="https://leetcode.cn/problems/longest-valid-parentheses/" target="_blank">最长有效括号</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **爬楼梯**：`dp[i] = dp[i-1] + dp[i-2]`，斐波那契数列。
- **打家劫舍**：`dp[i] = max(dp[i-1], dp[i-2] + nums[i])`，相邻不可同时选。
- **零钱兑换 / 完全平方数**：完全背包，`dp[i] = min(dp[i], dp[i-coin] + 1)`。
- **最长递增子序列**：`dp[i]` = 以 `nums[i]` 结尾的 LIS 长度；也可用二分 + 贪心 O(n log n)。
- **乘积最大子数组**：同时维护当前最大值和最小值（负负得正），`maxDP[i] = max(nums[i], maxDP[i-1]*nums[i], minDP[i-1]*nums[i])`。
- **分割等和子集**：01 背包，目标为 `sum/2`，`dp[j] = dp[j] || dp[j - nums[i]]`。
- **最长有效括号**：`dp[i]` 表示以 `s[i]` 结尾的最长有效括号长度；遇到 `)` 时查看配对的 `(` 前的状态。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/greedy/">← 贪心算法</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/multi-dp/">多维动态规划 →</a>
</div>
