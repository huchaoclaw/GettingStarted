[Xuan酱部署](https://ycnezwebj31p.feishu.cn/docx/MVomdT4tWoeEnmxFFEAcsHGpnph)

- [方舟 Coding Plan](https://www.volcengine.com/activity/codingplan)
  - [百炼Coding Plan](https://cn.aliyun.com/benefit/scene/codingplan?from_alibabacloud=)
- [ClawHub](https://clawhub.ai/)
- 



# 初始化

```bash
curl -fsSL https://openclaw.ai/install.sh | bash

cat <<EOF >> ~/.zshrc

export PATH="/Users/huchaoclaw/.local/share/fnm/node-versions/v24.14.0/installation/bin:\$PATH"
EOF

openclaw onboard
openclaw doctor
openclaw doctor --fix

# 查看网关状态
openclaw gateway status

# 启动/停止网关
openclaw gateway start
openclaw gateway stop

# 查看当前配置的模型
openclaw models list
openclaw models status

# skills
openclaw skills

# update
openclaw update
npm update -g openclaw

# channels
openclaw channels add
openclaw channels list
openclaw channels login --channel whatsapp
# 给自己发消息就可以了


# Hook
openclaw hooks list
openclaw hooks disable boot-md
```

## 基本配置

### 模型配置

```bash
# https://docs.siliconflow.cn/cn/usercases/use-siliconcloud-in-OpenClaw
# https://docs.siliconflow.cn/cn/userguide/quickstart
https://api.siliconflow.cn/v1
# https://cloud.siliconflow.cn/me/models
deepseek-ai/DeepSeek-V3.2
◇  Endpoint ID
│  custom-api-siliconflow-cn
◇  Model alias (optional)
│  DSV32
```

### channels

```bash
openclaw channels login
https://wa.me/qr/RUIX4ZWL3KHNP1

# https://docs.openclaw.ai/tools/web
# https://docs.openclaw.ai/zh-CN/tools/web
```

### Install missing skill dependencies

```bash
◇  Install missing skill dependencies
│  🔐 1password, 📰 blogwatcher, 🧩 clawhub, 🐙 github, 🎮 gog, 📍 goplaces, 📦 mcporter, 📊 model-usage, 🎙️ openai-whisper, 🧾 summarize, 🎞️ video-frames, 📱 wacli


◇  Install failed: clawhub — spawn pnpm ENOENT
spawn pnpm ENOENT
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills
│

################################################################################################

◇  Installed goplaces
│
◇  Install failed: mcporter — spawn pnpm ENOENT
spawn pnpm ENOENT
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills

################################################################################################

◇  Install failed: model-usage (exit 1) — Error: Failed to load formula: steipete/tap/codexbar
Error: Failed to load formula: steipete/tap/codexbar
steipete/tap/codexbar: formula requires at least a URL
Warning: Treating steipete/tap/codexbar as a cask.
Error: This software does not run on macOS versions older than Sonoma.
Warning: You are using macOS 13.
We (and Apple) do not provide support for this old version.
You may have better luck with MacPorts which supports older versions of macOS:
  https://www.macports.org

This is a Tier 3 configuration:
  https://docs.brew.sh/Support-Tiers#tier-3
You can report Tier 3 unrelated issues to Homebrew/* repositories!
Read the above document before opening any issues or PRs.
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills

################################################################################################

◇  Install failed: openai-whisper (exit 1) — Error: openai-whisper: An unsatisfied requirement failed this build.
Warning: You are using macOS 13.
We (and Apple) do not provide support for this old version.
You may have better luck with MacPorts which supports older versions of macOS:
  https://www.macports.org

```

## Hooks Configured

```bash
│  ◻ 🚀 boot-md (Run BOOT.md on gateway startup)
│  ◻ 📎 bootstrap-extra-files (Inject additional workspace bootstrap files via glob/path patterns)
│  ◻ 📝 command-logger (Log all command events to a centralized audit file)
│  ◻ 💾 session-memory (Save session context to memory when /new or /reset command is issued)

◇  Hooks Configured ─────────────────────────╮
│                                            │
│  Enabled 2 hooks: boot-md, session-memory  │
│                                            │
│  You can manage hooks later with:          │
│    openclaw hooks list                     │
│    openclaw hooks enable <name>            │
│    openclaw hooks disable <name>           │
│                                            │
├────────────────────────────────────────────╯
```




## 其他知识

### npm VS pnpm VS Bun

1. npm (Node Package Manager)
定位：Node.js 官方默认工具，生态最稳、兼容性最好。

2. pnpm (Performant npm)
节省空间：相同版本的包在磁盘上只存一份。
速度快：比 npm 快得多，且原生支持高效的 Monorepo 工作流。 

3. Bun
定位：一个新兴的全栈 JavaScript 运行时，它不仅是包管理器，还集成了运行环境、测试工具和打包工具。
原理：使用 Zig 语言编写，针对性能进行了底层优化，并行处理任务。
极致速度：安装速度比 npm 快达 30 倍，甚至大幅超越 pnpm。
