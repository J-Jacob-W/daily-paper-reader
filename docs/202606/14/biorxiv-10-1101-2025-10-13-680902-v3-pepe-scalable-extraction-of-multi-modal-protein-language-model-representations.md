---
title: "PEPE: Scalable extraction of multi-modal protein language model representations"
title_zh: PEPE：多模态蛋白质语言模型表示的可扩展提取
authors: "Zhong, J., Cardente, N., Bashour, H., Sandve, G. K., Abbate, M. F., Greiff, V."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.13.680902v3.full.pdf"
tags: ["query:multi-modal"]
score: 7.0
evidence: 可扩展的多模态蛋白质语言模型表示提取
tldr: 蛋白质语言模型（PLM）嵌入提取常因层、池化、填充的随意选择而效果不佳，大规模生成也受内存与计算瓶颈限制。PEPE工具通过并行流式架构，实现多模态嵌入的高通量提取，运行速度比顺序方法快数个数量级，且内存消耗稳定低。它支持多种主流PLM，接口灵活，使研究者能高效生成海量嵌入数据，助力结构、功能与进化下游任务的最优表示发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有PLM嵌入提取工作流依赖任意选择，导致表示次优，且大规模生成因内存累积和重复计算而效率低下。
method: PEPE采用并行化与流式架构，支持多种PLM，通过简单接口实现高效、高吞吐的多模态嵌入提取。
result: 相比传统方法，PEPE运行速度快数个数量级，内存消耗稳定低，甚至能在超出RAM容量下顺畅提取多模态嵌入。
conclusion: PEPE使研究人员能轻松生成大规模、多配置的嵌入数据集，从而为特定生物学语境筛选最优表示，无需额外计算资源。
---

## 摘要
动机：蛋白质语言模型（PLM）能够捕捉复杂的氨基酸依赖关系，生成编码丰富结构、功能和进化信息的嵌入向量。尽管具有潜力，当前的提取工作流程在嵌入层、池化和填充方面依赖任意选择，经常导致特征提取和下游分析中的次优表示。大规模嵌入生成进一步受限于计算和内存效率低下：(i) 在写入磁盘前将模型所有输出累积在内存中会造成严重瓶颈，(ii) 重复嵌入相同序列以提取不同模式引入了冗余计算，大幅降低了吞吐量和可扩展性。

结果：我们提出了PEPE（蛋白质嵌入的并行提取），一个命令行工具和Python库，能够从蛋白质语言模型中实现高效、高通量和多模态提取。PEPE的并行化和流式架构实现了比顺序方法快数个数量级的运行时间。与传统方法（其峰值内存使用量与输出大小线性增长，并在超过内存容量时失败）不同，PEPE保持稳定、低内存消耗，使得即使超出可用RAM也能进行多模态嵌入提取。通过简单灵活的接口，PEPE支持多种最先进和自定义的PLM。通过结合可扩展性、鲁棒性和易用性，PEPE使研究人员能够高效地生成大规模、信息丰富的嵌入数据集，并促进为结构、功能和进化下游任务发现最优表示。通过简化不同嵌入配置的生成，PEPE为研究人员提供了必要的数据，以识别特定生物学背景下的高性能潜在状态，而无需额外的计算资源。

可用性与实现：PEPE是一个用Python编写的命令行工具，基于MIT许可证发布。源代码和文档可在https://github.com/csi-greifflab/pepe-cli获取。PEPE也可从PyPI（https://pypi.org/project/pepe-cli）安装，并存储在Zenodo（https://zenodo.org/records/15912054）。

## Abstract
MotivationProtein language models (PLMs) capture intricate amino-acid dependencies, producing embeddings that encode rich structural, functional, and evolutionary information. Despite their potential, current extraction workflows rely on arbitrary choices, with respect to embedding layer, pooling, and padding, that frequently yield suboptimal representations for feature extraction and downstream analyses. Large-scale embedding generation is further limited by inefficiencies in computation and memory: (i) accumulating all model outputs in memory before writing to disk causes severe bottlenecks, and (ii) repeatedly embedding identical sequences to extract different modes introduces redundant computation and drastically reduces throughput and scalability.

ResultsWe introduce PEPE (Parallel Extraction for Protein Embeddings), a command-line tool and Python library that enables efficient, high-throughput, and multimodal extraction from protein language models. PEPEs parallelized and streaming-based architecture achieves runtimes several orders of magnitude faster than sequential approaches. Unlike conventional methods--whose peak memory usage scales linearly with output size and fails when memory capacity is exceeded--PEPE maintains stable, low memory consumption, enabling multimodal embedding extraction even beyond available RAM. PEPE supports a wide range of state-of-the-art and custom PLMs through a simple, flexible interface. By combining scalability, robustness, and ease of use, PEPE allows researchers to generate massive, information-rich embedding datasets efficiently, and facilitate the discovery of optimal representations for structural, functional, and evolutionary downstream tasks. By streamlining the generation of diverse embedding configurations, PEPE provides researchers with the necessary data to identify high-performing latent states for specific biological contexts without requiring additional computational resources.

Availability and ImplementationPEPE is a command-line tool written in Python and published under MIT license. The source code and documentation are available at https://github.com/csi-greifflab/pepe-cli. PEPE is also available for installation from PyPI under https://pypi.org/project/pepe-cli and deposited on Zenodo at https://zenodo.org/records/15912054.