# GitHub CLI 授权指南

## 第一步：安装 GitHub CLI

### Windows 安装方法：

#### 方法一：使用 winget（推荐）
```bash
winget install --id GitHub.cli
```

#### 方法二：下载安装包
1. 访问 https://cli.github.com/
2. 下载 Windows 安装包
3. 运行安装程序

#### 方法三：使用 Chocolatey
```bash
choco install gh
```

## 第二步：验证安装

安装完成后，在新的终端窗口中运行：
```bash
gh --version
```

## 第三步：GitHub 身份验证

### 登录到 GitHub
```bash
gh auth login
```

### 登录流程：
1. **选择 GitHub.com**（按回车）
2. **选择登录方式**：
   - 推荐选择：`Login with a web browser`（使用网页浏览器登录）
3. **按回车** 继续
4. **生成授权码**，然后按回车
5. **浏览器会自动打开** GitHub 授权页面
6. **点击 "Authorize"** 授予权限
7. **等待确认** 终端会显示认证成功信息

## 第四步：验证权限

验证是否成功登录并检查权限：
```bash
gh auth status
```

你应该看到类似这样的输出：
```
github.com
  ✓ Logged in to github.com as 你的用户名
  ✓ Git operations for github.com configured to use https protocol
  ✓ Token: gho_****************
  ✓ Token scopes: gist, repo, workflow, ...
```

## 第五步：确认创建仓库权限

确保你有以下权限：
- `repo` - 完整的仓库访问权限
- `workflow` - 工作流权限（用于 GitHub Actions）

如果权限不完整，可以重新运行：
```bash
gh auth login --scopes repo,workflow
```

## 第六步：完成授权后

完成以上步骤后，通知我 "授权完成"，我将帮你：
1. ✅ 创建 GitHub 仓库
2. ✅ 推送代码到 GitHub
3. ✅ 配置 GitHub Pages
4. ✅ 生成公开访问链接

## 常见问题

### Q: 授权失败怎么办？
A: 确保你的网络可以访问 GitHub，必要时可以配置代理。

### Q: 如何查看当前的 token？
A: 运行 `gh auth token` 可以查看当前的访问令牌。

### Q: 想要撤销授权怎么办？
A: 访问 https://github.com/settings/tokens 查看和撤销令牌。

## 注意事项
- 请确保你的 GitHub 账号有创建公开仓库的权限
- 如果你使用的是企业 GitHub 账号，可能需要额外授权
- 仓库将是公开的，任何人都可以访问
