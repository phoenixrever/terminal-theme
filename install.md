---
## ✅ 实现方式：**手动复制 `.json` 配色到 settings.json**

### 步骤说明如下：
---

### 🔧 步骤一：找到主题 JSON 文件

1. 打开 GitHub 或 VSCode 插件页面里的 `themes/*.json` 文件，比如这个主题的 JSON 路径：

   ```
   https://github.com/berthomejulien/material-theme-oceanic-custom/blob/master/themes/Material-Theme-Oceanic-Custom-color-theme.json
   ```

2. 点击“Raw”查看原始 JSON 内容，复制全部内容。

---

### 📁 步骤二：提取关键信息

VSCode 的颜色自定义设置支持以下两类：

- `workbench.colorCustomizations`: 控制编辑器界面、背景等
- `editor.tokenColorCustomizations`: 控制代码语法高亮（也就是 `tokenColors`）

所以我们只需要提取出你复制的 JSON 文件中的两个字段：

```json
{
  "type": "dark",
  "colors": { ... },                ← 提取到 workbench.colorCustomizations
  "tokenColors": [ ... ]           ← 提取到 editor.tokenColorCustomizations
}
```

---

### 🛠 步骤三：粘贴到你的 `settings.json`

打开 VSCode 的 `settings.json`：

1. `Ctrl + Shift + P` → 搜索 `Preferences: Open Settings (JSON)`
2. 把下面格式粘贴进去（记得你替换成自己的 JSON 里的 `colors` 和 `tokenColors`）

```json
{
  "workbench.colorCustomizations": {
    // 替换成 themes json 里的 "colors": {...} 内容
  },
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      // 替换成 themes json 里的 "tokenColors": [ ... ] 内容
    ]
  }
}
```

---

### ✅ 示例（简化版 Material Oceanic）

这是从 `Material Theme Oceanic Custom` 提取的一小段示例（完整配色你可以从 themes JSON 中复制）：

```json
{
  "workbench.colorCustomizations": {
    "editor.background": "#263238",
    "editor.foreground": "#EEFFFF",
    "editorLineNumber.foreground": "#546E7A"
  },
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "scope": "comment",
        "settings": {
          "foreground": "#546E7A",
          "fontStyle": "italic"
        }
      },
      {
        "scope": "keyword",
        "settings": {
          "foreground": "#C792EA"
        }
      },
      {
        "scope": "string",
        "settings": {
          "foreground": "#C3E88D"
        }
      }
    ]
  }
}
```

你只要把原始 `JSON` 中的 `"colors"` 和 `"tokenColors"` 替换进来即可。

---

### 🎁 如果你需要帮助我可以：

- 帮你从某个具体主题 JSON 页面提取
- 生成完整的可粘贴 `settings.json` 模板
- 或者生成 `.json` 文件你直接导入

"workbench.colorCustomizations": {
"tab.activeBorder": "#ff0000",
"tab.activeBackground": "#114d25",
}
