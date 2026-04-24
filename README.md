# 学霸帝AI 

基于 Qwen2.5-VL + llama.cpp 的本地多模态AI助手，支持纯文本对话和图片视觉问答。

## 功能特性

- 🤖 **本地运行** - 无需联网，保护隐私
- 🖼️ **视觉问答** - 支持图片上传/拖拽，进行图像理解
- 📦 **一键打包** - 单文件 EXE，开箱即用
- 🇨🇳 **国内镜像** - 模型从 ModelScope 下载，速度更快
- 💻 **GPU 加速** - 支持 CUDA 加速推理（需 NVIDIA 显卡）

## 快速开始

### 方式一：直接运行源码

```bash
# 1. 克隆仓库
cd xueba-ai

# 2. 安装依赖
pip install -r requirements.txt

# 3. 运行
python main.py
```

### 方式二：构建 EXE（推荐）

```bash
# 运行构建脚本
build.bat
```

构建完成后，在 `dist/学霸帝AI.exe` 找到可执行文件。

## 首次使用

1. 启动应用后，如未检测到模型，会显示下载面板
2. 点击「开始下载」，从 ModelScope 下载 Qwen2.5-VL-3B 模型（约 2GB）
3. 下载完成后点击「加载模型」
4. 开始对话！支持拖拽图片进行视觉问答

## 模型信息

- **模型**: Qwen2.5-VL-3B-Instruct-q4_k_m.gguf
- **来源**: [ModelScope](https://www.modelscope.cn/models/aplux/Qwen2.5-VL-3B-Instruct-q4_k_m)
- **大小**: 约 2GB
- **量化**: Q4_K_M（平衡速度与质量）
- **上下文**: 4096 tokens

## 系统要求

- Windows 10/11 64位
- 内存: 8GB+（推荐 16GB）
- 磁盘: 5GB 可用空间
- GPU: 可选，支持 NVIDIA CUDA 加速

## GPU 加速（可选）

如需 GPU 加速，重新安装 llama-cpp-python：

```bash
# NVIDIA GPU
set CMAKE_ARGS=-DGGML_CUDA=on
pip install llama-cpp-python --force-reinstall --no-cache-dir
```

## 项目结构

```
xueba-ai/
├── main.py              # 入口文件
├── requirements.txt     # Python 依赖
├── build.bat           # Windows 构建脚本
├── README.md           # 说明文档
├── core/               # 核心模块
│   ├── __init__.py
│   ├── model_manager.py   # 模型下载管理
│   └── llm_engine.py      # LLM 推理引擎
└── ui/                 # UI 模块
    ├── __init__.py
    └── main_window.py       # 主窗口
```

## 许可证

MIT License
