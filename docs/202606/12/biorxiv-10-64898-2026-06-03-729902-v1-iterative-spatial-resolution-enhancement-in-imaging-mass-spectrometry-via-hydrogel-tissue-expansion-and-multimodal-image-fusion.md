---
title: Iterative Spatial Resolution Enhancement in Imaging Mass Spectrometry via Hydrogel Tissue Expansion and Multimodal Image Fusion
title_zh: 通过水凝胶组织扩张与多模态图像融合实现成像质谱中的迭代空间分辨率增强
authors: "Mayo, E., Samuel, J. M., Guo, Y., Ciccone, A. B., Liang, Z., Prentice, B. M."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729902v1.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 多模态图像融合用于分辨率增强
tldr: 成像质谱像素尺寸受限于探针直径和步长。水凝胶膨胀（ExM）可物理放大组织，但分辨率提升有限。本文提出ExFusion，将膨胀显微镜（ExM）的荧光图像与膨胀成像质谱（ExIMS）的脂质数据进行多模态融合，对9.4倍膨胀小鼠脑组织进行10倍计算上采样，在10 μm步长下实现约106 nm有效像素尺寸，清晰解析小脑浦肯野细胞的亚细胞脂质分布。该方法为亚细胞分辨率质谱成像提供了实用路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 突破成像质谱的固有空间分辨率极限，实现亚细胞水平的原位脂质检测。
method: 结合水凝胶组织膨胀（9.4倍）与多模态图像融合（荧光-质谱），对同一组织进行联合采集与计算上采样（10倍）。
result: 在商用质谱仪上以10 μm步长获取约106 nm像素尺寸的脂质图像，清晰展现浦肯野细胞中脂质的细胞内分布。
conclusion: ExFusion通过物理膨胀与计算融合协同，显著提升IMS分辨率，为亚细胞脂质成像提供有效手段。
---

## 摘要
成像质谱（IMS）的像素尺寸从根本上受到多个因素的限制，包括入射探针的直径和样品台的栅格步长。我们之前已证明，最初为显微镜开发的基于水凝胶的组织膨胀（ExM）也可适用于成像质谱，以物理放大组织尺寸。膨胀成像质谱（ExIMS）使用超吸水水凝胶各向同性地膨胀薄组织切片，然后通过成像质谱采样，从而提高有效空间分辨率。另外，多模态图像融合已被用于通过预测性地将质谱强度值映射到同一组织切片的显微镜图像的更小像素尺寸，以计算方式上采样成像质谱的有效空间分辨率。在此，我们提出ExFusion，一种统一的工作流程，通过计算融合从同一9.4倍膨胀的小鼠脑组织获得的具有结构细节的荧光ExM和具有化学细节的脂质ExIMS数据，结合了这两种方法。在图像融合进行10倍上采样后，多模态膨胀图像融合使得能够在商业质谱仪上以10 μm栅格步长预测约106 nm像素尺寸的质谱图像。在此分辨率下，小脑浦肯野细胞中的脂质清晰可见，并具有细胞内分布。

## Abstract
The pixel size of imaging mass spectrometry (IMS) is fundamentally limited by several factors, including the diameter of the incident probe and the raster step size of the sample stage. We have previously demonstrated that hydrogel-based tissue expansion, originally developed for microscopy (ExM), can also be adapted for imaging mass spectrometry to physically magnify the size of the tissue. Expansion imaging mass spectrometry (ExIMS) uses a superabsorbent hydrogel to isotropically expand thin tissue sections, which can then be sampled via imaging mass spectrometry, resulting in improved effective spatial resolution. Separately, multimodal image fusion has been used to computationally upsample the effective spatial resolution in imaging mass spectrometry by predictively mapping mass spectrometric intensity values to the smaller diameter pixel sizes of a microscopy image of the same tissue section. Here, we present ExFusion, a unified workflow that combines these two approaches by computationally fusing structurally detailed fluorescent ExM and chemically detailed lipid ExIMS data obtained from the same 9.4-fold expanded mouse brain tissue. Following a 10-fold upsampling from image fusion, multimodal expansion image fusion enabled prediction of MS images at a [~]106 nm pixel size on a commercial mass spectrometer using a 10 m raster step size. At this resolution, lipids in the Purkinje cells of the cerebellum are clearly defined with intracellular distributions.