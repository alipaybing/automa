# 小红书多关键词笔记采集 · Automa v5

在浏览器中按关键词搜索小红书笔记，收集链接，再逐篇读取页面可见内容，导出 JSON。仓库只保留 v5 工作流。

- [下载工作流 JSON](https://github.com/alipaybing/automa/raw/refs/heads/main/red_note_v5.json)
- [安装与使用教程](docs/tutorial.md)
- [Automa 官方安装页](https://chromewebstore.google.com/detail/automa/infppggnoaenmfagbfknfkancpbljcca)

## 快速开始

1. 在 Chrome 安装 Automa，登录小红书网页版。
2. 下载本仓库 `red_note_v5.json`，在 Automa 工作流列表中导入。
3. 运行 `rednote_v5_多关键词`，填入「关键词」和「每个关键词篇数」。首次建议 1 个关键词、3 篇。
4. 等待流程结束，检查浏览器下载目录中的 `red_note.json` 和 `red_note_links.json`。

多个关键词可用英文逗号、中文逗号、顿号或分号分隔。工作流原始默认值为「阿德莱德修车」、每词 30 篇；首次运行请手动调小。

## 导出字段

| 字段 | 内容 |
| --- | --- |
| keyword | 搜索关键词 |
| name | 笔记标题 |
| img | 当前可见图片的链接 |
| detail | 笔记正文 |
| edit_time | 页面展示的日期文本 |
| comments | 当前页面已加载的评论区域文本 |
| link | 笔记链接 |

`red_note_links.json` 保存收集到的链接对象（`id`、`kw`、`url`）。跨关键词按笔记 ID 去重；每词篇数为上限，实际结果可能较少。评论和图片仅取当前页面匹配内容，不代表完整评论或全部图片。

## 验证状态

2026-10-28：已检查 JSON 可解析、工作流节点与导出配置，保留原始 v5 内容。浏览器已经安装 Automa，但自动操作插件页面被浏览器安全策略阻止；完整的导入、3 篇实测及结果截图尚待补齐。当前不能据此宣称已完成端到端验证。

本流程依赖小红书页面结构和登录状态。页面变化、登录失效或访问限制可能导致空值或中断；遇到验证提示请停止并手动处理。导出节点使用覆盖同名文件的配置，保留历史结果请先改名。

## 目录

- `red_note_v5.json`：唯一保留的工作流。
- `docs/tutorial.md`：安装、导入、运行、结果说明。
- `docs/images/`：教程截图。

旧工作流和采集数据已完整备份至原码云仓库的 `backup/all-workflows-2026-10-28` 分支；未纳入此公开仓库。
