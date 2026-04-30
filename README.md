<div align="center">

# Elaina-plugins

ElainaBot 官方插件市场 — 在这里发现和分享插件

[![ElainaBot](https://img.shields.io/badge/框架-ElainaBot_v2-blue)](https://github.com/ElainaCore/ElainaBot_v2)
[![QQ群](https://img.shields.io/badge/QQ交流群-1085402468-blue)](https://qm.qq.com/q/5O3xGoe4so)

</div>

## 📦 插件列表

| 插件名 | 作者 | 描述 | 分类 |
|--------|------|------|------|
| *等待你的 PR* | — | — | — |

> 插件列表自动从 [`plugins.json`](plugins.json) 读取，Web 面板实时展示。

## 🚀 如何安装插件

### 方式一：Web 面板 (推荐)

1. 打开 ElainaBot Web 面板
2. 进入「插件市场」页面
3. 浏览或搜索插件
4. 点击「安装」即可

### 方式二：手动安装

```bash
cd ElainaBot_v2/plugins
git clone https://github.com/作者/插件仓库.git 插件名
```

## 🔌 如何提交插件

### 第一步：准备你的插件仓库

你的插件是一个独立的 GitHub 仓库，结构如下：

**大型插件** (含入口文件)：
```
你的仓库/
├── main.py              # 入口文件 (必须)
├── app/                 # 子模块目录
│   ├── feature_a.py
│   └── feature_b.py
├── data/                # 数据目录 (可选)
└── requirements.txt     # 额外依赖 (可选)
```

**小型插件** (单文件)：
```
你的仓库/
└── my_plugin.py         # 插件文件
```

### 第二步：添加插件元数据

在入口文件中声明 `__plugin_meta__`：

```python
__plugin_meta__ = {
    'name': '我的插件',
    'author': '你的名字',
    'description': '插件功能描述',
    'version': '1.0.0',
    'github': 'https://github.com/你的用户名/你的仓库',
}
```

### 第三步：提交 PR

1. Fork 本仓库
2. 编辑 `plugins.json`，添加你的插件信息
3. 提交 Pull Request

### `plugins.json` 格式

```json
[
  {
    "name": "插件目录名",
    "author": "作者",
    "description": "插件描述",
    "version": "1.0.0",
    "category": "分类",
    "github": "https://github.com/你的用户名/你的仓库",
    "branch": "main",
    "tags": ["标签1", "标签2"]
  }
]
```

#### 字段说明

| 字段 | 必填 | 说明 |
|------|------|------|
| `name` | ✅ | 插件名，安装后的目录名 `plugins/<name>` |
| `author` | ✅ | 作者名 |
| `description` | ✅ | 插件描述 |
| `version` | ✅ | 版本号 |
| `category` | ✅ | 分类 (工具/娱乐/管理/查询/其他) |
| `github` | ✅ | GitHub 仓库地址 |
| `branch` | ❌ | 分支名，默认 `main` |
| `path` | ❌ | 仓库内文件路径 (单文件插件用，如 `plugins/hello/hello.py`) |
| `tags` | ❌ | 标签数组，用于搜索 |

#### 两种安装模式

**仓库型** — 整个仓库拉取解压到 `plugins/<name>/`：
```json
{
  "name": "my-plugin",
  "github": "https://github.com/user/my-plugin",
  "branch": "main"
}
```

**单文件型** — 一个仓库包含多个小插件，通过 `path` 指定：
```json
{
  "name": "hello",
  "github": "https://github.com/ElainaCore/Elaina-plugins",
  "path": "plugins/hello/hello.py",
  "branch": "main"
}
```

## 📋 提交规范

- 插件必须是独立可用的，不依赖其他第三方插件
- 额外 pip 依赖请在仓库中提供 `requirements.txt`
- 插件代码中必须包含 `__plugin_meta__` 元数据
- 禁止提交恶意代码、违法内容

## 📄 License

MIT License
