---
title: 子串 | LeetCode Hot 100
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

# 🔍 子串

> 涉及子数组前缀和、单调队列等技巧，处理较复杂的子串/子数组约束问题。

**3 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×1</span> &nbsp;<span class="badge hard">困难 ×2</span>

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
      <td class="num">560</td>
      <td><a href="https://leetcode.cn/problems/subarray-sum-equals-k/" target="_blank">和为 K 的子数组</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">239</td>
      <td><a href="https://leetcode.cn/problems/sliding-window-maximum/" target="_blank">滑动窗口最大值</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
    <tr>
      <td class="num">76</td>
      <td><a href="https://leetcode.cn/problems/minimum-window-substring/" target="_blank">最小覆盖子串</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **和为 K 的子数组**：前缀和 + 哈希表，遍历时统计 `prefixSum - k` 出现的次数即为以当前位置结尾的合法子数组数量。
- **滑动窗口最大值**：单调递减双端队列，队头始终是当前窗口最大值；新元素入队时弹出所有更小的元素。
- **最小覆盖子串**：可变滑动窗口 + 需求满足计数器，右指针扩张纳入字符，满足条件后左指针收缩求最小窗口。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/sliding-window/">← 滑动窗口</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/array/">普通数组 →</a>
</div>
