# CHANGELOG

## [Unreleased]

- 移除临时的 `apps/qtcloud-learn` 子模块关联：学习云挂载以领域仓库（domains/quanttide-learn）为准，避免同仓多副本漂移

### Added
- `data/profile/data-engineering/`：新增数据工程课程需求文档，包含课程背景、现状、需求要点及下一步工作规划

### Changed
- `apps/qtcloud-course`：provider 持久化从 SQLite 更换为对象存储（OSS）——解决 FC 无持久化问题（容器回收数据仍在）
  - 新增 `OSSStore[T]`（internal/store/ossstore.go）：与 SQLiteStore 同接口（List/Get/Create/Update/Delete/NameExists/ListWhere/SetID），每表一个对象（programs.json 等全量实体列表），懒加载 + 写时全量覆盖原子写；对齐 qtcloud-crowd 的 OSS store 模式（aliyun SDK + QTCLOUD_OSS_* 配置前缀）
  - 新增配置 `QTCLOUD_COURSE_STORE=oss|memory`（默认 memory 测试）；移除 SQLite（DB_PATH）分支与 modernc.org/sqlite 依赖
  - seed/seed-catalog 同步迁移：`QTCLOUD_COURSE_STORE=oss` 写入 OSS（Dockerfile 启动时先 seed 再起服务），默认 local 本地文件验证
  - 新增 OSS store 单测（mock OSS server，对齐 qtcloud-crowd oss_test）：CRUD/持久化/ListWhere/SetID/快照格式
  - terraform：新增课程数据 OSS 桶 + FC 环境变量注入（QTCLOUD_COURSE_STORE/QTCLOUD_OSS_*）

### Added
- `apps/qtcloud-course`：验收标准模型（provider v0.1.1-alpha.2）
  - Lesson/Scene 加 `Acceptance{criteria, method, on_fail}`（课时总验收 + 场景级每步判定，两层同构；Course 不加——课程完成 = 课时全过）

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
- `data/brochure`：新增课程研发宣传册子模块（quanttide-brochure-of-course-development）
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
