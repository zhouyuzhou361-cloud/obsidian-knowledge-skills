# 首页模板

根据 navigation.mode 选择一种模板，并替换 paths 与 writing.field_map 对应字段。不要将两种形式重复写入同一首页。

## 普通 Markdown

```markdown
# 知识库总导航

## 分类导航

| 分类 | 说明 | 入口 |
|------|------|------|

## 系统工具

| 工具 | 说明 |
|------|------|

## 快速入口

| 入口 | 说明 |
|------|------|

## 最近更新

只列已核实的最近修改笔记；没有修改时间时暂不生成。
```

## Obsidian Dataview

此形式需要 Dataview，JavaScript 查询需要在用户环境中已启用；技能不自动更改插件设置。表中路径与字段为默认示例。更新 cats 时使用 JSON 序列化，不直接插入来源文本；不得添加网络请求、动态代码执行或未经核实的嵌入。

````markdown
# 🏠 知识库总导航

## 分类导航

```dataviewjs
const cats = [];
// 每项：{ emoji, name, nav, dir, desc }
dv.table(["分类", "说明", "笔记数"], cats.map(c => [
  `${c.emoji || ""} ${dv.fileLink(c.nav, false, c.name)}`,
  c.desc,
  dv.pages(JSON.stringify(c.dir)).where(p => !p.file.name.includes("📌")).length
]));
```

## 系统工具

| 工具 | 说明 |
|------|------|

## 快速入口

| 入口 | 说明 |
|------|------|

## 最近更新

```dataview
TABLE WITHOUT ID file.link AS "笔记", summary AS "一句话"
FROM "知识库"
WHERE !contains(file.name, "📌")
SORT file.mtime DESC
LIMIT 10
```
````
