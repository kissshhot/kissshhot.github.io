---
title: 贪心算法 | LeetCode Hot 100
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

# 💰 贪心算法

> 每步选择当前最优解，依赖局部最优能推导全局最优的问题结构。

**4 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×1</span> &nbsp;<span class="badge medium">中等 ×3</span>

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
      <td class="num">121</td>
      <td><a href="https://leetcode.cn/problems/best-time-to-buy-and-sell-stock/" target="_blank">买卖股票的最佳时机</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">55</td>
      <td><a href="https://leetcode.cn/problems/jump-game/" target="_blank">跳跃游戏</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">45</td>
      <td><a href="https://leetcode.cn/problems/jump-game-ii/" target="_blank">跳跃游戏 II</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">763</td>
      <td><a href="https://leetcode.cn/problems/partition-labels/" target="_blank">划分字母区间</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **买卖股票的最佳时机**：遍历维护最低买入价，实时计算当前卖出利润并更新最大利润。
- **跳跃游戏**：维护当前能到达的最远位置 `maxReach`，若当前下标超过 maxReach 则不可达。
- **跳跃游戏 II**：维护当前跳的范围终点 `curEnd` 和下一跳能到达的最远点 `farthest`，到达终点时步数加一并更新终点。
- **划分字母区间**：先记录每个字母最后出现位置，再贪心扩张当前区间终点，到达终点时切分。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/heap/">← 堆</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/dp/">动态规划 →</a>
</div>
