# Ed25519 SchnorrQ 在线签名工具（纯 JavaScript）

**高性能 Ed25519 数字签名工具 · 支持 SHA-512 / BLAKE2b-512 动态切换 · 纯浏览器端运行**

基于 [@noble/ed25519](https://github.com/paulmillr/noble-ed25519) + [@noble/hashes](https://github.com/paulmillr/noble-hashes) 实现，完全兼容 **Nano / python-ed25519-blake2b**（BLAKE2b 模式）和标准 Ed25519 / FourQ-SchnorrQ（SHA-512 模式）。

### 在线演示（部署后）

https://wgsxsm.github.io/ed25519-hash-switch-web

### 功能

- 生成公私钥对（32 + 32 字节）
- 对任意消息进行签名（64 字节签名）
- 验证签名（即时反馈 ✅ / ❌）
- **实时切换哈希算法**：
  - SHA-512（标准模式）
  - BLAKE2b-512（Nano / python-ed25519-blake2b 兼容模式）
- 全部计算在浏览器本地完成，**私钥永不离开本地**，数据零上传

### 使用方法

1. 打开 `index.html`（或部署后的在线地址）
2. 切换 SHA-512 / BLAKE2b 开关（默认 SHA-512）
3. 点击「生成新密钥对」→ 立即复制私钥（请妥善备份！）
4. 输入消息 → 「生成签名」
5. 在步骤 3 粘贴公钥、消息、签名 → 「验证签名」

### 部署到 GitHub Pages（超简单，30 秒完成）

1. Fork 或新建一个 GitHub 仓库（推荐仓库名：`ed25519-schnorrq-web`）
2. 把 `index.html` 上传到仓库根目录
3. 进入 **Settings → Pages**
4. Source 选择 **Deploy from a branch** → `main` / `(root)` → 保存
5. 等待 1~2 分钟，即可通过 `https://wgsxsm.github.io/ed25519-hash-switch-web` 访问

无需 Emscripten、无需编译、无需服务器，纯静态文件即可运行。

### 技术栈

- **核心库**：`@noble/ed25519@2` + `@noble/hashes@1`（通过 esm.sh CDN 加载）
- **UI**：Tailwind CSS + 完全复刻 [fourq-schnorrq-web](https://github.com/wgsxsm/fourq-schnorrq-web) 的紫色渐变风格
- **体积**：单个 `index.html` 文件（< 30KB），加载极快

### 为什么选择这个项目？

- 与原 `fourq-schnorrq-web` 风格完全一致（紫色头部、步骤卡片、开关样式）
- 无 WebAssembly 依赖，更轻量、更易维护
- 支持你最需要的 **BLAKE2b-512** 模式（直接兼容 Nano 生态和 python-ed25519-blake2b）

---

**安全提醒**：本工具仅供学习和测试使用。私钥请仅在可信环境使用，生产环境推荐使用硬件钱包。

欢迎 Star / Fork / PR ✨

Made with ❤️ for Nano & Ed25519 爱好者
