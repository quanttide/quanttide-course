# CHANGELOG

## [0.1.0-alpha.1] - 2026-07-04

### Added
- 新增 `apps/qtcloud-course` 应用目录结构及无状态 CLI（含蓝图子命令和 README）。
- 新增课程蓝图：Git 课程蓝图、Docker 课程蓝图（含第 2 课），并拆分 Git 蓝图为文件夹。
- 新增文档 essay 子模块，包含课程蓝图的定义及重写后的 `blueprint.md`。
- 新增示例项目 `examples/default`，初始化 LLM 蓝图实验并移植到 Rust。
- 添加根目录 README、CC BY 4.0 许可证、顶层目录 `.gitkeep` 及课程生态相关子模块。

### Changed
- 清理 `examples/default` 中的冗余代码和实验结果。
- 从 `apps/qtcloud-course` 中提取蓝图模块。
- 更新子模块引用，包括 Git 蓝图重命名、文档重写及同步提示修复。
