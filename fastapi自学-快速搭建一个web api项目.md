# 1、安装FastApi

```python -m pip install fastapi uvicorn[standard]```

# 2、Python FastApi完整项目
将相同的结构和配置应用于最小的FastApi项目。其中包含一下功能：
- 1、项目的虚拟环境
- 2、目录结构， 分为不同的模块和文件
- 3、使用```ruff```和```mypy```等工具进行代码格式化
- 4、使用pytest等框架进行自动化测试，与版本控制和GitHub集成。
下面的清单并排显示了应用perfect Python project模板项目的结构：
```
my_fastapi_project/
├── app/
│   ├── api/
│   │   ├── __init__.py
│   │   ├── endpoints/
│   │   │   ├── __init__.py
│   │   │   ├── users.py
│   │   │   ├── items.py
│   │   ├── dependencies.py
│   ├── core/
│   │   ├── __init__.py
│   │   ├── config.py
│   │   ├── security.py
│   ├── db/
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── schemas.py
│   │   ├── session.py
│   ├── services/
│   │   ├── __init__.py
│   │   ├── user_service.py
│   │   ├── item_service.py
│   ├── main.py
│   ├── tests/
│   │   ├── __init__.py
│   │   ├── test_main.py
│   │   ├── test_users.py
│   │   ├── test_items.py
├── .env
├── .gitignore
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── README.md

```

目录结构说明
app/: 主应用程序目录。
api/: 包含 API 相关的模块。
endpoints/: 包含各个 API 端点的模块。
dependencies.py: 包含 API 依赖项的模块。
core/: 包含核心配置和安全相关的模块。
config.py: 包含应用程序配置。
security.py: 包含安全相关的功能，如密码哈希、JWT 处理等。
db/: 包含数据库相关的模块。
models.py: 包含数据库模型。
schemas.py: 包含 Pydantic 模型（用于数据验证和序列化）。
session.py: 包含数据库会话管理。
services/: 包含业务逻辑服务的模块。
main.py: 应用程序的入口点。
tests/: 包含测试相关的模块。
.env: 包含环境变量配置。
.gitignore: 指定 Git 忽略的文件和目录。
requirements.txt: 包含项目依赖的 Python 包。
Dockerfile: 用于构建 Docker 镜像。
docker-compose.yml: 用于定义和运行多容器 Docker 应用程序。
README.md: 项目说明文档。

# 3、安装依赖
主要的库：
- FastApi
- Loguru是一个旨在使日志记录更愉快的库
- python-dotenv从.env文件中读取name=value对，并设置响应的环境变量
- uvloop是一个高效的实现，它取代了asyncio中使用的默认解决方案

  # 4、重构main.py
  原始的main.py
