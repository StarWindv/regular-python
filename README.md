# Regular Python (repy) 🐍

[![PyPI Version](https://img.shields.io/pypi/v/stv_repy.svg)](https://pypi.org/project/stv_repy/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/starwindv/regular-python/blob/main/LICENSE)

> 一个专为Windows优化的Python通配符执行工具，弥补原生shell不支持`python /*/tar*get.py`的不足，支持多级目录匹配操作。

> 仅支持Windows环境

> 让Python通配符执行像呼吸一样自然 🌟

---

## ✨ 功能特性

- **通配符解析**  
  - 支持 `*.py`、`src/**/test_*.py` 等复杂模式
  - 自动转换为正则表达式，适配Windows大小写不敏感文件系统
- **多层级递归匹配**  
  - 通过 `--rp-allow-multiple` 允许`*`跨多级目录匹配
- **无缝参数传递**  
  - 支持向被运行脚本传递参数（如`-- args`）

---

## 📦 安装

### 通过PyPI安装
```bash
pip install stv_repy
```

### 从源码安装
```bash
git clone https://github.com/StarWindv/regular-python.git
cd regular-python
pip install .
```

---

## 🚀 使用指南

### 基本命令
```bash
repy [--rp-选项] <路径模式> [-- Python参数]
```

### 主要参数说明
| 选项                            | 说明                  |
|-------------------------------|---------------------|
| `-rh`, `--rp-help`            | 显示帮助信息              |
| `-ram`, `--rp-allow-multiple` | 允许多级通配符（如`**/*.py`） |

### 示例
#### 1. 执行当前目录所有Python文件
```bash
repy *.py
```

#### 2. 多级目录匹配测试文件
```bash
repy --rp-allow-multiple tests/**/*_test.py args
```

#### 3. 跨盘符匹配并传递参数
```bash
repy D:/*/*/*/target.py args
```

#### 4. 显示帮助信息
```bash
repy --rp-help
```

#### 5. 向Python解释器和脚本同时传参
```bash
repy D:/*/*/*/target.py script_args -- python_args
```

---

## ⚠️ 注意事项

1. **路径空格处理**  
   若路径含空格，需用双引号包裹（如`"My Project/*.py"`）。

2. **性能提示**  
   深层目录匹配（如`**/*.py`）因设备原因可能较慢，建议结合具体层级限制。

3. **特殊字符转义**  
   尽可能避免在路径模式中使用特殊符号，或手动转义。

---

## 🤝 贡献指南

欢迎提交Issue或PR!
希望您能完善正则匹配模式！

---

## 📜 许可证

[MIT License](https://github.com/starwindv/regular-python/blob/main/LICENSE) © 2025 StarWindv (星灿长风v)  
📧 联系作者：[starwindv.stv@gmail.com](mailto:starwindv.stv@gmail.com)
