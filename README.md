# 项目文档生成器 (Project Overview Generator)

一个简单而强大的Python工具，用于自动生成项目的完整文档，包括项目结构树和所有代码文件的内容。

## ✨ 特性

- 🌳 **智能项目结构树** - 生成清晰的目录结构可视化
- 📄 **完整代码内容** - 包含所有源代码文件的内容
- 🚫 **智能过滤** - 自动忽略 `.git`、`node_modules`、`__pycache__` 等无关文件
- 🎨 **语法高亮** - 支持多种编程语言的Markdown语法高亮
- ⚙️ **高度可配置** - 轻松自定义忽略规则和输出格式
- 🚀 **一键运行** - 无需复杂配置，开箱即用

## 🎯 使用场景

- **代码审查** - 快速了解项目整体结构
- **项目交接** - 为新团队成员提供完整项目概览
- **AI辅助开发** - 为AI工具提供完整的项目上下文
- **文档生成** - 自动化项目文档维护
- **学习参考** - 分析开源项目结构

## 🚀 快速开始

### 安装要求

- Python 3.6+
- 无需额外依赖，使用标准库

### 使用方法

1. 将 `generate_project_overview.py` 下载到你的项目根目录
2. 运行脚本：

```bash
python generate_project_overview.py
```

3. 查看生成的 `project_overview.md` 文件

## 📋 输出示例

生成的文档包含两个主要部分：

### 项目结构
```
my-project/
├── src/
│   ├── main.py
│   └── utils.py
├── tests/
│   └── test_main.py
└── README.md
```

### 文件内容
每个文件的完整内容，带有适当的语法高亮：

````markdown
## `src/main.py`

```python
def main():
    print("Hello, World!")

if __name__ == "__main__":
    main()
```
````

## ⚙️ 配置选项

### 自定义忽略规则

编辑 `IGNORE_PATTERNS` 集合来添加或移除忽略规则：

```python
IGNORE_PATTERNS: Set[str] = {
    ".git", ".vscode", "__pycache__", "node_modules",
    "*.pyc", "*.log", "*.png", "*.jpg",
    # 添加你的自定义规则
    "custom_folder", "*.tmp"
}
```

### 支持的语言

脚本自动识别以下文件类型并应用相应的语法高亮：

- Python (`.py`)
- JavaScript/TypeScript (`.js`, `.ts`)
- HTML/CSS (`.html`, `.css`, `.scss`)
- JSON/YAML (`.json`, `.yaml`, `.yml`)
- Markdown (`.md`)
- Shell脚本 (`.sh`, `.bat`)
- 以及更多...

## 🔧 高级功能

### 性能优化
- 使用递归目录遍历，在遍历阶段就跳过被忽略的目录
- 智能模式分离（普通模式 vs 通配符模式）提升匹配效率

### 错误处理
- 优雅处理权限错误和编码问题
- 对二进制文件和无法读取的文件提供友好提示

## 📝 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## ⭐ 如果这个工具对你有帮助，请给个星标支持一下！

---

**作者**: [你的用户名]  
**项目主页**: [GitHub仓库链接]