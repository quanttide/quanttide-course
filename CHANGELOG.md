# CHANGELOG

## [0.1.0] - 2026-07-04

### Added
- 课程领域仓库结构，以子模块组织应用、工具、素材与文档
- `apps/qtcloud-course`：课程云应用，含无状态 CLI（`blueprint` 子命令，`--input-path`/`--output-path` 参数）
- `data/profile/git/`：Git 课程蓝图（分布式 vs 集中式，2 课时）
- `data/profile/docker/`：Docker 课程蓝图（镜像 vs 容器，2 课时）
- `docs/essay`：课程开发随笔（含《课程蓝图》一文）
- `docs/tutorial`：课程开发教程（含蓝图方法论文档）
- `examples/default`：课程开发实验室（Rust，通过 quanttide-agent 调用 DeepSeek）
- `.agents/skills/devops-contract`：发布管理技能
- `.gitmodules` 子模块管理机制
- CC BY 4.0 许可证

### Removed
- `assets/courses/big-data`：子模块已移除
