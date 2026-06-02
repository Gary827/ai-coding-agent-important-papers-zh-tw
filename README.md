# AI Coding Agent Important Paper

:::success
Refer from: https://www.vectorexplore.com/tech/agent/coding/papers.html
:::

:::info
AI Coding Agent 的演化截至目前為止可以分為以下幾個階段
1. 會寫程式碼的模型
1. 會推理與規劃
1. 會用工具執行
1. 會進行自我修正
1. 會進行多代理協作
1. 真實軟體任務評測與平台化

以下我們將整理以上這幾個階段的代表性論文, 同時也會整理其他的重要論文文獻
:::

## 第一階段: 讓LLM具備寫程式的能力(基石層級)
在這個階段, 先讓LLM具備一定程度的寫程式能力, 包含理解/生成/修正/補全等能力
### [Evaluating Large Language Models Trained on Code(Codex)](https://arxiv.org/abs/2107.03374)
OpenAI, 2021.07

#### 核心貢獻
* 首次證明 GPT 類模型可以大規模學習程式碼並完成：
* Code Completion
* Function Synthesis
* Documentation Generation
* 也是 GitHub Copilot 的基礎
* Agent的最底層能力就是能寫程式, 但還不會規劃

#### Keywords
Code Generation, Code Completion, HumanEval, Program Synthesis, Few-shot Coding


### [Competition-Level Code Generation with AlphaCode](https://arxiv.org/abs/2203.07814)
DeepMind, 2022.03
#### 核心貢獻
* 提出: 大量生成->排序->過濾 的競賽程式解法流程
* 第一次接近人類競程選手水準
* 開始有Search + Reasoning的概念出現
* 影響後面的 Tree of Thoughts

#### Keywords
Sampling, Ranking, Competitive Programming, Search, Program Synthesis


### [Code Llama: Open Foundation Models for Code](https://arxiv.org/abs/2308.12950)
Meta, 2023.08
#### 核心貢獻
第一個開源且高品質的Coding LLM
Agent不再依賴Closed-source LLM
#### Keywords
Intruction Tuning, Long Context

## 第二階段: Prompt / Context 時代
### [Language Models are Few-Shot Learners (GPT-3)](https://arxiv.org/abs/2005.14165)
OpenAI, 2020.05

#### 核心貢獻
* 提出In-context Learning, 模型不用訓練, 只靠Prompt
* 使Agent的本質變成Model + Prompt + Memory, 即是從這邊開始
#### Keywords
Few-shot Learning, Prompt Engineering, In-context Learning, Emergent Ability



## 第三階段: Reasong Agent
### [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903)
Google, 2022.03
#### 核心貢獻
* 要求模型一步一步思考, 變成Question -> Reasoning -> Answer
* Agent第一次出現Thought, 但其實是發生在模型端
#### Keywords
Reasoning, step-by-step, CoT, Inference

### [Self-Consistency Improves Chain of Thought Reasoning in Language Models](https://arxiv.org/abs/2203.11171)
Google, 2022.03
#### 核心貢獻
* 提出一種自一致性(Self-Consistency)的策略, 通過生成多條不同的Chain-of-Thought(CoT)推理路徑篩選出一致的答案, 顯著提升語言模型在多部推理任務中的準確性與魯棒性
* Agent開始探索多個可能的世界
#### Keywords
Sampling, voting, Reasoning Ensemble


### [Least-to-Most Prompting Enables Complex Reasoning in Large Language Models](https://arxiv.org/abs/2205.10625)
2022.05
#### 核心貢獻
* 將複雜的問題分解為有序列的子問題並逐步求解的提示技巧, 對任務分解與規則類Agent非常有用
* Agent學會規劃能力的起點
#### Keywords
Hierarchical Reasoning, Planning, Task Decomposition


### [Tree of Thoughts: Deliberate Problem Solving with Large Language Models](https://arxiv.org/abs/2305.10601)
Princeton, Google, 2023.05

#### 核心貢獻
* 提出思維樹(Tree-of-thought), 突破大語言模型傳統的線性推理模式, 推過讓模型透過多路徑思維分支並迭代評估, 顯著提升其在複雜推理任務的問題解決能力與準確性.
* 第一次有了Planning Agent的概念

## 第四階段: Tool Use Agent
### [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)
Google Research, 2022.10
#### 核心貢獻
* 提出Agent Loop, Thought -> Action -> Observation -> Thougth
* 雖然ReAct(Reason + Act), 並非專屬的程式碼領域, 但他對於Coding Agent非常重要. 
* 他能讓模型生成推理軌跡與具體動作（工具調用/執行代碼), 這對於調試, 使用API等任務

#### Keywords
Tool Use, Action, Reasoning, Agent Loop

### [Toolformer: Language Models Can Teach Themselves to Use Tools ](https://arxiv.org/abs/2302.04761)
Meta, 2023.02

#### 核心貢獻
* 教模型自己決定什麼時候使用工具
* 提出一種讓語言模型通過Self-Supervised learning的方式學會使用外部工具(計算機, 搜尋引擎, 代碼解釋器)等方法.
* Function Calling的始祖
#### Keywords
Self-supervised, Function Calling, Tool Selection


### [SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering](https://arxiv.org/abs/2405.15793)
Princeton, 2024.05
#### 核心貢獻
* 把ReAct這個範式套用到真實的Repo
* 可以進行程式閱讀, 修改程式, 執行測試等
* 真正的Coding Agent正式誕生 ！
#### Keywords
Software Engineering, GitHub Issues, Terminal Agent, Code Repair

## 第五階段: Memory + Reflection
### [Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442)
Princeton, 2023.04

#### 核心貢獻
* 提出Memory, Planning, Reflection等三層架構
* 現代AGent記憶系統的祖先
* 通過整合記憶, 規劃, 反射機制, 建構出模擬人類日常行為且能進行長期互動並自主演化社會動態的Agent
#### Keywords
Memory, Planning, Reflection, Long-term Memory


### [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366)
Northeastern University, 2023.03
#### 核心貢獻
* Agent開始會檢討自己
* Agent開始學會反思並改進策略, 直接相關於自我驗證持續學習的主題
#### Keywords
Reflection, Verbal Reinforcement, Self-Improvement, Retry


### [Self-Refine: Iterative Refinement with Self-Feedback](https://arxiv.org/abs/2303.17651)
CMU, 2023.03
#### 核心貢獻
* Agent自己當Reviewer
* 提出一種無需監督訓練資料或額外訓練或強化學習的Self-Refine方法, 通過讓單一大型語言模型對自身輸出進行迭代反饋和細化, 提升任務性能
#### Keywords
Feedback, Self-Critique, Itertive Refinement

### [Teaching Large Language Models to Self-Debug](https://arxiv.org/abs/2304.05128)
Google, 2023.04
#### 核心貢獻
* 讓LLM Debug自己寫的程式碼
* 提出一種訓練方法, 使LLM能夠在生成程式碼後自動識別並糾正自身錯誤, 顯而提升程式碼生成與問題求解的可靠性與正確率
#### Keywords
Debugging, Code Repair, Self Correction


### [Voyager: An Open-Ended Embodied Agent with Large Language Models](https://arxiv.org/abs/2305.16291)
NVIDIA, 2023.05
#### 核心貢獻
* 在Minecraft環境中提出自我改進的Agent, 利用LLM生成程式碼並在外部執行環境中測試與迭代, 實現基於工具的持續技能學習與能力累積
* 長期記憶的重要里程碑
#### Keywords
Skill Library, Curriculem Learning, Lifelong Learning, Embodied Agent

## 第六階段: Multi-Agent

### [Improving Factuality and Reasoning in Language Models through Multiagent Debate](https://arxiv.org/abs/2305.14325)
MIT, 2023.05

#### 核心貢獻
* 提出Multi-Agent Debate Framework(辯論框架), 有效提升語言模型在事實性和推理任務的表現, 突破單模型依賴自身知識的侷限, 也進而降低幻覺
#### Keywords
Debate, Consesus, Reasoning, Collaboration


### [AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation](https://arxiv.org/abs/2308.08155)
Microsoft, 2023.08

https://github.com/microsoft/agent-framework

#### 核心貢獻
* 提出AutoGen框架, 通過標準化Multi-Agent對話流程與靈活的交互機制, 降低了下一代語言模型複雜應用的開發門檻, 推動Multi-Agent技術的應用化落地
* Multi-Agent工程框架的始祖
#### Keywords
Multi-Agent, Conversation, Workflow, Framework


### [AgentVerse: Facilitating Multi-Agent Collaboration and Exploring Emergent Behaviors](https://arxiv.org/abs/2308.10848)
北京清華大學, 2023.08
#### 核心貢獻
提出AgentVerse框架, 該框架不僅為Multi-Agent協作提供靈活和可擴展的開發與部署平台, 還通過系統性探索, 展示了Multi-Agent交互中湧現的複雜群體行為, 推動Multi-Agent從功能性實現轉向行為機制研究.
#### Keywords
Agent Society, Role Playing, Collaboration


### [MapCoder: Multi-Agent Code Generation for Competitive Problem Solving](https://arxiv.org/abs/2405.11403)
Bangladesh University of Enginering and Technology, 2024.05
#### 核心貢獻
使用Multi-Agent專門用於解程式碼的問題
Coding Agent 多協作的代表之一
#### Keywords
Coding Agent, Planning, Program Synthesis, Multi-Agent


## 第七階段: 真實的Software Engineering Benchmark
### [SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://arxiv.org/abs/2310.06770)
Princeton, 2023.10
#### 核心貢獻
* 提出一個衡量語言模型解決真實世界軟體工程問題能力的基礎, 其核心創新在於從開源項目中提取已修復的GitHub問題作為評估任務
* 第一次針對真實的GitHub issue所做的測試
* 取代HumanEval成為評估Coding Agent的主流指標Benchmark
#### Keywords
GitHub, Bug Fixing, Software Engineering, Benchmark


### [LiveCodeBench: Holistic and Contamination Free Evaluation of Large Language Models for Code](https://arxiv.org/abs/2403.07974)
UC Berkeley, 2024.03

#### 核心貢獻
* 提出LiveCodeBench基準測試集, 針對現有程式碼評估基準的"資料污染嚴重, 任務場景單一, 評估維度過於片面"等關鍵痛點, 建構一套全面, 無污染的大型語言模型程式碼能力評估體系, 為LLM程式碼能力的客觀, 可靠評測提供新的Benchmark
#### Keywords
Contamination, Competitive programming, Live Benchmark


### [ML-Bench: Evaluating Large Language Models and Agents for Machine Learning Tasks on Repository-Level Code](https://arxiv.org/abs/2311.09835)
Yale University, 南京大學, 北京大學, 2023.11

#### 核心貢獻
* 第一個測試ML Researcher Agent的Benchmark
#### Keywords
Machine Learning, Research Agent, Experiment


### [GitTaskBench: A Benchmark for Code Agents Solving Real-World Tasks Through Code Repository Leveraging](https://arxiv.org/abs/2508.18993)
中國科學院大學, 北郵, 2025.08

#### 核心貢獻
* 評估大型的Repo任務
#### Keywords
Repository Level, Software Engineering, Task Execution


## 第八階段: 真正的Coding Agent

### [OpenHands: An Open Platform for AI Software Developers as Generalist Agents](https://arxiv.org/abs/2407.16741)
UIUC, 2024.07
#### 核心貢獻
* 發不了面向LLM Agent的開源平台, 提供標準化API, 執行追蹤與基準工具, 降低建構與評估代理系統的工程門檻
#### Keywords
Terminal Agent, Browser Agent, Open Source Devin


### [Executable Code Actions Elicit Better LLM Agents](https://arxiv.org/abs/2402.01030)

#### 核心貢獻
* Code = Action
* Agent 用程式碼作為行動語言
#### Keywords
Code-as-Action, Executable Planning, Environment Interaction
