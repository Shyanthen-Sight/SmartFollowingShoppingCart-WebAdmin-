# IFCweb — 商场智能跟随购物车 · Web 管理端

商场管理员使用的 Web 管理端：查看车辆状态、下发控制指令、查看运行日志。

- 技术栈：Vue 3（`<script setup>` + TS）+ Vite + Vue Router + Pinia
- 全 TypeScript strict，`noUncheckedIndexedAccess` 已开，禁止 `any`
- 协议合同：与车端、小程序共用 `docs/protocol.md`，**字段名不得改名或增删**
- 硬约束：前端**不直接** publish `car/{id}/cmd`，指令统一由后端下发

## 命令

```bash
npm install
npm run dev        # 本地开发
npm run build      # 类型检查 + 构建
npm run type-check # 仅类型检查
npm run lint       # oxlint + eslint
npm run format     # prettier 格式化
```

## 目录

```
src/
├── assets/      # 全局样式
├── components/  # 通用组件
├── router/      # 路由
├── stores/      # Pinia 状态
└── views/       # 页面
```

## 开发约定

1. 一次只做一个页面，先写**静态假数据版**，不接真实 MQTT。
2. 页面做通后再把假数据换成 store，最后换订阅。
3. 每次改完列出改动的文件。

## 相关仓库

- 小程序用户端：`SmartFollowingShoppingCart-MiniApp`
- 本仓库：`SmartFollowingShoppingCart-WebAdmin-`
