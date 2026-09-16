# 工作手记 — 任务日历 & 灵感库

一个零依赖的单页应用，用于记录工作细碎事项与灵感捕捉。所有数据保存在浏览器 localStorage 中，无需后端。

## 功能

### 工作页
- **任务日历**：月历网格视图，点击日期添加任务，支持优先级（高 / 中 / 低）、完成标记与删除
- **灵感库**：快速记录灵感，支持标签分类（想法 / 工作 / 学习 / 生活 / 待办）、颜色标记、搜索与标签筛选

### 生活页
- **生活待办记事板**：与工作任务分开的简单清单，按分类管理（购物 / 家务 / 健康 / 社交 / 其他）
- 进度条显示完成比例，支持标签筛选

### 通用
- 顶部 Tab 切换工作页 / 生活页，顶部固定显示当前日期
- 统计栏：今日任务数、已完成数、灵感总数

## 快捷键

| 快捷键 | 功能 |
| --- | --- |
| `Cmd/Ctrl + K` | 切到工作页并聚焦灵感输入框 |
| `Cmd/Ctrl + L` | 切到生活页并聚焦待办输入框 |
| `Esc` | 关闭弹窗 |

## 技术栈

- 纯 HTML + CSS + Vanilla JavaScript（单文件 `index.html`）
- 数据持久化：`localStorage`，key 为 `workbuddy_notes_v1`
- 无构建步骤、无第三方依赖

## 使用方式

直接用浏览器打开 `index.html` 即可。

也可以起一个本地静态服务：

```bash
python3 -m http.server 8080
# 然后访问 http://localhost:8080
```

## 数据结构

```js
{
  tasks:    [{ id, date, text, priority, done, created }],  // 工作任务
  ideas:    [{ id, text, tags, color, created }],           // 灵感库
  lifeTodos:[{ id, text, category, done, created }]         // 生活待办
}
```

## License

MIT
