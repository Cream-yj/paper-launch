# 防御性写作对照示例

所有方法名、数字和设定均为虚构，只演示改写方式。使用时以用户材料为准。

## 结果领先于自我评价

已知证据：相同预算下，攻击成功率由 42.0% 降至 11.0%；干净任务准确率由 91.5% 变为 91.2%。这是一个以攻击防御为目标的研究。

原文：

> Unfortunately, our method still falls behind the baseline in clean accuracy, although it reduces attack success.

改写：

> Under the same budget, our method reduces attack success from 42.0% to 11.0%, with clean-task accuracy of 91.2% compared with the baseline's 91.5%.

原因：先讲研究目标及关键证据，同时保留 0.3 个百分点的准确率差异。不凭空声称“零代价”或“没有显著下降”；统计显著性需要另外的依据。

## 方法设计替代尝试过程

已知证据：最终方法把记忆的来源核验与任务相关性评分分开，核验发生在记忆注入上下文之前。用户没有提供对照实验。

原文：

> We first tried a single prompt, which did not work well. We then added another module and eventually used two stages.

改写：

> We separate memory provenance checking from task-relevance scoring, checking provenance before admitting a memory into the agent's context.

原因：直接说明最终机制。不把缺失的比较结果补写成“two stages outperform a single prompt”。如果尝试过程承担关键的消融论证，应在对应实验中保留它。

## 必要限定应保留

已知证据：在两个数据集、固定检索器的设置下观察到收益，尚未验证其他检索器。

原文：

> Our method only works on the two evaluated datasets, and its generalization remains uncertain.

改写：

> With the retriever held fixed, our method improves performance on both evaluated datasets.

原因：这句原文把未验证的泛化误写成“只在两个数据集上有效”。改写准确表述已观察到的结果，保留实验范围。若跨检索器泛化是论文核心主张，则另列需要补的实验，不能宣称已经实现。

## 正当效率维度需要直接比较

已知证据：部署约束是检索时间不超过 30 ms；A 为 20 ms、准确率 85%，B 为 80 ms、准确率 90%。比较采用相同硬件与检索规模。

原文：

> Although A is less accurate than B, it is a reasonable trade-off.

改写：

> Under the 30 ms retrieval constraint, A achieves 85% accuracy at 20 ms. B reaches 90% accuracy at 80 ms under the same hardware and retrieval scale.

原因：用有来源的部署目标解释价值，同时保留性能差异。没有部署约束时，不能为了使 A 胜出而临时编造 30 ms 门槛。

## 无依据的权衡不能靠改写成立

已知证据：A 的准确率为 70%，B 为 80%；没有成本、延迟或其他收益测量。原研究目标是提高准确率。

原文：

> A sacrifices a little accuracy for superior efficiency.

可用改写：

> A achieves 70% accuracy in this setting, compared with B's 80%.

作者待办：现有证据不能支持效率优势，也不能支持原来的准确率提升主张。补充效率测量或重新形成有证据的研究主张，再决定如何组织叙事。

原因：有力写作不要求把每个不利结果变成胜利。此时不编造“reasonable trade-off”，也不通过改名或更换分母制造优势。

## 推测不能升级为因果

已知证据：长记忆组的攻击成功率高于短记忆组，但两组任务和攻击内容也不同。

原文：

> These observations may potentially suggest that longer memory might increase vulnerability.

改写：

> Attack success is higher in the long-memory group, suggesting an association between memory length and vulnerability in the evaluated settings.

原因：去掉重复犹疑，保留相关性证据的力度。若要写“longer memory causes vulnerability”，需要控制其他差异。

## 让表格承担明确论证

已知证据：表 2 中，完整方法为 84%，移除来源检查为 72%，其他设定不变。

原文：

> Table 2 presents our ablation results.

改写：

> Provenance checking contributes to performance: removing it reduces accuracy from 84% to 72% under the same setting (Table 2).

原因：主动说出消融支持的判断，不扩大为“唯一关键机制”或“所有组件都不可或缺”。

## 结论保留记忆点

已知证据：方法在评估设置下通过来源检查减少恶意记忆被接纳，未评估其他来源核验方案。

原文：

> We propose a memory admission check. However, our approach is far from perfect and many challenges remain.

改写：

> Our results show that checking provenance at memory admission reduces the acceptance of malicious memories in the evaluated settings.

原因：落在机制与实证结果上，不追加空泛自我否定。不能由此声称来源检查优于所有替代方案；需要披露的具体边界应在相关位置说明。
