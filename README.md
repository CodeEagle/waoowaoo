# waoowaoo - 懒猫微服自动构建项目

> [!NOTE]
> 本项目跟踪 [waoowaooAI/waoowaoo](https://github.com/waoowaooAI/waoowaoo) 上游源码，并为 LazyCat 自动构建可安装镜像与 `.lpk` 包。

> [!IMPORTANT]
> **Icon 规范**：`icon.png` 文件大小不得超过 **200KB**，建议使用 512x512 像素的 PNG 格式图片。

## 本次修复

- 修复应用容器里错误调用 `mysqladmin` 等待数据库的问题
- 改为使用 Node 自带 TCP 探测等待 `mysql:3306` 与 `redis:6379`
- 增加 MySQL / Redis healthcheck，让 `depends_on` 真正等待依赖健康
- 明确 `/app/data` 与 `/app/logs` 的持久化挂载
- 将入口健康检查固定到 `/api/system/boot-id`

## 验收结果

这套 manifest 已在 LazyCat 盒子里完成安装验证：

- MySQL、Redis、`waoowaoo`、入口 sidecar 全部进入 `healthy`
- `Prisma db push --skip-generate` 成功
- Next.js `0.0.0.0:3000` 启动成功
- Bull Board 与 worker 正常启动

## 自动构建说明

本项目会在上游更新或手动触发时：

1. 构建 `ghcr.io/<owner>/waoowaoo:<tag>`
2. 复制镜像到 `registry.lazycat.cloud/...`
3. 使用当前仓库的 [lzc-manifest.yml](/Users/lincoln/Develop/GitHub/_codex_sync_waoowaoo/lzc-manifest.yml) 构建 `.lpk`
4. 发布 GitHub Release 产物

## 上游项目简介

waoowaoo 是一款基于 AI 技术的短剧 / 漫画视频制作工具，支持从小说文本自动生成分镜、角色、场景，并制作成完整视频。

## 技术栈

- Framework: Next.js 15 + React 19
- Database: MySQL + Prisma ORM
- Queue: Redis + BullMQ
- Styling: Tailwind CSS v4
- Auth: NextAuth.js

## Homepage

访问 [https://github.com/waoowaooAI/waoowaoo](https://github.com/waoowaooAI/waoowaoo) 了解更多信息。

## License

MIT License
