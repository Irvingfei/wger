# wger for TOS 7 (Docker)

自托管的健身与营养管理器：制定训练计划、浏览动作库、记录体重与饮食，提供网页界面和 REST API，手机 App 也能连接。

A self-hosted workout and nutrition manager: plan routines, browse the exercise database, and track body weight and meals, with a web UI and a REST API for the mobile app.

## Package

- Application ID: `wger`
- Type: Docker (TOS 7)
- Architecture: `x86_64`, `aarch64`
- Upstream image: see `docker-compose.yml` in the downloaded asset
- Web UI port: declared in `x-app-meta`

## Source

The `src/` directory contains the files the package is built from:

- `src/config.x86_64.ini` / `src/config.aarch64.ini` — `config.ini` per architecture
- `src/docker-compose.yml` — compose template; `@@...@@` placeholders are replaced at build time
- `src/wger.lang` — 14 language sections
- `src/wger.svg` — application icon

Build toolchain: https://github.com/Irvingfei/docker-apps

## Install

1. In the TOS App Center, add this repository's application and submit the matching `wger_<arch>.tar.gz` asset from the latest Release.
2. Data is stored under `/Volume<N>/DockerAppData/wger/` through the compose bind mounts.

## Notes

由 6 个容器组成（Web、PostgreSQL、Redis、Celery×2、Nginx），建议至少 2GB 可用内存。首次启动需要执行数据库迁移和静态文件收集，可能要 5–10 分钟才能打开页面，请耐心等待。SITE_URL 默认是 http://localhost:18089，需要外链或媒体地址时请改成 NAS 的实际地址。注册功能默认开启。

This repository packages the upstream open-source application for TerraMaster TOS 7.
It is not affiliated with or endorsed by the upstream project. Application names and
trademarks belong to their respective owners. All images are pulled from Docker Hub.
