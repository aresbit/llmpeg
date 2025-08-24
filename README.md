# llmpeg - AI驱动的FFmpeg命令生成器

`llmpeg` 是一个智能命令行工具，通过AI大模型将自然语言描述转换为FFmpeg命令，让你无需记忆复杂的FFmpeg语法即可完成音视频处理任务。

## ✨ 功能特性

- **自然语言转FFmpeg命令**：用中文或英文描述需求，自动生成对应命令
- **多AI模型支持**：支持DeepSeek和Kimi(Moonshot AI)两种大模型
- **智能文件名**：自动为输出文件生成有意义的名称
- **同目录输出**：输出文件默认保存在输入文件同目录下
- **执行确认**：显示生成的命令，确认后才执行，避免误操作

## 🚀 安装方法

1. 克隆仓库：
   ```bash
   git clone https://github.com/aresbit/llmpeg.git
   cd llmpeg
   ```

2. 赋予执行权限：
   ```bash
   chmod +x llmpeg
   ```

3. 将文件移动到系统PATH：
   ```bash
   sudo mv llmpeg /usr/local/bin/
   ```

## 🔑 API密钥配置

### 使用DeepSeek（推荐）
```bash
export DEEPSEEK_API_KEY="你的DeepSeek API密钥"
```

### 使用Kimi(Moonshot AI)
```bash
export KIMI_API_KEY="你的Moonshot AI API密钥"
```

**建议**：将上述命令添加到 `~/.bashrc` 或 `~/.zshrc` 中，使其永久生效。

## 📖 使用示例

### 基础用法
```bash
llmpeg 从example.mp4中提取音频
llmpeg 将test.mov转换为mp4格式
llmpeg 压缩video.mp4，保持质量的同时减小文件大小
```

### 高级用法
```bash
# 调整视频分辨率
llmpeg 将input.mp4分辨率调整为1920x1080

# 添加字幕
llmpeg 给movie.mp4添加chinese.srt字幕文件

# 裁剪视频片段
llmpeg 裁剪video.mp4从00:01:30到00:03:45的片段

# 调整播放速度
llmpeg 将clip.mp4播放速度调整为0.5倍慢放

# 提取视频帧
llmpeg 从animation.mp4中提取每秒一帧图片
```

## 🎯 支持的操作类型

- 格式转换（MP4, MOV, AVI, MKV, WebM等）
- 音频提取与合并
- 视频压缩与质量调整
- 分辨率与帧率调整
- 视频裁剪与合并
- 字幕添加与提取
- 播放速度调整
- 音频/视频分离与重新编码
- 图片序列与视频互转

## ⚠️ 注意事项

1. **使用前请确认**：工具会显示生成的FFmpeg命令，按Enter执行，Ctrl+C取消
2. **文件路径**：建议使用相对路径或绝对路径，避免中文路径
3. **大文件处理**：大文件处理可能需要较长时间，请耐心等待
4. **备份原文件**：重要文件请先备份，避免意外覆盖

## 🔧 依赖要求

- **FFmpeg**：必须预先安装FFmpeg
  - Ubuntu/Debian: `sudo apt install ffmpeg`
  - macOS: `brew install ffmpeg`
  - Windows: 从[FFmpeg官网](https://ffmpeg.org/download.html)下载

- **curl**：用于API调用（通常系统已预装）

## 🛠️ 故障排除

### 常见问题

1. **"No API key found"错误**
   - 确保已设置 `DEEPSEEK_API_KEY` 或 `KIMI_API_KEY`
   - 运行 `echo $DEEPSEEK_API_KEY` 检查环境变量

2. **FFmpeg命令执行失败**
   - 检查文件路径是否正确
   - 确认FFmpeg已安装：`ffmpeg -version`

3. **API调用失败**
   - 检查网络连接
   - 确认API密钥有效且有足够余额

## 🤝 贡献指南

欢迎提交Issue和Pull Request！如果你发现了问题或有改进建议，请通过以下方式参与：

1. Fork本项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建Pull Request

## 📄 许可证

本项目采用MIT许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🌟 致谢

- 感谢DeepSeek和Moonshot AI提供强大的AI模型
- 感谢FFmpeg社区提供的优秀多媒体处理框架
