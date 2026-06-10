# DB Folder (Modified)

基于 [RafaelGB/obsidian-db-folder](https://github.com/RafaelGB/obsidian-bd-folder) v3.5.1 的修改版。

## 新增功能

### 元数据列筛选

在筛选弹窗中支持以下 Dataview 元数据列的筛选：

- `__created__` — 文件创建时间
- `__modified__` — 文件修改时间
- `__tags__` — 标签
- `__tasks__` — 任务
- `__outlinks__` — 出链
- `__inlinks__` — 入链

### 命名日期引用

`__created__` 和 `__modified__` 列支持命名日期引用进行范围筛选：

- `@today` — 今天
- `@yesterday` — 昨天
- `@thisweek` — 本周
- `@lastweek` — 上周
- `@thismonth` — 本月
- `@lastmonth` — 上月
- `@thisyear` — 今年

例如：`__created__` is `@thisweek` 可筛选本周创建的所有文件。

## 修改详情

| 修改点 | 文件位置 | 说明 |
|--------|---------|------|
| `V2e` | main.js | 使用 `getRowDataType(columns)` 替代 `getAllRowDataType()`，将元数据列包含进筛选数据 |
| `$Tr` | main.js | 仅排除 `__note__` 键，不再过滤所有 `__*__` 格式的键 |
| `s()` (JQ) | main.js | `__created__` 和 `__modified__` 自动识别为 CALENDAR 类型 |
| `calendarAtomicFilter` | main.js | EQUAL 运算符改用范围比较，适配浮点差值 |
| `validateAtomicFilter` | main.js | `@` 前缀值自动路由到日历筛选器 |

## 安装

将 `main.js`、`manifest.json`、`styles.css` 复制到 vault 的 `.obsidian/plugins/dbfolder/` 目录下，重启 Obsidian 即可。
