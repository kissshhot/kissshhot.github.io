---
title: 栈 | LeetCode Hot 100
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

# 📚 栈

> 栈的后进先出特性适合处理括号匹配、表达式解析、单调栈等场景。

**5 题** &nbsp;·&nbsp; <span class="badge easy">简单 ×1</span> &nbsp;<span class="badge medium">中等 ×3</span> &nbsp;<span class="badge hard">困难 ×1</span>

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
      <td class="num">20</td>
      <td><a href="https://leetcode.cn/problems/valid-parentheses/" target="_blank">有效的括号</a></td>
      <td><span class="badge easy">简单</span></td>
    </tr>
    <tr>
      <td class="num">155</td>
      <td><a href="https://leetcode.cn/problems/min-stack/" target="_blank">最小栈</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">394</td>
      <td><a href="https://leetcode.cn/problems/decode-string/" target="_blank">字符串解码</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">739</td>
      <td><a href="https://leetcode.cn/problems/daily-temperatures/" target="_blank">每日温度</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">84</td>
      <td><a href="https://leetcode.cn/problems/largest-rectangle-in-histogram/" target="_blank">柱状图中最大的矩形</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **有效的括号**：遇到左括号入栈，遇到右括号则弹出栈顶检查是否匹配；最终栈为空则合法。
- **最小栈**：维护辅助栈，每次 push 时同步记录当前最小值（`min(val, minStack.top())`）。
- **字符串解码**：数字与字符串分别用栈存储，遇到 `[` 压栈，遇到 `]` 弹栈并重复字符串。
- **每日温度**：单调递减栈，栈内存下标；遇到比栈顶温度高的天，依次弹栈并计算天数差。
- **柱状图中最大的矩形**：单调递增栈，遇到较低柱子时弹栈并以弹出柱为高度计算面积（两端哨兵简化边界）。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/binary-search/">← 二分查找</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/heap/">堆 →</a>
</div>
