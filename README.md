# dawn_shuttle

`dawn_shuttle` 是一个基于 [PEP 420](https://peps.python.org/pep-0420/) 隐式命名空间包机制的 Python 项目模板仓库。

## 特性

- 使用 `dawn_shuttle` 作为顶级命名空间包（无 `__init__.py`，遵循 PEP 420）
- 支持 Python 3.10+
- 使用 [Hatchling](https://hatch.pypa.io/) 作为构建后端
- 集成 [mypy](https://mypy.readthedocs.io/) 静态类型检查
- 集成 [Ruff](https://docs.astral.sh/ruff/) 代码风格检查与格式化
- 许可证：GNU 宽松通用公共许可证 v2.1（LGPL-2.1）

## 快速开始

### 使用模板初始化子项目

克隆此模板后，运行以下命令初始化子项目：

```bash
python init_project.py <子包名>
```

例如，创建一个名为 `web` 的子项目：

```bash
python init_project.py web
```

这将：

1. 将 `pyproject.toml` 中的项目名称修改为 `dawn_shuttle_web`
2. 在 `dawn_shuttle/` 目录下创建 `dawn_shuttle_web/` 包目录及 `__init__.py`

### 创建带额外目录结构的子项目

通过 `--dirs` 参数指定需要在包内创建的子目录：

```bash
python init_project.py web --dirs api models services
```

### 交互模式

使用 `-i` 启用交互模式，逐行输入目录名：

```bash
python init_project.py web -i
```

## 目录结构

```
dawn_shuttle/              # 顶级命名空间包（无 __init__.py）
    dawn_shuttle_<name>/   # 子项目包（由 init_project.py 生成）
        __init__.py
        [自定义子目录]/
pyproject.toml             # 项目配置（mypy / ruff / hatchling）
init_project.py            # 项目初始化脚本
CHANGELOG.md               # 版本变更说明
CONTRIBUTING.md            # 贡献指南
LICENSE                    # GNU LGPL v2.1
```

## 开发

安装开发依赖并运行检查：

```bash
pip install -e ".[dev]"
mypy dawn_shuttle
ruff check .
ruff format .
```

## 许可证

本项目使用 [GNU 宽松通用公共许可证 v2.1](LICENSE)。

