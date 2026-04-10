---
title: LeetCode Hot 100
date: 2026-04-10
---

<style>
.lc-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 16px;
  margin: 24px 0;
}
.lc-card {
  border: 1px solid var(--border-color, #e0e0e0);
  border-radius: 8px;
  padding: 16px 20px;
  text-decoration: none !important;
  display: block;
  transition: box-shadow 0.2s, transform 0.2s;
}
.lc-card:hover {
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
  transform: translateY(-2px);
}
.lc-card-title {
  font-size: 1.05em;
  font-weight: 600;
  margin-bottom: 6px;
}
.lc-card-sub {
  font-size: 0.85em;
  color: #888;
  margin-bottom: 10px;
}
.lc-badges {
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
}
.badge {
  font-size: 0.75em;
  padding: 2px 8px;
  border-radius: 12px;
  font-weight: 500;
}
.badge-easy   { background: #e6f7f4; color: #00b8a3; }
.badge-medium { background: #fff7e6; color: #ffb800; }
.badge-hard   { background: #fff0f3; color: #ff375f; }
.badge-total  { background: #f0f4ff; color: #4a6cf7; }
.lc-stats {
  display: flex;
  gap: 24px;
  margin: 20px 0 32px;
  flex-wrap: wrap;
}
.lc-stat {
  text-align: center;
}
.lc-stat-num {
  font-size: 2em;
  font-weight: 700;
  line-height: 1;
}
.lc-stat-label {
  font-size: 0.8em;
  color: #888;
  margin-top: 4px;
}
</style>

> 收录 LeetCode 精选 100 道高频算法题，按知识点分类整理，附每题链接与难度标注。

<div class="lc-stats">
  <div class="lc-stat">
    <div class="lc-stat-num" style="color:#4a6cf7">100</div>
    <div class="lc-stat-label">总题数</div>
  </div>
  <div class="lc-stat">
    <div class="lc-stat-num" style="color:#00b8a3">17</div>
    <div class="lc-stat-label">简单</div>
  </div>
  <div class="lc-stat">
    <div class="lc-stat-num" style="color:#ffb800">72</div>
    <div class="lc-stat-label">中等</div>
  </div>
  <div class="lc-stat">
    <div class="lc-stat-num" style="color:#ff375f">11</div>
    <div class="lc-stat-label">困难</div>
  </div>
</div>

<div class="lc-grid">

<a class="lc-card" href="/leetcode/hash/">
  <div class="lc-card-title">🔑 哈希</div>
  <div class="lc-card-sub">Hash Table</div>
  <div class="lc-badges">
    <span class="badge badge-total">3 题</span>
    <span class="badge badge-easy">简单 ×1</span>
    <span class="badge badge-medium">中等 ×2</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/two-pointers/">
  <div class="lc-card-title">👆 双指针</div>
  <div class="lc-card-sub">Two Pointers</div>
  <div class="lc-badges">
    <span class="badge badge-total">4 题</span>
    <span class="badge badge-easy">简单 ×1</span>
    <span class="badge badge-medium">中等 ×2</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/sliding-window/">
  <div class="lc-card-title">🪟 滑动窗口</div>
  <div class="lc-card-sub">Sliding Window</div>
  <div class="lc-badges">
    <span class="badge badge-total">2 题</span>
    <span class="badge badge-medium">中等 ×2</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/substring/">
  <div class="lc-card-title">🔍 子串</div>
  <div class="lc-card-sub">Substring</div>
  <div class="lc-badges">
    <span class="badge badge-total">3 题</span>
    <span class="badge badge-medium">中等 ×1</span>
    <span class="badge badge-hard">困难 ×2</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/array/">
  <div class="lc-card-title">📊 普通数组</div>
  <div class="lc-card-sub">Array</div>
  <div class="lc-badges">
    <span class="badge badge-total">5 题</span>
    <span class="badge badge-medium">中等 ×4</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/matrix/">
  <div class="lc-card-title">🗂️ 矩阵</div>
  <div class="lc-card-sub">Matrix</div>
  <div class="lc-badges">
    <span class="badge badge-total">4 题</span>
    <span class="badge badge-medium">中等 ×4</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/linked-list/">
  <div class="lc-card-title">🔗 链表</div>
  <div class="lc-card-sub">Linked List</div>
  <div class="lc-badges">
    <span class="badge badge-total">14 题</span>
    <span class="badge badge-easy">简单 ×5</span>
    <span class="badge badge-medium">中等 ×7</span>
    <span class="badge badge-hard">困难 ×2</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/binary-tree/">
  <div class="lc-card-title">🌲 二叉树</div>
  <div class="lc-card-sub">Binary Tree</div>
  <div class="lc-badges">
    <span class="badge badge-total">15 题</span>
    <span class="badge badge-easy">简单 ×6</span>
    <span class="badge badge-medium">中等 ×8</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/graph/">
  <div class="lc-card-title">🕸️ 图论</div>
  <div class="lc-card-sub">Graph</div>
  <div class="lc-badges">
    <span class="badge badge-total">4 题</span>
    <span class="badge badge-medium">中等 ×4</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/backtracking/">
  <div class="lc-card-title">↩️ 回溯</div>
  <div class="lc-card-sub">Backtracking</div>
  <div class="lc-badges">
    <span class="badge badge-total">8 题</span>
    <span class="badge badge-medium">中等 ×7</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/binary-search/">
  <div class="lc-card-title">🎯 二分查找</div>
  <div class="lc-card-sub">Binary Search</div>
  <div class="lc-badges">
    <span class="badge badge-total">6 题</span>
    <span class="badge badge-easy">简单 ×1</span>
    <span class="badge badge-medium">中等 ×4</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/stack/">
  <div class="lc-card-title">📚 栈</div>
  <div class="lc-card-sub">Stack</div>
  <div class="lc-badges">
    <span class="badge badge-total">5 题</span>
    <span class="badge badge-easy">简单 ×1</span>
    <span class="badge badge-medium">中等 ×3</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/heap/">
  <div class="lc-card-title">⛰️ 堆</div>
  <div class="lc-card-sub">Heap / Priority Queue</div>
  <div class="lc-badges">
    <span class="badge badge-total">3 题</span>
    <span class="badge badge-medium">中等 ×2</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/greedy/">
  <div class="lc-card-title">💰 贪心算法</div>
  <div class="lc-card-sub">Greedy</div>
  <div class="lc-badges">
    <span class="badge badge-total">4 题</span>
    <span class="badge badge-easy">简单 ×1</span>
    <span class="badge badge-medium">中等 ×3</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/dp/">
  <div class="lc-card-title">🧮 动态规划</div>
  <div class="lc-card-sub">Dynamic Programming</div>
  <div class="lc-badges">
    <span class="badge badge-total">10 题</span>
    <span class="badge badge-easy">简单 ×2</span>
    <span class="badge badge-medium">中等 ×7</span>
    <span class="badge badge-hard">困难 ×1</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/multi-dp/">
  <div class="lc-card-title">📐 多维动态规划</div>
  <div class="lc-card-sub">Multidimensional DP</div>
  <div class="lc-badges">
    <span class="badge badge-total">5 题</span>
    <span class="badge badge-medium">中等 ×5</span>
  </div>
</a>

<a class="lc-card" href="/leetcode/tricks/">
  <div class="lc-card-title">✨ 技巧</div>
  <div class="lc-card-sub">Tricks & Bit Manipulation</div>
  <div class="lc-badges">
    <span class="badge badge-total">5 题</span>
    <span class="badge badge-easy">简单 ×2</span>
    <span class="badge badge-medium">中等 ×3</span>
  </div>
</a>

</div>

---

题目来源：[LeetCode 精选 100 道](https://leetcode.cn/studyplan/top-100-liked/)
