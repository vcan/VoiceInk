# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

VoiceInk 是一个原生 macOS 语音转文字应用，使用 SwiftUI 和 whisper.cpp 框架构建。应用支持本地和云端转录模型，具有智能增强功能、快捷键控制、多语言支持等特性。

## 构建和开发命令

### 基本构建
- 使用 Xcode 打开 `VoiceInk.xcodeproj`
- Cmd+B 构建项目
- Cmd+R 运行项目
- Cmd+U 运行测试
- Cmd+Shift+K 清理构建

### 依赖要求
- macOS 14.0+
- Xcode (最新版本)
- whisper.xcframework 必须存在于项目根目录

### 测试
- 单元测试: `VoiceInkTests/VoiceInkTests.swift`
- UI 测试: `VoiceInkUITests/VoiceInkUITests.swift`

## 核心架构

### 主要组件
1. **VoiceInkApp.swift** - 应用入口点，管理 SwiftData 容器和核心服务
2. **WhisperState** - 转录引擎的核心状态管理类
3. **ContentView.swift** - 主界面，使用 NavigationSplitView 分栏布局

### 服务层架构
- **TranscriptionService 协议** - 统一的转录服务接口
- **本地转录**: LocalTranscriptionService (使用 whisper.cpp)
- **云端转录**: OpenAI, Deepgram, Groq 等多种云服务
- **AI 增强**: AIEnhancementService 用于内容后处理
- **音频管理**: AudioDeviceManager, AudioFileProcessor

### 数据层
- 使用 **SwiftData** 作为主要数据存储
- **Transcription** 模型存储转录历史
- 数据库位置: `~/Library/Application Support/com.prakashjoshipax.VoiceInk/`

### UI 架构
- **ViewType 枚举** 定义所有可用视图
- **DynamicSidebar** 提供统一的侧边导航
- 模块化视图组织在 `Views/` 目录下

### 关键特性组件
- **PowerMode/** - 智能应用检测和上下文感知
- **Whisper/** - 本地 Whisper 模型集成
- **Services/CloudTranscription/** - 云端转录服务
- **Notifications/** - 系统通知管理

### 权限管理
应用需要以下系统权限：
- 麦克风访问 (音频录制)
- 辅助功能权限 (AXIsProcessTrusted)
- 屏幕录制权限 (CGPreflightScreenCaptureAccess)

### 依赖库
- **Sparkle** - 自动更新
- **KeyboardShortcuts** - 全局快捷键
- **LaunchAtLogin** - 开机启动
- **whisper.cpp** - 本地语音识别