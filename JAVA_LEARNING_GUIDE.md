# Spring AI Examples Java 学习指南

## 一、项目概览与学习目标
本指南面向只使用 Java 的学习者，帮助你在 Spring AI Examples 仓库中快速入门并逐步进阶。

学习目标：
1. 掌握 Spring AI 的核心理念与配置方式；
2. 通过运行示例理解 ChatClient、函数回调、流式响应等技术；
3. 学习代理工作流、MCP 集成与 Prompt Engineering；
4. 能够在实际项目中迁移或扩展这些示例。

---

## 二、环境准备（第 0 周）
- 安装 JDK 17、Maven 与 Git；
- 设置 OpenAI API Key；
- 在仓库根目录执行 `./mvnw -q help:evaluate -Dexpression=project.version` 确认构建工具可用；
- 阅读根目录 `README.md` 与 `CLAUDE.md`，了解构建与运行要求。

理论要点：
- Spring Boot 项目结构与 Maven 模块化；
- ChatClient 基础概念与配置。

---

## 三、学习计划（4 周）

### 第 1 周：ChatClient 入门
**理论：**
- 消息构建、响应封装、CommandLineRunner 使用。

**实践：**
- 模块：`models/chat/helloworld`
  - 阅读 `HelloWorldApplication`；
  - 运行 `./mvnw -q -pl models/chat/helloworld spring-boot:run`；
  - 修改 prompt，观察输出变化。

### 第 2 周：函数回调与流式响应
**理论：**
- 函数调用在 LLM 应用中的作用；
- WebFlux 与 SSE 流式接口。

**实践：**
- 模块：`misc/spring-ai-java-function-callback`
  - 运行项目，理解如何通过回调返回天气数据；
  - 添加一个新的城市测试数据。
- 模块：`misc/openai-streaming-response`
  - 启动服务并用 `curl` 请求，体验逐步输出。

### 第 3 周：Agentic Patterns 与 Reflection Agent
**理论：**
- 多步骤智能体工作流；
- 自我反思与迭代优化。

**实践：**
- 模块：`agentic-patterns/*`
  - 依次运行 `chain-workflow`、`routing-workflow` 等示例，修改提示词或参数。
- 模块：`agents/reflection`
  - 让代理生成或批判一段 Java 代码，体验生成/反思循环。

### 第 4 周：Model Context Protocol 与 Prompt Engineering
**理论：**
- MCP 工具注册机制与上下文传递；
- 常见 Prompt Engineering 策略。

**实践：**
- 模块：`model-context-protocol/sqlite/simple`
  - 使用自然语言查询 SQLite 数据库，并尝试扩展表结构；
- 模块：`prompt-engineering/prompt-engineering-patterns`
  - 对照示例练习 Chain-of-Thought、Few-shot 等提示模板。

---

## 四、进阶与拓展
- 阅读 `integration-testing` 目录，了解 AI 驱动的测试思路；
- 将某个示例迁移到其他模型提供方（如 Azure OpenAI、Anthropic）。

---

## 五、学习建议
1. 每次运行示例前先阅读 `README` 与 `pom.xml`；
2. 记录实验使用的 prompt、参数与输出；
3. 常用 `./mvnw -q -pl <module> spring-boot:run` 运行示例；
4. 在实践中持续调整提示词和配置，观察模型行为。

祝你在 Spring AI 的 Java 世界中学习顺利！
