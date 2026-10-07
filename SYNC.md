# 发布与同步指南（Publish & Sync）

本文档说明如何将该 SkillHub 发布到 WorkBuddy 与同步到 GitHub。
> 注：当前自动化构建环境（沙箱）未持有你的 WorkBuddy 发布凭据与 GitHub Token，
> 故「发布」与「git push」两步需在你本机 WorkBuddy / 终端中执行。仓库已 `git init` 并提交，处于可直接推送状态。

## 一、发布到 WorkBuddy（workbuddy.link 分享链接）

方式 A —— 在 WorkBuddy 客户端内：
1. 打开本仓库 `README.md`（专业学术性介绍）。
2. 使用「分享 / 发布为页面」功能，即可生成 `workbuddy.link/p/...` 公开可渲染链接。

方式 B —— 用 Artifact 工具（需你的账号登录态）：
- 上传 `README.md`（或 `pep-intro.html`），返回 shareable link。

如已生成链接，可回填到本文件顶部 `> 发布链接：` 处便于归档。

## 二、同步到 GitHub

### 1. 在本机配置身份（首次）
```bash
git config --global user.name  "你的GitHub用户名"
git config --global user.email "你的GitHub邮箱"
```

### 2. 创建远程仓库并推送
```bash
cd paper-research-team
# 若用 gh CLI（已登录）：
gh repo create paper-research-team --public --source=. --push --description "论文研究专家团：多智能体协同学术研究 SkillHub"

# 或手动关联已有空仓库：
git remote add origin https://github.com/<你的用户名>/paper-research-team.git
git branch -M main
git push -u origin main
```

### 3. 仅用 Token（无 gh）时
```bash
git remote add origin https://<TOKEN>@github.com/<用户名>/paper-research-team.git
git push -u origin main
```

## 三、安装到 WorkBuddy 专家中心

将本目录整体放入 marketplace 插件路径（参考原始路径）：
`~/.workbuddy/plugins/marketplaces/my-experts/plugins/paper-research-team/`
随后在【专家中心 → 我的专家】即可调用「论文研究专家团」。
