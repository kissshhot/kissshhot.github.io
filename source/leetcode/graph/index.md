---
title: 图论 | LeetCode Hot 100
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

# 🕸️ 图论

> 图的 BFS/DFS 遍历、拓扑排序与前缀树（Trie）。

**4 题** &nbsp;·&nbsp; <span class="badge medium">中等 ×4</span>

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
      <td class="num">200</td>
      <td><a href="https://leetcode.cn/problems/number-of-islands/" target="_blank">岛屿数量</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">994</td>
      <td><a href="https://leetcode.cn/problems/rotting-oranges/" target="_blank">腐烂的橘子</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">207</td>
      <td><a href="https://leetcode.cn/problems/course-schedule/" target="_blank">课程表</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
    <tr>
      <td class="num">208</td>
      <td><a href="https://leetcode.cn/problems/implement-trie-prefix-tree/" target="_blank">实现 Trie（前缀树）</a></td>
      <td><span class="badge medium">中等</span></td>
    </tr>
  </tbody>
</table>

---

**核心思路**

- **岛屿数量**：DFS/BFS，遇到 `'1'` 则将整块岛屿标记为已访问（置为 `'0'`），计数器加一。
- **腐烂的橘子**：多源 BFS，将所有腐烂橘子同时入队作为第 0 层，BFS 层数即为最少分钟数；最后检查是否还有新鲜橘子。
- **课程表**：拓扑排序（BFS Kahn 算法），若最终处理节点数等于总课程数则可完成，否则存在环。
- **实现 Trie**：每个节点含 26 个子节点指针和一个 `isEnd` 标志，insert/search/startsWith 均按字符逐层遍历。

<div class="nav-bar" style="margin-top: 24px; margin-bottom: 0;">
  <a href="/leetcode/binary-tree/">← 二叉树</a>
  <a href="/leetcode/">返回总览</a>
  <a href="/leetcode/backtracking/">回溯 →</a>
</div>
