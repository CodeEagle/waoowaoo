# waoowaoo - 懒猫微服自动构建项目

> [!NOTE]
> 本项目是 [waoowaoo](https://github.com/waoowaooAI/waoowaoo) 的懒猫微服（LazyCat）自动构建项目，用于自动跟踪上游更新并发布到懒猫应用商店。

> [!IMPORTANT]
> **Icon 规范**：`icon.png` 文件大小不得超过 **200KB**，建议使用 512x512 像素的 PNG 格式图片。

**waoowaoo - 首家工业级全流程 AI 影视生产平台**

## 关于本项目

本项目会自动监测 [waoowaooAI/waoowaoo](https://github.com/waoowaooAI/waoowaoo) 的更新，当有新版本发布时：
1. 自动构建 Docker 镜像
2. 复制镜像到懒猫官方镜像源
3. 更新 `lzc-manifest.yml` 配置
4. 构建并发布到懒猫应用商店

## waoowaoo 简介

waoowaoo 是一款基于 AI 技术的短剧/漫画视频制作工具，支持从小说文本自动生成分镜、角色、场景，并制作成完整视频。

## 功能特性

| 功能 | 描述 |
|------|------|
| 🎬 AI 剧本分析 | 自动解析小说，提取角色、场景、剧情 |
| 🎨 角色 & 场景生成 | AI 生成一致性人物和场景图片 |
| 📽️ 分镜视频制作 | 自动生成分镜头并合成视频 |
| 🎙️ AI 配音 | 多角色语音合成 |
| 🌐 多语言支持 | 中文 / 英文界面，一键切换 |

## 技术栈

- **Framework**: Next.js 15 + React 19
- **Database**: MySQL + Prisma ORM
- **Queue**: Redis + BullMQ
- **Styling**: Tailwind CSS v4
- **Auth**: NextAuth.js

## Homepage

访问 [https://github.com/waoowaooAI/waoowaoo](https://github.com/waoowaooAI/waoowaoo) 了解更多信息。

## License

MIT License
