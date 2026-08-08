# ✨ 智能待办清单

一个纯 HTML/CSS/JavaScript 单文件待办清单应用，无需后端、无需安装、无需依赖任何框架或 CDN，打开即用。

## 🌟 功能特性

### 任务管理
- **添加任务**：输入任务名 + 设置优先级（高/中/低）+ 开始/截止日期
- **4 段进度**：每个任务有 4 段独立进度，点击逐段点亮（25% → 50% → 75% → 100%）
- **一键完成**：点击左侧圆圈可一键点亮全部 4 段或重置
- **搜索 & 筛选**：支持关键字搜索 + 全部/未完成/已完成筛选
- **编辑任务**：点击任务可打开编辑模态框修改所有字段
- **删除任务**：悬停显示删除按钮，带滑出动画
- **已完成折叠**：已完成的任务自动折叠，点击展开

### 每日打卡
- 为任务开启「每日打卡」，设置间隔周期（每隔 N 天）
- 到了周期日自动重置进度，提示可打卡
- 打卡成功触发彩色粒子爆散 + 和弦音效
- 实时显示打卡状态（「今天可打卡」/「还有 X 天」/「已打卡」）

### 日程提醒
- 添加日程（指定日期 + 内容）
- 当天有日程时，顶部横幅滚动提醒
- 日程管理卡片：按日期排序、当天高亮、可删除

### 视觉与交互
- 🎨 **毛玻璃 UI**（glassmorphism）+ 渐变背景
- 🌙 **暗色模式**自适应（`prefers-color-scheme`）
- 🔊 **Web Audio API 音效**：添加、完成、删除、打卡、编辑等操作均有音效，可一键开关
- 🎉 **彩色粒子动画**：任务完成时触发 confetti 爆散
- 📊 **统计卡片**：全部 / 已完成 / 进行中 / 今日打卡
- 📈 **总进度条**：渐变色 + 流光动画
- 💾 **本地存储**：`localStorage` 持久化，刷新不丢失

### 布局
- 全屏铺满，充分利用宽屏空间
- 任务列表 ≥1100px 时自动双列并排
- 统计区和添加任务区保持紧凑居中

## 🚀 使用方法

1. 下载 `index.html`
2. 用浏览器打开
3. 开始管理你的待办事项！

> 无需联网（字体降级为系统字体，功能完整不受影响）

## 🛠️ 技术栈

- 纯 HTML5 + CSS3 + JavaScript（无框架、无库）
- Web Audio API（音效生成）
- localStorage（数据持久化）
- CSS Grid + Flexbox（响应式布局）
- CSS Custom Properties（主题变量）

## 📄 数据结构

```javascript
// 任务
{
  id: "uuid",
  text: "任务名称",
  priority: "high|medium|low",
  startDate: "YYYY-MM-DD",
  dueDate: "YYYY-MM-DD",
  stages: [false, false, false, false],  // 4 段进度
  completedAt: null | timestamp,
  createdAt: timestamp,
  checkIn: {
    enabled: false,
    intervalDays: 1,
    lastDoneAt: null | timestamp
  }
}

// 日程
{
  id: "uuid",
  date: "YYYY-MM-DD",
  text: "日程内容",
  createdAt: timestamp
}
```

## 📝 License

MIT
