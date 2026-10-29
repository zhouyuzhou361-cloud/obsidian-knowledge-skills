# 分类导航模板

按照 navigation.mode 选择一种形式。替换分类名称、实际知识目录、navigation.marker 和 writing.field_map 中的 summary/difficulty；分组名称使用 writing.difficulty_values。emoji 关闭时使用普通标题。

## 普通 Markdown

```markdown
# 某分类 导航

## 入门

- [笔记标题](已核实的相对路径.md)：一句话总结

## 进阶

只列确实存在的笔记。

## 专题

只列确实存在的笔记。
```

## Obsidian Dataview

只在用户使用 Dataview 时采用。下例为默认字段和路径：

````markdown
# 📌 [分类名] 导航

## 🟢 入门推荐

```dataview
TABLE WITHOUT ID file.link AS "笔记", summary AS "一句话"
FROM "知识库/[分类名]"
WHERE difficulty = "入门"
SORT file.name ASC
```

## 🟡 进阶深入

```dataview
TABLE WITHOUT ID file.link AS "笔记", summary AS "一句话"
FROM "知识库/[分类名]"
WHERE difficulty = "进阶"
SORT file.name ASC
```

## 🔴 专题参考

```dataview
TABLE WITHOUT ID file.link AS "笔记", summary AS "一句话"
FROM "知识库/[分类名]"
WHERE difficulty = "专题"
SORT file.name ASC
```
````
