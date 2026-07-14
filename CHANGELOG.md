# CHANGELOG

## [0.1.1] - 2026-07-14

### Added
- `apps/qtcloud-course`：新增 Flutter Studio 客户端（`src/studio`），版本迭代至 v0.0.5
  - 四级 CRUD（Program/Course/Phase/Lesson 新建/编辑/删除）
  - 发布/下架功能
  - JSON 导入/导出（双轨互通）
  - Sidebar 导航重构（底部导航 → 左侧导航）
  - PreviewScreen 试听预览页
  - GUI 自动化测试套件
- `apps/qtcloud-course`：新增 Go provider 服务端
- `apps/qtcloud-course`：新增 CLI 工具（blueprint 子命令）
- `docs/gallery`：新增案例集子模块（多个客户案例分析）
- `docs/specification`：新增规格文档子模块（考核、Assignment 等）
- `data/context`：新增课程开发上下文子模块
- `data/intention`：新增产品意图子模块
- `data/journal`：新增开发日志子模块
- `docs/tutorial`：新增 Vibe Coding 教程子模块
- `examples/default`：新增课程开发实验室（Rust/Python/Go 模拟程序）
- `data/profile/git/`：Git 课程蓝图（分布式 vs 集中式，2 课时）
- `data/profile/docker/`：Docker 课程蓝图（镜像 vs 容器，2 课时）

### Changed
- `docs/specification`：多次重构，统一实体命名、精简 AssessmentType、目录重组
- `data/context`：补充开发者画像、产品愿景、AI 反思笔记
- `data/intention`：按场景重组，降级技术细节，聚焦产品设计
- 主仓库 CHANGELOG 补全 v0.1.0 以来的全部变更

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
