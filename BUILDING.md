# Building VoiceInk

This guide provides detailed instructions for building VoiceInk from source.

## Prerequisites

Before you begin, ensure you have:
- macOS 14.0 or later
- Xcode (latest version recommended)
- Swift (latest version recommended)

## Building whisper.cpp Framework

1. Clone and build whisper.cpp:
```bash
git clone https://github.com/ggerganov/whisper.cpp.git
cd whisper.cpp
./build-xcframework.sh
```
This will create the XCFramework at `build-apple/whisper.xcframework`.

## Building VoiceInk

1. Clone the VoiceInk repository:
```bash
git clone https://github.com/Beingpax/VoiceInk.git
cd VoiceInk
```

2. Add the whisper.xcframework to your project:
   - Drag and drop `../whisper.cpp/build-apple/whisper.xcframework` into the project navigator, or
   - Add it manually in the "Frameworks, Libraries, and Embedded Content" section of project settings

3. Build and Run
   - Build the project using Cmd+B or Product > Build
   - Run the project using Cmd+R or Product > Run

## Development Setup

1. **Xcode Configuration**
   - Ensure you have the latest Xcode version
   - Install any required Xcode Command Line Tools

2. **Dependencies**
   - The project uses [whisper.cpp](https://github.com/ggerganov/whisper.cpp) for transcription
   - Ensure the whisper.xcframework is properly linked in your Xcode project
   - Test the whisper.cpp installation independently before proceeding

3. **Building for Development**
   - Use the Debug configuration for development
   - Enable relevant debugging options in Xcode

4. **Testing**
   - Run the test suite before making changes
   - Ensure all tests pass after your modifications

## Troubleshooting

If you encounter any build issues:
1. Clean the build folder (Cmd+Shift+K)
2. Clean the build cache (Cmd+Shift+K twice)
3. Check Xcode and macOS versions
4. Verify all dependencies are properly installed
5. Make sure whisper.xcframework is properly built and linked

For more help, please check the [issues](https://github.com/Beingpax/VoiceInk/issues) section or create a new issue. 

# 构建 VoiceInk

本指南提供了从源代码构建 VoiceInk 的详细说明。

## 先决条件

开始之前，请确保您拥有
- macOS 14.0 或更高版本
- Xcode（建议使用最新版本）
- Swift（建议使用最新版本）

## 构建 whisper.cpp 框架

1.克隆并构建 whisper.cpp
```bash
git clone https://github.com/ggerganov/whisper.cpp.git
cd whisper.cpp
./build-xcframework.sh
```
这将在 `build-apple/whisper.xcframework` 中创建 XCFramework。

## 构建 VoiceInk

1.克隆 VoiceInk 仓库：
```bash
git clone https://github.com/Beingpax/VoiceInk.git
cd VoiceInk
```

2.将 whisper.xcframework 添加到项目中：
   - 将 `../whisper.cpp/build-apple/whisper.xcframework` 拖放到项目导航器中，或
   - 在项目设置的 "框架、库和嵌入内容 "部分手动添加

3.构建并运行
   - 使用 Cmd+B 或 "产品">"构建 "构建项目
   - 使用 Cmd+R 或 "产品">"运行 "运行项目

## 开发设置

1.**Xcode 配置**
   - 确保您拥有最新的 Xcode 版本
   - 安装任何所需的 Xcode 命令行工具

2.**依赖项***
   - 该项目使用 [whisper.cpp](https://github.com/ggerganov/whisper.cpp) 进行转录
   - 确保在您的 Xcode 项目中正确链接了 whisper.xcframework
   - 在继续之前独立测试 whisper.cpp 的安装情况

3.**为开发而构建**
   - 使用调试配置进行开发
   - 在 Xcode 中启用相关调试选项

4.**测试**
   - 在进行修改之前运行测试套件
   - 确保修改后所有测试通过

## 疑难解答

如果遇到任何构建问题
1.清理构建文件夹 (Cmd+Shift+K)
2.清理编译缓存 (Cmd+Shift+K 两次)
3.检查 Xcode 和 macOS 版本
4.确认所有依赖项均已正确安装
5.确保 whisper.xcframework 已正确构建和链接

如需更多帮助，请查看 [issues](https://github.com/Beingpax/VoiceInk/issues) 部分或创建新问题。