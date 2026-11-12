# Optical features dataset

Dataset accompanying Applied Sciences manuscript **applsci-4712280**.

## File

`all.csv` contains 37,265 data rows and 25 columns. The original CSV, including its Chinese column names and numeric values, is preserved without modification. This repository contains extracted optical features, not the source images or videos.

## Dataset partitions

| Partition (`数据集`) | Rows |
| --- | ---: |
| train | 26,096 |
| val | 5,586 |
| test | 5,583 |

Use the existing partition column when separating training, validation, and test data.

## Columns

| Column(s) | Description |
| --- | --- |
| 数据集 | Dataset partition: train, val, or test |
| 图片号 | Source image identifier; read as text to preserve leading zeros |
| 标签 | Integer class label, with values 0 through 7 |
| 火焰面积占比 | Flame area ratio |
| 火焰质心相对位置 | Relative flame centroid position |
| 10%区域亮度最大值 through 100%区域亮度最大值 | Ten regional maximum brightness features |
| 10%区域亮度均值 through 100%区域亮度均值 | Ten regional mean brightness features |

Refer to the accompanying manuscript for the experimental methods, class definitions, and feature extraction procedure.

## Class distribution

| Label | Rows |
| --- | ---: |
| 0 | 13,377 |
| 1 | 1,488 |
| 2 | 2,620 |
| 3 | 1,850 |
| 4 | 14,280 |
| 5 | 2,200 |
| 6 | 830 |
| 7 | 620 |

## Reading the data

Open the CSV in a spreadsheet application using UTF-8 encoding. In Python with pandas:

```python
import pandas as pd

df = pd.read_csv("all.csv", encoding="utf-8-sig", dtype={"图片号": str})
train = df[df["数据集"] == "train"]
validation = df[df["数据集"] == "val"]
test = df[df["数据集"] == "test"]
```

## File integrity

SHA-256 of `all.csv`:

```text
8b89952b8aa1d710d0bc3fc038a39687e0f1ed74479512d24d5f1331e8700946
```
