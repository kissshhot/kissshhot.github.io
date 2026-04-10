---
title: 哈希 | LeetCode Hot 100
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

# 🔑 哈希

> 利用哈希表以 O(1) 的时间复杂度完成查找，是将时间复杂度从 O(n²) 降到 O(n) 的常用手段。

**3 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×1</span> &nbsp;<span class="badge medium">中等 ×2</span>

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
      <td class="num">1</td>
      <td><a href="https://leetcode.cn/problems/two-sum/" target="_blank">两数之和</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">49</td>
      <td><a href="https://leetcode.cn/problems/group-anagrams/" target="_blank">字母异位词分组</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">128</td>
      <td><a href="https://leetcode.cn/problems/longest-consecutive-sequence/" target="_blank">最长连续序列</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **两数之和**：遍历数组，将每个数存入哈希表，查找 `target - num` 是否已存在。
- **字母异位词分组**：以排序后的字符串为 key，将同组单词归并到同一个列表。
- **最长连续序列**：将所有数存入 Set，对每个序列起点（`num-1` 不在 Set 中）向后延伸计数。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/">← 返回总览</a>
  <a href="/leetcode/two-pointers/">双指针 →</a>
</div>
