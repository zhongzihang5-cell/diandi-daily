# 点滴日报

美柚 · 点滴的日次分析报表，通过 GitHub Pages 在线访问。

## 在线地址

部署完成后访问：

`https://zhongzihang5-cell.github.io/diandi-daily/`

可通过 URL 参数直接打开指定日期（默认最新 8/27）：

- `?date=827` — 8月27日
- `?date=826` — 8月26日
- `?date=825` — 8月25日

也支持 `?sfx=827` 写法。

（首次发布可能需等待 1–2 分钟）

## 怎么改数据

所有内容和数据都在单个文件 `index.html` 里。

### 方式一：在 GitHub 网页上直接改（最方便）

1. 打开仓库里的 `index.html`
2. 点右上角铅笔图标（Edit）
3. 改数字或文案
4. 底部点「Commit changes」保存 → 几十秒到几分钟后网站自动更新

### 方式二：本地改完再推送

```bash
git clone https://github.com/zhongzihang5-cell/diandi-daily.git
cd diandi-daily
# 编辑 index.html
git add index.html
git commit -m "更新日报数据"
git push
```

## 数据在文件里的位置

- **KPI 卡片 / 漏斗 / 条形图**：在 HTML 上半部分，搜索 `class="kpi"`、`class="funnel"`、`class="bar"`
- **折线图数据**：页面底部 `<script>` 里的变量
  - `CH0`：数据总览页图表
  - `CH1`：记录习惯页图表
  - `CH2`：留存表现页图表
- **分记录类型日数据**：`RT` 变量，格式为 `[日期, 文本, 快捷, 语音, 饮食]`

示例（改 `CH0` 里的记录人数）：

```js
"records":{"title":"点滴记录人数","fmt":"int","series":[{"name":"记录","color":"#ef2f6b",
  "data":[["8/18",0.0],["8/19",0.0],["8/20",19.0],["8/25",100.0]]}]}
```

只需增删或修改 `["日期", 数值]` 这一对，图表就会跟着变。
