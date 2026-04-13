# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

Kaggle 学习与竞赛练习仓库。每个练习以日期前缀命名（如 `4.13_` 表示 4 月 13 日），内含 Jupyter Notebook 和 `input/` 数据目录。

## 环境设置

```bash
source .venv/bin/activate   # Python 3.13 虚拟环境
```

核心依赖：pandas, scikit-learn, numpy, matplotlib, kagglehub（无需额外安装，已在 venv 中）。

## 运行 Notebook

```bash
jupyter notebook                            # 启动 Jupyter
# 或逐 cell 执行单个 notebook
jupyter nbconvert --to notebook --execute <notebook.ipynb>
```

## 仓库结构

```
4.13_Titanic/           # 泰坦尼克号生存预测
  ├── Start.ipynb       # 基线：性别特征 + RandomForestClassifier
  ├── V2.ipynb          # 改进：增加 Age/Fare/Embarked，填充缺失值
  └── input/titanic/    # train.csv, test.csv, gender_submission.csv

4.13_HousingPrices/     # 房价预测
  ├── Pratice.ipynb     # Melbourne 数据：DecisionTree → RandomForest 回归
  ├── main.ipynb        # Kaggle ML Course 数据（开发中）
  └── input/            # melb_data.csv, home-data-for-ml-course/
```

## 约定

- 当用户确定结束今天的学习后，把知识点和笔记加入 `Note.md`文件
- 项目目录格式：`<日期>_竞赛名/`（日期为 M.DD 格式）
- 原始数据放在各项目的 `input/` 目录下，不修改
- 提交文件 (`submission*.csv`) 已被 .gitignore 排除
- Notebook 使用相对路径 `"./input/..."` 读取数据，从项目目录内运行
- 模型以 scikit-learn 为主，常用 `RandomForestClassifier`（分类）和 `RandomForestRegressor` / `DecisionTreeRegressor`（回归）
