---
name: devops-contract
description: 使用 qtcloud-devops 进行组件的发布管理，包括 contract.yaml 配置、版本检查、CHANGELOG 更新和 GitHub Release 创建。
---

# devops-contract

使用 `qtcloud-devops` 发布组件版本。

## contract.yaml

每个组件的契约文件位于 `<submodule-root>/.quanttide/devops/contract.yaml`。

```yaml
scopes:
  <scope-name>:
    dir: <relative-path-to-component>
```

- `scope-name`：版本号前缀，如 `cli/v0.1.0` 中的 `cli`
- `dir`：组件目录相对于子模块根目录的路径（字段名是 `dir`，不是 `path`）

## 发布流程

1. **更新版本号**：确保组件的版本配置与目标版本一致（如 `Cargo.toml` 中的 `version` 字段）
2. **运行发布命令**：从子模块根目录执行
3. **确认并推送**：使用 `--yes` 跳过确认

```bash
cd <submodule-root>
qtcloud-devops release publish --version <scope>/<version>
# 或带 --yes 跳过确认
qtcloud-devops release publish --version <scope>/<version> --yes
```

## 注意事项

- 版本标签格式为 `<scope>/<version>`，如 `cli/v0.1.0-alpha.1`
- 版本号必须与组件配置文件一致（如 Cargo.toml 的 version 字段）
- `contract.yaml` 中的字段名是 `dir`，不是 `path`
- 发布命令在子模块根目录运行，不要在父仓库目录运行
- 发布完成后，需要提交父仓库的子模块引用变更
- `--yes` 用于 CI/自动化场景，手动发布可省略以预览变更
