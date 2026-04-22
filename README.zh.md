<div align="center">
  <a href="https://casdoor.ai">
    <img src="https://cdn.casbin.org/img/casdoor-logo_1185x256.png" alt="Casdoor" width="500">
  </a>

  <h1>Casdoor</h1>
  <h3>AI-First 身份与访问管理（IAM）/ AI MCP 网关</h3>
  <p align="center">
    <strong>Languages:</strong>
    <a href="README.md"><strong>English</strong></a> |
    <a href="README.zh.md"><strong>简体中文</strong></a>
  </p>

  <p align="center">
    <strong>一个开源、AI-First 的 IAM / MCP 网关与认证服务器，内置 Web UI。</strong><br>
    支持 MCP、A2A、OAuth&nbsp;2.0、OIDC（OAuth&nbsp;2.x）、SAML、CAS、LDAP、SCIM、WebAuthn、TOTP、MFA、Face ID、<br>
    Google Workspace、Azure AD 等。
  </p>

  <p align="center">
    <a href="https://casdoor.ai/"><strong>文档与指南：casdoor.ai</strong></a>
  </p>

  <p>
    <a href="https://casdoor.ai/docs/overview">
      <img src="https://img.shields.io/badge/documentation-casdoor.ai%2Fdocs-1890ff?style=flat-square&logo=readthedocs&logoColor=white" alt="Documentation">
    </a>
    <a href="https://github.com/casdoor/casdoor/releases/latest">
      <img src="https://img.shields.io/github/v/release/casdoor/casdoor?style=flat-square&color=blue" alt="GitHub Release">
    </a>
    <a href="https://hub.docker.com/r/casbin/casdoor">
      <img src="https://img.shields.io/docker/pulls/casbin/casdoor?style=flat-square&color=brightgreen" alt="Docker Pulls">
    </a>
    <a href="https://github.com/casdoor/casdoor/actions/workflows/build.yml">
      <img src="https://img.shields.io/github/actions/workflow/status/casdoor/casdoor/build.yml?style=flat-square&label=build" alt="Build Status">
    </a>
    <a href="https://goreportcard.com/report/github.com/casdoor/casdoor">
      <img src="https://goreportcard.com/badge/github.com/casdoor/casdoor?style=flat-square" alt="Go Report Card">
    </a>
    <a href="https://github.com/casdoor/casdoor/blob/master/LICENSE">
      <img src="https://img.shields.io/github/license/casdoor/casdoor?style=flat-square&color=orange" alt="License">
    </a>
  </p>

  <p>
    <a href="https://github.com/casdoor/casdoor/stargazers">
      <img src="https://img.shields.io/github/stars/casdoor/casdoor?style=flat-square&color=yellow" alt="GitHub Stars">
    </a>
    <a href="https://github.com/casdoor/casdoor/network/members">
      <img src="https://img.shields.io/github/forks/casdoor/casdoor?style=flat-square" alt="GitHub Forks">
    </a>
    <a href="https://github.com/casdoor/casdoor/issues">
      <img src="https://img.shields.io/github/issues/casdoor/casdoor?style=flat-square&color=red" alt="GitHub Issues">
    </a>
    <a href="https://discord.gg/5rPsrAzK7S">
      <img src="https://img.shields.io/discord/1022748306096537660?style=flat-square&logo=discord&label=Discord&color=5865F2" alt="Discord">
    </a>
    <a href="https://crowdin.com/project/casdoor-site">
      <img src="https://badges.crowdin.net/casdoor-site/localized.svg" alt="Crowdin">
    </a>
  </p>

  <p align="center">
    <a href="https://casdoor.ai"><strong>官网</strong></a> ·
    <a href="https://casdoor.ai/docs/overview"><strong>文档</strong></a> ·
    <a href="https://door.casdoor.com"><strong>在线演示</strong></a> ·
    <a href="https://discord.gg/5rPsrAzK7S"><strong>Discord</strong></a>
  </p>
</div>

---

## 目录

- [为什么选择 Casdoor](#why-casdoor)
- [在线演示](#live-demos)
- [快速开始](#quick-start)
- [功能特性](#features)
- [技术栈](#technology-stack)
- [文档](#documentation)
- [集成](#integrations)
- [安全](#security)
- [社区与支持](#community-and-support)
- [参与贡献](#contributing)
- [许可证](#license)

---

<a id="why-casdoor"></a>
## 为什么选择 Casdoor

Casdoor 是一个**UI 优先**的身份提供方（IdP）与访问管理平台：通过现代化 Web 控制台，在一个地方统一管理用户、组织、应用与身份源。授权策略可借助 **[Casbin](https://casbin.org/)** 表达（ACL、RBAC、ABAC 等）。与以反向代理为中心的认证伴生方案不同，Casdoor 是一个支持广泛协议的专用认证服务器——其定位更接近完整 IdP，而非仅作为 sidecar 代理——因此你可以自托管，并在同一平台完成用户、应用与身份源集成。更多信息请参阅 **[casdoor.ai](https://casdoor.ai)**。

---

<a id="live-demos"></a>
## 🌐 在线演示

| 环境 | URL | 说明 |
|-------------|-----|-------------|
| **只读** | [door.casdoor.com](https://door.casdoor.com) | 全球演示站；**任何修改或写入操作都会失败**（只读）。 |
| **可写** | [demo.casdoor.com](https://demo.casdoor.com) | 可完整体验；**数据大约每 5 分钟重置一次**。 |

默认演示管理员账号（适用时）：`admin` / `123` —— 仅用于演示，请在你自己的部署中修改凭据。

---

<a id="quick-start"></a>
## 🚀 快速开始

选择以下任一部署方式。为保证与上游行为一致，步骤与官方文档保持对齐。

### 🛠️ 源码部署（默认）

1. 安装依赖：**Go 1.25**（以 `go.mod` 为准）、**Node.js LTS（20）**、**Yarn 1.x** 以及受支持的数据库。
2. 克隆仓库：

```bash
git clone https://github.com/casdoor/casdoor.git
cd casdoor
```

3. 在 `conf/app.conf` 中配置数据库（至少设置 `driverName`、`dataSourceName` 和 `dbName`；若使用 MySQL，请先创建 `casdoor` 数据库）。
4. 构建前端并启动后端：

```bash
cd web
yarn install
yarn build
cd ..
go run main.go
```

5. 打开 [http://localhost:8000](http://localhost:8000)，在全新安装时使用 `built-in/admin` / `123` 登录（生产环境请立即修改密码）。

官方指南：[Server installation](https://casdoor.ai/docs/basic/server-installation)

### 🐳 Docker

使用以下任一官方 Docker 方式：

- **All-in-one（SQLite 快速体验）**：

```bash
docker run -p 8000:8000 casbin/casdoor-all-in-one
```

- **Docker Compose**（将你的 `conf/app.conf` 与 `docker-compose.yml` 放在同一目录）：

```bash
docker compose up
```

然后打开 [http://localhost:8000](http://localhost:8000)，在全新安装时使用 `built-in/admin` / `123` 登录。

官方指南：[Try with Docker](https://casdoor.ai/docs/basic/try-with-docker)

### ☸️ Kubernetes Helm

在已安装 Helm v3 且 Kubernetes 集群可用的前提下：

```bash
helm install casdoor oci://registry-1.docker.io/casbin/casdoor-helm-charts
```

安装完成后，通过集群 service/ingress 访问 Casdoor。若需可复现安装，请使用 `--version` 固定 chart 版本；官方指南中提供了当前 chart 与各类集群选项。

官方指南：[Try with Helm](https://casdoor.ai/docs/basic/try-with-helm)

---

<a id="features"></a>
## ✨ 功能特性

<table>
<tr>
<td width="50%">

### 🔐 认证能力

- **OAuth 2.0 / OIDC** — OpenID Connect 与 OAuth 2.x 授权
- **SAML 2.0** — 企业级单点登录集成
- **CAS** — 中央认证服务
- **LDAP** — 目录服务集成
- **WebAuthn / Passkeys** — 无密码认证
- **TOTP / MFA** — 多因素认证
- **Face ID** — 生物识别认证

</td>
<td width="50%">

### 🏢 企业能力

- **SCIM 2.0** — 用户生命周期与自动预配
- **RBAC** — 基于角色的访问控制
- **Social Login** — Google、GitHub、Azure AD 等
- **Custom providers** — 可扩展的身份提供方
- **User management** — 可视化管理后台
- **Audit logs** — 完整审计日志
- **Multi-tenancy** — 多组织租户支持

</td>
</tr>
<tr>
<td width="50%">

### 🤖 AI 与 MCP

- **MCP Gateway** — Model Context Protocol 支持
- **A2A Protocol** — Agent-to-Agent 通信
- **AI-First Design** — 面向 AI 应用设计

</td>
<td width="50%">

### 🛠️ 开发者体验

- **RESTful API** — 完整 API 覆盖
- **SDKs** — Go、Java、Python、Node.js 等
- **Swagger UI** — 交互式 API 文档
- **Webhooks** — 事件驱动集成
- **Customizable UI** — 品牌化主题能力

</td>
</tr>
</table>

---

<a id="technology-stack"></a>
## 技术栈

Casdoor 采用**前后端分离**架构：

- **Web UI**：JavaScript 与 **React**（[`web/`](https://github.com/casdoor/casdoor/tree/master/web)）
- **API 服务端**：基于 **Go** 与 **Beego** 的 RESTful API（[仓库根目录](https://github.com/casdoor/casdoor)）
- **数据层**：支持 **MySQL**、**PostgreSQL** 等主流数据库（[overview](https://casdoor.ai/docs/overview)）
- **缓存层**：可选 **Redis**，用于会话/缓存型部署（按需配置）

---

<a id="documentation"></a>
## 📖 文档

**所有产品文档、安装指南与教程均在 [casdoor.ai/docs/overview](https://casdoor.ai/docs/overview)。** 建议从这里开始，再按下列主题深入。

**安装部署**

- [Install from source](https://casdoor.ai/docs/basic/server-installation)
- [Install with Docker](https://casdoor.ai/docs/basic/try-with-docker)
- [Install with Kubernetes Helm](https://casdoor.ai/docs/basic/try-with-helm)

**应用接入**

- [How to connect to Casdoor](https://casdoor.ai/docs/how-to-connect/overview)

**API**

- [Public API](https://casdoor.ai/docs/basic/public-api)
- [Swagger UI](https://door.casdoor.com/swagger)（在线 API 浏览器）

---

<a id="integrations"></a>
## 🔌 集成

Casdoor 可与常见编程语言和框架集成：

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original.svg" width="40" alt="Go">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" width="40" alt="Java">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="40" alt="Python">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" width="40" alt="Node.js">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="40" alt="React">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" width="40" alt="Vue">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/angularjs/angularjs-original.svg" width="40" alt="Angular">
</p>

查看完整列表：[Integrations](https://casdoor.ai/docs/category/integrations)。

---

<a id="security"></a>
## 🔒 安全

请**不要**在公开 GitHub issues 中报告安全漏洞。请参阅 [SECURITY.md](SECURITY.md) 了解负责任的漏洞提交流程。

---

<a id="community-and-support"></a>
## 🤝 社区与支持

- **Discord**：[加入社区](https://discord.gg/5rPsrAzK7S)
- **联系支持**：[casdoor.ai/help](https://casdoor.ai/help)
- **Issues**：[GitHub Issues](https://github.com/casdoor/casdoor/issues)
- **Discussions**：[GitHub Discussions](https://github.com/casdoor/casdoor/discussions)

---

<a id="contributing"></a>
## 🌍 参与贡献

如果你对 Casdoor 有疑问，欢迎**[提交 issue](https://github.com/casdoor/casdoor/issues)**。也欢迎提交 Pull Request；但**建议先开 issue**，便于在较大改动前与维护者和社区对齐方向。

贡献前也请阅读我们的[贡献指南](https://casdoor.ai/docs/contributing/)。

### 翻译与 i18n

- 翻译工作流使用 **Crowdin**：[casdoor-site on Crowdin](https://crowdin.com/project/casdoor-site)。
- Web 应用使用 **i18next**。当你在 [`web/`](https://github.com/casdoor/casdoor/tree/master/web) 下新增或修改面向用户的文案时，请同步更新英文词条 [`web/src/locales/en/data.json`](web/src/locales/en/data.json)。

---

<a id="license"></a>
## 📄 许可证

Casdoor 基于 [Apache License 2.0](https://github.com/casdoor/casdoor/blob/master/LICENSE) 开源。

---

<div align="center">

[![Made with ❤️](https://img.shields.io/badge/Made_with-%E2%9D%A4%EF%B8%8F-ff6b6b?style=flat-square&logoColor=white)](https://casdoor.ai) [![By Casdoor](https://img.shields.io/badge/by-Casdoor-4ecdc4?style=flat-square)](https://casdoor.ai)

<a href="https://github.com/casdoor/casdoor/stargazers"><img src="https://img.shields.io/github/stars/casdoor/casdoor?style=social&logo=github&label=Star" alt="GitHub Stars"></a>

<sub>© 2026 <a href="https://casdoor.ai">Casdoor</a>。遵循 <a href="https://github.com/casdoor/casdoor/blob/master/LICENSE">Apache License 2.0</a>。</sub>

</div>
