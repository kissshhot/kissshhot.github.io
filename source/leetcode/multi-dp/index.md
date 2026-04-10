---
title: 多维动态规划 | LeetCode Hot 100
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

# 📐 多维动态规划

> 状态由两个或多个变量决定（如两个序列的下标、矩阵坐标），通常需要二维 DP 表。

**5 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×5</span>

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
      <td class="num">62</td>
      <td><a href="https://leetcode.cn/problems/unique-paths/" target="_blank">不同路径</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">64</td>
      <td><a href="https://leetcode.cn/problems/minimum-path-sum/" target="_blank">最小路径和</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">5</td>
      <td><a href="https://leetcode.cn/problems/longest-palindromic-substring/" target="_blank">最长回文子串</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">1143</td>
      <td><a href="https://leetcode.cn/problems/longest-common-subsequence/" target="_blank">最长公共子序列</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">72</td>
      <td><a href="https://leetcode.cn/problems/edit-distance/" target="_blank">编辑距离</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **不同路径**：`dp[i][j] = dp[i-1][j] + dp[i][j-1]`，可压缩为一维数组。
- **最小路径和**：同上加权，`dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + grid[i][j]`。
- **最长回文子串**：`dp[i][j]` 表示 `s[i..j]` 是否为回文；`dp[i][j] = (s[i]==s[j]) && dp[i+1][j-1]`；也可用中心扩展法 O(n²) 时间 O(1) 空间。
- **最长公共子序列**：`dp[i][j]` = `s1[0..i-1]` 与 `s2[0..j-1]` 的 LCS 长度；字符相同则 `+1`，否则取两者删一个的最大值。
- **编辑距离**：`dp[i][j]` = 将 `word1[0..i-1]` 转换为 `word2[0..j-1]` 的最少操作数；字符相同则继承，否则取插入/删除/替换三者最小值加 1。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/dp/">← 动态规划</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/tricks/">技巧 →</a>
</div>
