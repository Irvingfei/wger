# Source

This directory holds the source files of the TOS 7 Docker package. The release
assets are built from these files.

- `config.x86_64.ini` / `config.aarch64.ini` — `config.ini` for each architecture
- `docker-compose.yml` — build template; `@@...@@` placeholders are replaced at build time
- `wger.lang` — 14 language sections
- `wger.svg` — application icon

Build toolchain: https://github.com/Irvingfei/docker-apps
