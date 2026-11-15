## [0.9.1] - 2026-11-15

### 修复

- **macOS / Linux 无法打包**：`tauri-build` 2.6.3 在较新 Cargo 的构建目录布局
  （`target/<triple>/release/build/<pkg>/<hash>/out`）下，把
  `target/<triple>/release/build/docclear-mcp` 目录误当成 sidecar 目标文件删除，
  导致构建脚本 panic（macOS `Operation not permitted`、Linux `Is a directory`）。
  升级 `tauri-build` 至 2.7.4，改用上游修复后的 target 目录解析逻辑。Windows
  构建不受影响。

