# Discover Brand Domains

适用于 Claude Code 和 Codex 的 Agent Skill。逐一搜索 Google、百度、Bing 和 Yahoo，并在 Telegram、X、Facebook 上找公开线索，再用找到的品牌名、账号和域名回搜。合并各来源的结果，核对旧名单的遗漏，并可按要求整理为 Excel。

需要能搜索和读取公开网页的工具。各搜索引擎和社交平台能否访问取决于运行环境。报告会逐个记录实际查询、访问方式和命中情况。导出 Excel 需要运行环境支持生成 `.xlsx`。

## 安装

在 macOS 或 Linux 上克隆仓库。根据所用工具执行相应的链接命令。

```bash
git clone https://github.com/thisnicoisgood/discover-brand-domains.git \
  "$HOME/discover-brand-domains-repo"

skill_dir="$HOME/discover-brand-domains-repo/discover-brand-domains"

# Claude Code
mkdir -p "$HOME/.claude/skills"
ln -s "$skill_dir" "$HOME/.claude/skills/discover-brand-domains"

# Codex
mkdir -p "$HOME/.agents/skills"
ln -s "$skill_dir" "$HOME/.agents/skills/discover-brand-domains"
```

如果目标位置已经有同名技能，请先检查现有目录或链接，再决定是否替换。

## 使用

- Claude Code 输入 `/discover-brand-domains`，后面接任务。
- Codex 输入 `$discover-brand-domains`，后面接任务。

示例任务：盲搜 PC28 开奖和数据站，核对旧表的遗漏，按完整域名去重，保留来源和公开联系方式，并导出 Excel。

## 更新

```bash
git -C "$HOME/discover-brand-domains-repo" pull --ff-only
```

两个工具的链接指向同一个克隆目录。更新后可在新会话中使用最新版。

## 许可证

[MIT](LICENSE)
