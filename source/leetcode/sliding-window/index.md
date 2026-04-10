---
title: 滑动窗口 | LeetCode Hot 100
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

# 🪟 滑动窗口

> 维护一个可变大小的窗口（左右指针），根据条件动态扩张或收缩，解决连续子串/子数组问题，时间复杂度 O(n)。

**2 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×2</span>

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
      <td class="num">3</td>
      <td><a href="https://leetcode.cn/problems/longest-substring-without-repeating-characters/" target="_blank">无重复字符的最长子串</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">438</td>
      <td><a href="https://leetcode.cn/problems/find-all-anagrams-in-a-string/" target="_blank">找到字符串中所有字母异位词</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **无重复字符的最长子串**：右指针扩张，遇到重复字符则移动左指针直到窗口内无重复，全程记录最大长度。
- **找到字符串中所有字母异位词**：固定长度窗口（等于 p 的长度），用频率数组比较窗口内字符分布与 p 是否一致。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/two-pointers/">← 双指针</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/substring/">子串 →</a>
</div>
