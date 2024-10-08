# 2024秋学期ブートキャンプ

### Author:
* Liu Xiaoyang
### Description
2024年、新しく入ってきた3年生向けの「ブートキャンプ」。
内容は主に深層学習。

### Dependencies
* Docker

### このリポジトリの使い方
**このリポジトリは[このテンプレート](https://github.com/LinhMuks-DFox/DeepLearning-Template)を使って作成した。** なので、C++を用いて深層学習開発のパーツも入っている。　
For both C++ and Python development, build the Docker container first:

1. Docker環境作成用のファイルが保存しているPathにナビゲート。
    ```bash
    cd docker/[cpu/gpu]
    ```
2. Dockerのコンテナを作成する:
    ```bash
    docker compose build
    ```
3. 必要なライブラリをDownload:
    ```bash
    ./download_dep.sh
    ```
    This script will download `fmt` and `libtorch`, and use `poetry` to install Python dependencies.

### VS Code Container Development Support
Configuration files for VS Code container development are placed in the `.devcontainer/` and `.vscode/` directories.

### Development Rules
1. Place all C++ source files in directories starting with `pp`, such as `pp_src`, except for the `include` directory.
2. Place all Python source files in directories starting with `py`, such as `py_src`.
3. Build C++ executables in the `build` directory. **Do not** build them in the workspace root directory.

### Adding Python Dependencies
This template uses `poetry` as the package manager for Python. To add a new library, use:
```bash
poetry add <your_lib>
```

### Running Python Code
Use `poetry` to run Python code:
```bash
poetry run python <your_code>
```