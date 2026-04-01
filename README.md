# Metaverse Fans

Metaverse Fans 是一个面向 AI、机器人和太空探索爱好者的社区平台，提供论坛、实时聊天、AI 助手、新闻聚合、用户等级与 NFT 勋章等功能，支持一键 Docker 部署与自动化 CI/CD 流水线。

## 主要功能

- 用户认证（JWT）
- 论坛系统（发帖、评论、点赞）
- 实时聊天（Socket.IO）
- AI 助手（LangChain + OpenAI）
- 新闻聚合（ArXiv、NASA 等）
- NFT 勋章（ERC721，支持铸造与转移）
- 用户等级与积分系统���1-10 等级）
- 排行榜与成就展示
- Docker 化部署与 GitHub Actions CI/CD

## 技术栈

- 后端：Node.js、Express、TypeScript、Sequelize、PostgreSQL、Redis
- 前端：React 18、Vite、TypeScript、Tailwind CSS、Zustand
- 区块链：Solidity (ERC721)、Hardhat、Ethers.js
- AI：LangChain、OpenAI
- 部署：Docker / Docker Compose, GitHub Actions

## 快速开始（Docker）

1. 克隆仓库：

```bash
git clone https://github.com/Anmulzhao/Metaverse-fans.git
cd Metaverse-fans
```

2. 复制环境模板并修改：

```bash
cp .env.example .env
# 编辑 .env，填入数据库、RPC、私钥等配置
```

3. 启动服务：

```bash
docker-compose up --build
```

4. 访问：
- 前端: http://localhost
- 后端 API: http://localhost:3000

## 本地开发（分别运行）

- 后端：
```bash
cd server
npm install
npm run dev
```

- 前端：
```bash
cd client
npm install
npm run dev
```

- 智能合约（本地测试）：
```bash
cd smart-contracts
npm install
npx hardhat node
npx hardhat run scripts/deploy.ts --network localhost
```

## 环境变量示例 (.env.example)

- DATABASE_URL
- POSTGRES_USER/POSTGRES_PASSWORD
- REDIS_URL
- JWT_SECRET
- OPENAI_API_KEY
- CHAIN_ID, RPC_URL, PRIVATE_KEY
- BADGE_CONTRACT_ADDRESS
- IPFS_GATEWAY

## CI/CD

本仓库包含 GitHub Actions 工作流：
- `.github/workflows/ci.yml`：代码检查、测试与构建
- `.github/workflows/deploy.yml`：基于标签的自动发布（创建 Release）

发布示例：推送 tag，例如 `git tag v1.0.0 && git push origin v1.0.0`，工作流将自动创建 Release。

## 合约部署

使用 Hardhat 部署 NFT 合约：

```bash
cd smart-contracts
npx hardhat run scripts/deploy.ts --network mumbai
```

部署完成后，将合约地址配置到后端 `.env` 中的 `BADGE_CONTRACT_ADDRESS`。

## 贡献

欢迎贡献代码、提交 issue 或发起 PR。请遵循以下流程：

1. Fork 仓库
2. 新建分支 `feature/your-feature`
3. 提交并推送分支
4. 提交 Pull Request

## 许可证

本项目使用 MIT 许可证，详见 LICENSE 文件。

## 联系

如需支持，请在 GitHub 上打开 issue，或联系项目负责人。

---

Generated and committed by GitHub Copilot on behalf of the project owner.