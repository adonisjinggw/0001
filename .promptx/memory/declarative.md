# 陈述性记忆

## 高价值记忆（评分 ≥ 7）

- 2025/06/11 01:37 角色0 - 顶级全栈调度者：自动分析用户输入，将需求转化为专业术语并分发给最合适的AI专业角色，协调全流程产出。具备自然语言理解、术语转换、任务拆解、智能分发、全流程追踪与多角色协作能力。能够根据需求自动切换/组合子角色，也支持用户在关键节点手动指定优先角色。输出方案时融合多角色最佳实践，确保高质量和可落地性。工作流程：1.分析用户输入，提取核心需求与目标 2.将需求转化为各专业角色能理解的术语/任务 3.分发任务给前端、UI、动画、后端等角色 4.多轮澄清歧义，自动补全缺失信息 5.追踪执行进度，自动协调冲突 6.汇总产出，反馈给用户 --tags 角色0 顶级全栈调度者 智能分发 多角色协作 需求分析 任务拆解 ##最佳实践 #流程管理 #评分:8 #有效期:长期



- 2025/06/11 10:32 女娲混合修复方案第一阶段完成：
1. 创建了FreeApiKeyHelper免费API获取助手组件，支持6种免费AI服务的一键获取指导
2. 改进imageGenerationService，将Pollinations.AI设为优先服务，确保用户总能生成图片
3. 新增pollinationsService完全免费图像生成服务，支持多种模型和批量生成
4. 在App.tsx中集成了获取API按钮，提供显眼的UI入口
5. 解决了"图像生成API不好用"和"获取API方法丢失"的核心问题

技术栈：React + TypeScript + Tailwind CSS + 多AI服务商集成
修改文件：FreeApiKeyHelper.tsx(新增), imageGenerationService.ts, pollinationsService.ts(新增), App.tsx --tags API修复 免费服务 图像生成 Pollinations 用户体验 ##其他 #评分:8 #有效期:长期

- 2025/06/11 11:07 API架构全面修正完成：

1. 【腾讯混元API分离】
   - 文生文：https://api.hunyuan.cloud.tencent.com/v1 (OpenAI兼容)
   - 文生图：https://api.hunyuan.cloud.tencent.com/v1 (OpenAI兼容，与文生文共用)
   - 腾讯云原生：https://hunyuan.tencentcloudapi.com (需要特殊签名，暂不支持)

2. 【API验证系统】
   - 创建了统一的apiConfigValidator.ts服务
   - 支持密钥格式验证、端点检查、配置健康报告
   - 自动检测示例地址、错误配置等问题

3. 【服务恢复】
   - 恢复腾讯混元图像生成在优先级列表中的位置
   - 修正图像生成服务中的处理逻辑
   - 更新配置界面的提示信息

4. 【配置统一】
   - 所有API服务使用标准化的端点配置
   - 提供智能的配置修复建议
   - 支持批量API连接测试

技术要点：文生文和文生图可能使用不同的API架构，需要分开处理和验证。 --tags API修正 配置验证 腾讯混元 图像生成 系统架构 ##其他 #评分:8 #有效期:长期