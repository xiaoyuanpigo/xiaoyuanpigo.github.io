---
title: "DeCoMa: Detecting and Purifying Code Dataset Watermarks through Dual Channel Code Abstraction"
authors: 
    - <strong>Yuan Xiao</strong>, Yuchen Chen, Shiqing Ma, Haocheng Huang, Chunrong Fang<sup>*</sup>, Yanwei Chen, Weisong Sun, Yunfeng Zhu, Xiaofang Zhang, Zhenyu Chen<sup>*</sup>
collection: publications
permalink: /publication/issta2025
excerpt: ''
date: 2025-06-01
venue: 'International Symposium on Software Testing and Analysis'
location: 'Trondheim, Norway'
githuburl: 'https://github.com/xiaoyuanpigo/DeCoMa'
# slidesurl: '../files/cvpr2024.pptx'
paperurl: '../files/issta2025.pdf'
weight: 1
# citation: '@inproceedings{xiao2024towards,
#   title={Towards General Robustness Verification of MaxPool-based Convolutional Neural Networks via Tightening Linear Approximation},
#   author={Xiao, Yuan and Ma, Shiqing and Zhai, Juan and Fang, Chunrong and Jia, Jinyuan and Chen, Zhenyu},
#   booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
#   pages={24766--24775},
#   year={2024}
# }'
---

Watermarking is a technique to help identify the source of data points, which can be used to help prevent the misuse of protected datasets. Existing methods on code watermarking, leveraging the idea from the backdoor research, embed stealthy triggers as watermarks.Despite their high resilience against dilution attacks and backdoor detections, the robustness has not been fully evaluated. To fill this gap, we propose  DeCoMa, a dual-channel approach to Detect and purify Code dataset waterMarks.To overcome the high barrier created by the stealthy and hidden nature of code watermarks, DeCoMa leverages dual-channel constraints on code to generalize and map code samples into standardized templates. Subsequently, DeCoMa extracts hidden watermarks by identifying outlier associations between paired elements within the standardized templates. Finally, DeCoMa purifies the watermarked dataset by removing all samples containing the detected watermark, enabling the silent appropriation of protected code. We conduct extensive experiments to evaluate the effectiveness and efficiency of DeCoMa, covering 14 types of code watermarks and 3 representative intelligent code tasks (a total of 14 scenarios). Experimental results demonstrate that DeCoMa achieves a stable recall of 100% in 14 code watermark detection scenarios, significantly outperforming the baselines. Additionally, DeCoMa effectively attacks code watermarks with embedding rates as low as 0.1%, while maintaining comparable model performance after training on the purified dataset. Furthermore, as DeCoMa requires no model training for detection, it achieves substantially higher efficiency than all baselines, with a speedup ranging from 31.5 to 130.9X. The results call for more advanced watermarking techniques for code models, while DeCoMa can serve as a baseline for future evaluation.
