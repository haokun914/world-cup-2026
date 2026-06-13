# 🏆 World Cup 2026 Dashboard

**实时世界杯数据可视化平台** — 3D 地球仪 · 赛程比分 · 积分榜 · 赛事预测 · AI 助手

🌐 **[在线访问 →](https://skyseraph.github.io/world-cup-2026/)**

---

## 预览

| 3D 地球仪 | 赛程 & 比分 | 积分榜 | AI 助手 |
|:---------:|:----------:|:------:|:-------:|
| 48国标记 + 小组配色 | 实时赛果 + 时间线详情 | 12小组完整榜单 | Claude 驱动分析 |

---

## 功能

- **3D 地球仪** — 48 支参赛队在地图上实时标注，按小组着色，点击查看球队详情
- **赛程 & 比分** — 覆盖 ±4 天赛事，支持点击查看完整比赛时间线（进球 / 换人 / 黄红牌）
- **积分榜** — 12 个小组实时排名，带积分 / 净胜球 / 近期状态
- **赛事预测** — 基于积分榜 + 近期状态生成胜负概率，展示对比分析
- **AI 助手** — 内置 Claude 聊天，使用自己的 Anthropic API Key，密钥仅存于本地
- **中英双语** — 一键切换，默认中文

---

## 数据更新

GitHub Actions 每 **30 分钟**自动抓取最新赛事数据并提交到仓库，页面无需后端即可保持实时。

```
fetch-data.yml   → 抓取赛程 / 积分 / 时间线 → 写入 data/*.json
deploy.yml       → push 后自动部署到 GitHub Pages
```

数据来源：[sports-skills](https://github.com/machina-sports/sports-skills) (ESPN API，无需 Key)

---

## 本地运行

```bash
# 克隆仓库
git clone https://github.com/skyseraph/world-cup-2026.git
cd world-cup-2026

# 直接用任意静态服务器打开（无需 Node/构建工具）
npx serve .
# 或
python3 -m http.server 8080
```

访问 `http://localhost:8080`

### 手动刷新数据

```bash
pip install sports-skills
python3 scripts/fetch_data.py
```

---

## 技术栈

| 层 | 技术 |
|----|------|
| 前端 | 纯 HTML + ES Modules，无构建工具 |
| 3D 渲染 | Three.js v0.165 (CDN importmap) |
| 数据管道 | GitHub Actions + Python sports-skills CLI |
| 部署 | GitHub Pages (静态) |
| AI | Anthropic Claude API (浏览器直连，Key 存 localStorage) |

---

## 赛事信息

- **赛制**：48 队，12 小组，小组赛 + 淘汰赛
- **举办地**：美国 / 加拿大 / 墨西哥
- **时间**：2026 年 6 月 11 日 — 7 月 19 日

---

<div align="center">
  <sub>数据每 30 分钟自动更新 · Powered by Claude + Three.js + GitHub Actions</sub>
</div>
