venv 是 Python 自带的模块，用于创建轻量级的虚拟环境。使用虚拟环境可以让你在不同项目中隔离依赖，避免包冲突。下面是 venv 的使用方法，涵盖创建、激活、安装依赖和管理虚拟环境的基本步骤。

- 1. 创建虚拟环境
要创建一个新的虚拟环境，可以使用以下命令：

```python3 -m venv <env_name>```

其中 <env_name> 是你想要给虚拟环境起的名字。例如，创建一个名为 myenv 的虚拟环境：

```python3 -m venv myenv```

这将在当前目录下创建一个名为 myenv 的文件夹，里面包含了 Python 解释器和 pip 工具。

- 2. 激活虚拟环境

创建虚拟环境后，你需要激活它。根据你所使用的操作系统，激活命令有所不同：

在 Linux 或 macOS 上：

```source myenv/bin/activate```

在 Windows 上：

```myenv\Scripts\activate```

激活后，你会看到命令提示符前面有虚拟环境的名称（例如 (myenv)），表示你现在处于该虚拟环境中。

- 3. 安装依赖

在激活的虚拟环境中，你可以使用 pip 安装所需的依赖包。例如，要安装 FastAPI 和 uvicorn：

```pip install fastapi uvicorn```

你可以使用 pip list 查看当前虚拟环境中安装的所有包。

- 4. 生成依赖文件

如果你想要记录当前环境中的所有依赖，可以使用 pip freeze 命令生成一个 requirements.txt 文件：

```pip freeze > requirements.txt```
- 5. 从依赖文件安装依赖

如果你有一个 requirements.txt 文件，可以使用以下命令在虚拟环境中安装所有列出的包：

```pip install -r requirements.txt```
- 6. 退出虚拟环境

完成工作后，可以通过以下命令退出虚拟环境：

```deactivate```
- 7. 删除虚拟环境

如果不再需要某个虚拟环境，只需删除其对应的文件夹即可。例如，要删除名为 myenv 的虚拟环境，可以直接使用命令：

```rm -rf myenv```


基本目录结构
```
my_project/
│
├── myenv/                 # 虚拟环境目录
│   ├── bin/               # 可执行文件（包括 Python 解释器）
│   ├── lib/               # 安装的依赖库
│   └── ...                # 其他虚拟环境相关文件
│
├── app/                   # 项目代码目录
│   ├── __init__.py
│   ├── main.py            # 项目主文件
│   └── ...
│
├── tests/                 # 测试代码目录
│   ├── test_main.py
│   └── ...
│
├── requirements.txt       # 依赖文件（可选）
├── .gitignore             # Git忽略文件（如果使用Git）
└── README.md              # 项目说明文件
```
