记忆形成的方式可以分为三种形式：直接记录形式、抽象蒸馏形式和类型路由形式


# 抽象蒸馏形式

# **1. [Recursively summarizing](https://pdf.sciencedirectassets.com/271597/1-s2.0-S0925231225X00205/1-s2.0-S0925231225008653/main.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjEEcaCXVzLWVhc3QtMSJIMEYCIQC6NzmNCH2Xi%2BPdZMU1LE%2F4sl3OSNc5xJkoMJipZBlOZgIhAI6Qh2KKwT5IwBr6KRYzCO8AvBynpqAKndNQwIa9zEQ8KrMFCBAQBRoMMDU5MDAzNTQ2ODY1IgxF15k1WYhdADUO65UqkAXvkCK8idiehx1SV5PgvRSgT1SiRvTNcI0GnRURtj0iZDhvx5pAUQc9bxUCwd1jNHXG7bvpg%2B9rgvvtzgh9YyA9lUIzhQrRXPhVtYWHCHJxCGYqRxDjQ%2B2DJ7NqHNT8lMGoqCRkL8idLFh3aFhdotE5smZ6eZYbg7Oe9%2FK10F%2BRQZWENlC%2F%2B%2B5tptUSjr4HypwJ3Us2COuCt1yv2t4Y6SBEFcO2jYvryD%2FmEXasOWlD5S08mi055F1r3IRwOGJyFUH2WtVEHN0ghQEX%2FPCyvdEbRJKmtPv2LdXlSimlfVezXuQkZ3Q8uGvuNMTblKVI8slzii9ep9vyiA%2B4rNfZqrvLIAhsrXT8zcNh53YJg0DddMRXqH%2FB2SftI%2FGeVr6a9o%2Fpc3OGhHgpjz%2FkGP8LGTBE5W%2FAMlHUzhL2WtLrVTOf09aMm%2FBst3dxOBca7aLFxF5V2p3%2FPCWV%2FZaw1EBa6D6LN4%2FsiO6HYw%2BRr2DD3UotsfeBJiCo7IHx%2BIG91fYvr%2FpKC%2FTZ%2F1%2FW9hER4KXgNnwMsJbsQjFbn2qbsGZeBA%2FJQ80rUYxRQ0e06baVRd6%2FKxrMTSClqsM4nPxfWEiltl84DLUOyIBroPl2xrioa5IugCEDGRWWA2LAe4StAz7x0x5lT%2FG%2FITQRq9BkL02XShDPzz6Fplb5fi4B6lAhBe7qfi2PiWk6YOMU9gsu0YWLC8Oq7aQnTxG%2B6ELgG5pMikDBaiOnvADVz4oEO3OUoKbZAwxJFstpQvCDWN%2FtBPABgc9OpcLvAcf%2FT34OP4JMj5oqwf6QBp3yecEGhoc6q1Sxc7AbM6rISdm1y1050C4gg1qqDdGHJkeg2Pa%2F%2F268wt%2BzSUVHMDG%2FHQvBT%2F3DPGRklTCZtNfSBjqwASQF6I8M0x1uFSsYlkj2UFIfyk%2BfkWQwZrwuZyy8gG3m8XhDFwfvWTBb44L9Zzpjf8P003Jt8R0ERMskCi6BRlpmAw29RYfmS7hzPryFnQXe58R0XX0xAke8IMbEPnkigQGXOTQaeLI4DuJIDGCzu9CdhHFHHEgX1lJ5Qm9OdbrX3PvjpiSPsc0tLqKoy7N0vKKp86zm2XE%2FeTK9Ik3fFoqv9ZudX7pxmrtJbhi9gSEz&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20260714T070427Z&X-Amz-SignedHeaders=host&X-Amz-Expires=299&X-Amz-Credential=ASIAQ3PHCVTYSE5RFXYN%2F20260714%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=6d679b04f157a8d0e2655dffaf42afc10c446210382f2fbb640060683df9b25f&hash=876d48b1e91d12be4834be82b35aa0460df1661c92f3c8af636a668209d68237&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=S0925231225008653&tid=spdf-920982b5-45c1-4f98-ac6b-f01b4d39dd61&sid=dcfdf58d861fb745d8781639c2b22173b91dgxrqa&type=client&tsoh=d3d3LnNjaWVuY2VkaXJlY3QuY29t&rh=d3d3LnNjaWVuY2VkaXJlY3QuY29t&ua=050e045600040404555a&rr=a1aeac645aae8591&cc=cn) Recursively summarizing enables long-term dialogue memory in large language models (26-7-14)**

论文通过递归总结的方式来产生记忆，并在每轮对话中结合新的记忆产生回答

## 现有方法及局限
- 基于检索的方法从对话历史检索关键信息，但是与问题相似度高的信息不一定是关键信息，检索效果依赖检索query的质量

- 过去的记忆模块往往是静态的，通常也会通过会话总结记忆摘要，但是这种摘要往往不会与当前会话进行交互更新，导致一些过时或不正确的信息损害生成质量。

- MemoChat通过模型总结为话题-内容的机构化记忆、MemoryBank对每个会话产生摘要，然后生成总体摘要。这些记忆方式都是静态的。

<p align="center">
<img src="./picture/recursively.png" width="100%" />
</p>

## 做法

作者如下图所示，提出对于每一轮会话进行递归总结，这样便维护了一个动态记忆内容。每次回复都基于问题和最新的记忆来生成。

<p align="center">
<img src="./picture/recursively2.png" width="100%" />
</p>

## 论文缺陷

- 这种每次递归的方法可能会产生严重的错误累积，当模型产生出一个错误事实时，这个错误可能会被一直保存
- 其次在多次重写时，可能会导致一些正确信息被不可避免的删除。
- 自然语言的摘要往往缺乏证据溯源
- 论文固定重写内容只有20句话，这属于超参数设定，对模型存在影响


# **2. [SeCOM](https://openreview.net/pdf?id=xKDZAW0He3): ON MEMORY CONSTRUCTION AND RETRIEVAL FOR PERSONALIZED CONVERSATIONAL AGENTS (26.7.14)**

论文提出了一种基于话题分割来组织记忆的方法，作者将开放对话切成主题连贯的语义片段名为Segment，再用压缩模型Compress压缩对话中冗余的部分。

## 现有缺陷
- 全历史拼接：虽然信息全，但是引入的噪声太多
- Turn-level级别的记忆：粒度太细，完整话题的语义可能被切分
- session-level级别的记忆：粒度太粗，容易引入话题无关的信息
- 摘要式的记忆：这种记忆方式容易丢失关键的细节

## 做法

1. 先使用LLM对长session切分为主体一致连贯的segment，将每个segment作为一个记忆单元
2. 对每个记忆单元进行压缩，保留关键的信息
3. 检索最相关的片段进行时间重排
4. 对于分割模型如果有少量的标注数据，则先通过zero-shot对模型进行输出，返回最困难的一部分样本，然后，通过LLM反思错误来更新分割的提示词，从而学习更好的分割规则


## 缺陷

- 论文依赖分割模型的性能
- 记忆体仍然是静态的，无法对两个冲突的内容进行校准
- 话题分割不一定符合任务，一个复杂的任务可能涉及多个话题
- 分段错误仍然会向下传递，同时压缩也会造成信息的损失