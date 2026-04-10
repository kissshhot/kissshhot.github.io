---
title: 回溯 | LeetCode Hot 100
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

# ↩️ 回溯

> 在搜索空间中通过「选择 → 递归 → 撤销」的模板枚举所有可能性，适合排列、组合、子集、迷宫等问题。

**8 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×7</span> &nbsp;<span class="badge hard">困难 ×1</span>

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
      <td class="num">46</td>
      <td><a href="https://leetcode.cn/problems/permutations/" target="_blank">全排列</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">78</td>
      <td><a href="https://leetcode.cn/problems/subsets/" target="_blank">子集</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">17</td>
      <td><a href="https://leetcode.cn/problems/letter-combinations-of-a-phone-number/" target="_blank">电话号码的字母组合</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">39</td>
      <td><a href="https://leetcode.cn/problems/combination-sum/" target="_blank">组合总和</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">22</td>
      <td><a href="https://leetcode.cn/problems/generate-parentheses/" target="_blank">括号生成</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">79</td>
      <td><a href="https://leetcode.cn/problems/word-search/" target="_blank">单词搜索</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">131</td>
      <td><a href="https://leetcode.cn/problems/palindrome-partitioning/" target="_blank">分割回文串</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">51</td>
      <td><a href="https://leetcode.cn/problems/n-queens/" target="_blank">N 皇后</a></td>
      <td><span class="badge hard">困难</span></td>
    </tr>
  </tbody>
</table>

---

**回溯模板**

```
def backtrack(path, choices):
    if 满足结束条件:
        result.add(path.copy())
        return
    for choice in choices:
        做选择
        backtrack(path, remaining_choices)
        撤销选择
```

**核心思路**

- **全排列**：used 数组记录已选，每次从未选中的数中选一个加入 path。
- **子集**：从当前 index 开始枚举，每个节点都可以收录到结果集中。
- **组合总和**：允许重复选，每次从当前 index 开始；剩余 target < 0 则剪枝。
- **括号生成**：剩余左括号数 > 0 可加 `(`；剩余右括号数 > 剩余左括号数可加 `)`。
- **N 皇后**：用三个集合分别记录已占用的列、左对角线、右对角线，逐行放置皇后。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/graph/">← 图论</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/binary-search/">二分查找 →</a>
</div>
