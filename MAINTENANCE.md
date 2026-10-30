# AI_Chess_Alphazero 维护说明

使用蒙特卡洛树搜索与 Paddle/PyTorch 网络训练中国象棋 AI。

- 上游：https://github.com/tensorfly-gpu/aichess
- 在线文档：https://xiaoshecode.github.io/xiaoshecode/repos/AI_Chess_Alphazero/
- 检查日期：2026-10-30

## 环境与使用

- 安装与显卡 CUDA 匹配的 PyTorch 或 Paddle GPU 环境；配置 config.py 的 use_frame 和模型路径。

使用/检查入口（需先满足依赖条件）：

- `python collect.py`
- `python train.py`
- `python play_with_ai.py`

## 目录职责

- game.py — 棋盘规则
- mcts.py / mcts_pure.py — 搜索
- pytorch_net.py / paddle_net.py — 网络后端
- collect.py / train.py — 自我对弈与训练
- config.py — 参数与 Redis 配置

## 本次整理

- 新增维护文档和在线文档入口，补全用途、目录、使用路径及验证边界。
- 更正 Paddle 后端选择说明误写为 PyTorch 的问题。

## 检查记录

- **仓库目录与入口盘点**（passed）：检查 Git 索引中的 37 个路径、README 和项目配置；不等于功能验收。
- **Python AST**（passed）：13 个文件通过解析；不导入依赖、不执行应用。
- **完整构建与端到端运行**（not_run）：没有可复现的依赖锁文件；训练需要 GPU、模型和数据，未进行训练或 GUI 联调。

## 验证边界与待办

- 没有可复现的依赖锁文件；训练需要 GPU、模型和数据，未进行训练或 GUI 联调。

## 后续维护约定

保留上游许可证与作者信息。沿用现有模块边界和格式配置；修复功能时同步最小回归验证。依赖或接口变更需写明迁移步骤，避免仅为目录美观搬动公开入口。
