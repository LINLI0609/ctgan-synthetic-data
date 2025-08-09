# CTGAN Synthetic Data Generation

本项目是一个使用 **CTGAN** 生成合成数据的学习项目，参考了教程：
[https://www.mvrlink.com/synthesize-data-using-generated-ai/](https://www.mvrlink.com/synthesize-data-using-generated-ai/)
项目的数据集来源于kaggle：
https://www.kaggle.com/datasets/drrayislam/synthetic-credit-analysis-data-by-ctgan

## 项目简介
本项目的主要目标：
1. 加载原始数据集，并进行数据清洗。
2. 使用 CTGAN 模型训练并生成合成数据。
3. 使用 TableEvaluator 对真实数据和合成数据进行可视化评估。
4. 保存生成的数据集到本地 CSV 文件。

---

## 安装依赖
建议使用 Conda 创建虚拟环境：
```bash
conda create -n ctgan-env python=3.10
conda activate ctgan-env
pip install -r requirements.txt
```

## 模型说明

本项目使用 CTGAN（Conditional Tabular GAN）来生成结构化表格数据，适用于包含混合类型（连续型和类别型）的数据集。

### 主要步骤：

1. **数据清洗**：保留所需列，抽取 10000 条样本，删除缺失值。

2. **CTGAN 训练**：指定类别型特征和连续型特征，训练生成模型。

3. **生成合成数据**：使用 `ctgan.sample()` 生成 10000 条新数据。

4. **数据评估**：用 TableEvaluator 生成分布对比、相关性矩阵等可视化评估图表。

5. **保存数据**：保存为 `data_synthetic.csv` 供后续使用。

---

## 数据评估

本项目使用 TableEvaluator 来比较真实数据和合成数据在：

- 单变量分布  
- 多变量关系  
- 缺失值模式  
- 相关性矩阵  

这些图表能帮助判断生成数据的质量。
```

