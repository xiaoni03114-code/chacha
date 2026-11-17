# chacha

基于 GitHub Actions 运行的 [sherlock](https://github.com/sherlock-project/sherlock) 用户名查询机器人。

## 使用

1. **手动运行**：仓库 `Actions` → 左侧 `Sherlock` → `Run workflow`，填入要查询的用户名（多个用空格分隔）→ 运行。
2. **自动运行**：默认每天 UTC 01:00（北京时间 09:00）自动查询一次。
3. **查看结果**：进入某次运行详情页，在页面底部 `Artifacts` 下载 `sherlock-results`。

结果文件为 `results/sherlock.txt`，只包含找到的账号（`--print-found`）。

## 修改默认目标

编辑 `.github/workflows/sherlock.yml`：
- 改默认用户名：修改 `workflow_dispatch.inputs.username.default` 和 `TARGETS` 的兜底值。
- 关掉定时任务：删除 `on.schedule` 段。
- 改运行时间：调整 `cron`（注意是 UTC 时间）。
