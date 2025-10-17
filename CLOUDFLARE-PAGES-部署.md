# Cloudflare Pages 部署指南

## 🚀 部署步骤

### 方法1: 连接 Git 仓库（推荐）

#### 第一步: 准备 Git 仓库
确保代码已推送到 GitHub：
```bash
cd /home/wangzhengqiang/project/one-click-evaluation
git add .
git commit -m "准备部署到Cloudflare Pages"
git push origin main
```

#### 第二步: 创建 Cloudflare Pages 项目
1. 访问 https://dash.cloudflare.com
2. 登录账号
3. 点击左侧 "Workers & Pages"
4. 点击 "Create application"
5. 选择 "Pages" 标签
6. 点击 "Connect to Git"

#### 第三步: 连接 GitHub
1. 选择 "GitHub"
2. 授权 Cloudflare 访问你的 GitHub
3. 选择 `one-click-evaluation` 仓库
4. 点击 "Begin setup"

#### 第四步: 配置构建设置
**重要：这些设置决定部署是否成功**

```
项目名称: one-click-evaluation
生产分支: main (或 master)
Framework preset: None
Build command: (留空)
Build output directory: /
Root directory (advanced): (留空)
```

5. 点击 "Save and Deploy"
6. 等待3-5分钟

#### 第五步: 访问网站
部署成功后会显示访问地址：
- `https://one-click-evaluation.pages.dev`

---

### 方法2: 直接上传文件（最简单）

#### 第一步: 创建项目
1. 访问 https://dash.cloudflare.com
2. 点击 "Workers & Pages"
3. 点击 "Create application"
4. 选择 "Pages" 标签
5. 点击 "Upload assets"

#### 第二步: 上传文件
1. 项目名称: `one-click-evaluation`
2. 拖拽 `index.html` 到上传区域
3. 点击 "Deploy site"
4. 等待几秒钟

#### 第三步: 访问
- 访问地址: `https://one-click-evaluation.pages.dev`

---

## 🔧 常见问题排查

### 问题1: 部署成功但无法访问

**检查项**:
1. 等待DNS传播（可能需要5-10分钟）
2. 清除浏览器缓存
3. 尝试无痕模式访问
4. 检查是否有拼写错误

**访问地址应该是**:
- `https://one-click-evaluation.pages.dev`
- 不是 `https://one-click-evaluation.cloudflare.com`

### 问题2: 404 错误

**原因**: 
- 文件路径配置错误
- index.html 不在根目录

**解决**:
1. 确保 `index.html` 在仓库根目录
2. "Root directory" 设置为空
3. "Build output directory" 设置为 `/`

### 问题3: 国内访问慢或无法访问

**说明**:
- Cloudflare Pages 在国内访问可能较慢
- 但比 Vercel 稍好一些

**建议**:
- 使用手机4G/5G网络访问
- 或配置自定义域名+CDN

### 问题4: 构建失败

**原因**: 
- 构建命令错误

**解决**:
- 确保 "Build command" 留空
- 这是纯静态HTML，不需要构建

---

## 📝 部署检查清单

部署前确认：
- [ ] `index.html` 在仓库根目录
- [ ] 代码已推送到 GitHub
- [ ] Build command 留空
- [ ] Build output directory 设置为 `/`
- [ ] Framework preset 选择 None

部署后确认：
- [ ] 部署状态显示 "Success"
- [ ] 可以访问 `https://项目名.pages.dev`
- [ ] 页面功能正常

---

## 🎯 快速测试

部署完成后，测试这些功能：
1. 页面能否正常加载
2. 能否生成文案
3. 能否复制文案
4. 能否调起APP（需在手机浏览器中测试）

---

## 💡 提示

如果 Cloudflare Pages 也无法访问，建议：
1. **继续使用 Vercel**: https://one-click-evaluation.vercel.app
2. **用手机4G/5G网络**访问（不要用WiFi）
3. **Vercel在手机上通常是可以访问的**

Cloudflare Pages 和 Vercel 都是国外服务器，访问速度差不多。

