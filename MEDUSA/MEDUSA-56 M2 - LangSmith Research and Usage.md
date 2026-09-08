---
jira_key: MEDUSA-56
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-56"
server: etas
kind: motivation
type: Story
status: In Progress
priority: Medium
project: MEDUSA
assignee: cin8sgh
reporter: tao9sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-02T03:26:50.000+0000"
updated: "2026-09-07T02:36:40.000+0000"
synced-at: "2026-09-08T01:43:02.635Z"
jira-orphaned: false
profile: Medusa
---

# MEDUSA-56 M2 - LangSmith Research and Usage

> [!jira] In Progress · Medium · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]] · 更新于 2026-09-07T02:36:40.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/MEDUSA-56)

## 描述

DoD:

1. Try LangSmith based on current Agent

2. Try what happened when SubAgent is running and stop the agent. Can the chat be recovered and continue? Who continues the dialog? The main orchestrator agent or the SubAgent? Observe by LangSmith.

Phase 1: 环境准备与账号配置（Day 1，0.5天）

- 注册/登录 LangSmith 账号（[https://smith.langchain.com](https://smith.langchain.com/)）
- 获取 API Key，配置环境变量：

```

LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=<your-api-key>
LANGCHAIN_PROJECT=<project-name>
```

- 安装 LangSmith SDK：pip install langsmith
- 验证连接：运行一个简单的@traceable函数，确保能在UI中看到Trace

Phase 2: 构建测试数据集（Day 1-2，1天）

- 编写2-3个测试用例
- 通过SDK创建数据集并导入用例：

```

python
from langsmith import Client
client = Client()
dataset = client.create_dataset(dataset_name="My Agent Test Set")
client.create_examples(dataset_id=dataset.id, examples=examples)
```

- 产出：LangSmith UI中可查看的Dataset
  测试用例建议：适合DBC Import场景的用例，如导入DBC，修改DBC后导入DBC， 使用一个新的DBC文件导入...

Phase 3: 配置评估器（Day 2-3，1.5天）

至少实现两种类型的评估器：

类型A：代码评估器（Code Evaluator） —— 用确定性规则打分

- 实现一个精确匹配评估器，检查Agent是否按照**正确的顺序**调用了必要的工具
- 实现一个工具调用次数统计评估器，从intermediate_steps中提取工具调用记录
- 检查在关键节点（如修改Parameter.ini、导入DBC）是否正确触发了人工确认

类型B：LLM作为评判官（LLM-as-Judge） —— 用大模型评估回答质量

- 通过LangSmith UI创建LLM-as-Judge评估器，配置提示词和评分维度（如相关性、准确性）

Phase 4: 运行离线实验（Day 3-4，1天）

- 使用run_on_dataset运行评估实验：

```

python
client.run_on_dataset(
dataset_name="My Agent Test Set",
func=your_agent_function,
evaluators=[exact_match_evaluator, quality_judge],
)
```

在LangSmith UI中查看实验进度和结果

Phase 5: 结果分析与迭代（Day 4-5，1天）

查看实验报告，筛选低分用例

点击单个失败案例，查看完整执行轨迹（Trace） ，定位问题环节（是误解了指令？还是工具调用出错？）

尝试修改一次提示词，重新运行实验，对比前后两次实验的分数变化

Phase 6: 文档与交付（Day 5，0.5天）

撰写简短总结文档，包含：

- 数据集设计思路
- 评估器类型及评分逻辑
- 实验结论（Agent在哪些维度表现好/差）
- 后续改进建议

✅ 验收标准

LangSmith中存在一个可用的测试数据集（2-3个用例）

至少成功运行过一次完整的离线实验

实验报告中包含至少2种评估指标的得分

能通过UI筛选出失败用例并查看Trace

完成一次"修改→重跑→对比"的迭代闭环

## 评论

> [!note]+ 2026-09-07 02:36 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]
> [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]] I updated the description with more details. Please have a look. Thank you.

-------

> [!note]+ 2026-09-04 09:18 · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]]
> The LangSmith web interface shows how long each action takes, such as tool calls and model calls, and allows us to inspect the detailed input and output of every step. ![[MEDUSA-56-image-2026-09-04-17-18-37-472.png]]

-------

> [!note]+ 2026-09-04 05:05 · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]]
> I registered for LangSmith using my personal Bosch email account. We can now use the LangSmith website to observe every step the agent takes while executing tasks, as shown in the image.

-------
