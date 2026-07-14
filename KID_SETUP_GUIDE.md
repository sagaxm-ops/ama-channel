# 小孩独立开发操作指南

> GitHub 用户名：AB0592

---

## 一、Fork 仓库

1. 访问 https://github.com/sagaxm-ops/ama-channel
2. 点击右上角 **"Fork"** 按钮
3. **勾选** "Copy the main branch only"
4. 点击 **"Create fork"**

完成后你的仓库地址：`https://github.com/AB0592/ama-channel`

---

## 二、开启 GitHub Pages

1. 进入你 fork 的仓库：`https://github.com/AB0592/ama-channel`
2. 点击顶部 **Settings**
3. 左侧菜单点击 **Pages**
4. Source 选择：**Deploy from a branch**
5. Branch 选择：`main` / `root`
6. 点击 **Save**
7. 等待 1-2 分钟后，访问：`https://AB0592.github.io/ama-channel/`

---

## 三、生成 Personal Access Token

> GitHub 已不支持密码直接推送，必须用 Token

1. 点击右上角头像 → **Settings**
2. 左侧最下方 **Developer settings**
3. 点击 **Personal access tokens → Tokens (classic)**
4. 点击右上角 **Generate new token (classic)**
5. Note 填写：`ama-channel`
6. Expiration 选择：**No expiration**（永不过期）
7. 勾选权限：**`repo`**（完整仓库权限）
8. 点击最下方 **Generate token**
9. **立刻复制 Token**（绿色框里的字符串，只显示一次！）

**保存好这个 Token，它就是以后 git push 时用的密码。**

---

## 四、在 TRAE 中操作

### 1. 克隆仓库

在 TRAE 终端中执行：

```bash
git clone https://github.com/AB0592/ama-channel.git
cd ama-channel
```

### 2. 配置 Git 身份信息

```bash
git config user.name "AB0592"
git config user.email "你注册GitHub用的邮箱"
```

### 3. 修改代码

告诉 TRAE 你的需求，例如：

> "请帮我更新 index.html 中的 XUNFEI_CONFIG，换成新的凭据：AppID=xxx, APIKey=xxx, APISecret=xxx"

### 4. 提交并推送

```bash
git add -A
git commit -m "修改说明"
git push
```

推送时会要求输入：
- 用户名：`AB0592`
- 密码：粘贴刚才生成的 **Personal Access Token**

### 5. 查看更新

推送后等 1-2 分钟，访问：`https://AB0592.github.io/ama-channel/`

用 **Cmd+Shift+R**（Mac）或 **Ctrl+F5**（Windows）强制刷新。

---

## 五、重要提醒

1. **Token 只显示一次**，生成时务必复制保存
2. 每次 `git push` 都要用 Token 作为密码
3. 修改 `index.html` 后，**必须同步到 `ama-channel.html`**：
   ```bash
   cp index.html ama-channel.html
   ```
4. 推送后等 1-2 分钟，再用强制刷新查看效果
5. iFlytek API 每日 500 次免费调用，超限后自动回退到 FunASR
6. 语音识别有两组独立状态，修改时不能混用

---

## 六、常用命令速查

| 操作 | 命令 |
|------|------|
| 克隆仓库 | `git clone https://github.com/AB0592/ama-channel.git` |
| 查看状态 | `git status` |
| 添加所有修改 | `git add -A` |
| 提交修改 | `git commit -m "修改说明"` |
| 推送到 GitHub | `git push` |
| 同步副本文件 | `cp index.html ama-channel.html` |
| 拉取最新代码 | `git pull` |
