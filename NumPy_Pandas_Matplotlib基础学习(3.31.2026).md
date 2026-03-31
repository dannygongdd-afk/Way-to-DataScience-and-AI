# NumPy、Pandas 和 Matplotlib 基础学习

## 📅 学习日期
2026年3月31日

---

## 0️⃣ 虚拟环境的创建和激活

### 为什么需要虚拟环境？
不要直接用系统自带的 Python，也不要直接在"裸"环境里装库。在未来的每个项目中都应该建立一个虚拟环境，这样可以：
- 避免不同项目之间的依赖冲突
- 保持项目的独立性和可复现性

### 操作步骤（macOS + VSCode）

#### 1. 创建虚拟环境
```bash
python3 -m venv ai_venv  # ai_venv 是虚拟环境的名称，可自定义
```

#### 2. 激活虚拟环境
```bash
source ai_venv/bin/activate
```

> **Windows 用户**：使用 `ai_venv\Scripts\activate`

---

## 1️⃣ NumPy 基础

### 为什么学 NumPy？
🎯 **AI 的本质就是矩阵乘法**

NumPy 是 Python 中用于科学计算的基础库，提供高效的矩阵运算能力。相比 Python 原生 list，NumPy 数组的运算速度快**一万倍**！

### 核心学习任务

#### 任务 1：理解 ndarray 和 Python 原生 list 的区别
- **ndarray**：NumPy 的核心数据结构，支持矢量化操作
- **Python list**：通用列表，不适合数值计算

#### 任务 2：学会创建矩阵
常用创建方法：
- `np.array()` - 从列表创建数组
- `np.zeros()` - 创建全零数组
- `np.arange()` - 创建等差数列

### 📝 代码练习

```python
import numpy as np

# 创建矩阵
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])

# 矩阵乘法
c = np.dot(a, b)
print("矩阵乘法结果：")
print(c)
```

**输出结果：**
```
[[19 22]
 [43 50]]
```

---

## 2️⃣ Pandas 基础

### 为什么学 Pandas？
📊 **处理表格数据、CSV 文件全靠它**

Pandas 是数据处理和分析的强大工具，可以轻松处理表格数据。

### 核心学习任务

#### 任务 1：理解 DataFrame（就是一张表）
- DataFrame 是 Pandas 的核心数据结构
- 类似于 Excel 电子表格或 SQL 数据库表

#### 任务 2：学会读取和查看数据
- `pd.read_csv('file.csv')` - 读取 CSV 文件
- `.head()` - 查看前几行
- `.describe()` - 获取统计信息
- `.info()` - 查看数据信息（列名、类型、缺失值等）

### 📝 代码练习

```python
import pandas as pd

# 创建 DataFrame
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
})

# 查看数据
print("数据框内容：")
print(df)
print("\n前两行：")
print(df.head(2))
print("\n统计信息：")
print(df.describe())
print("\n数据信息：")
print(df.info())
```

**输出结果：**
```
      Name  Age           City
0    Alice   25       New York
1      Bob   30  Los Angeles
2  Charlie   35       Chicago
```

---

## 3️⃣ Matplotlib 基础

### 为什么学 Matplotlib？
📈 **数据看不懂？画出来就看懂了**

Matplotlib 是 Python 中最流行的数据可视化库，可以生成各种图表。

### 核心学习任务

#### 任务 1：安装库
```bash
pip install matplotlib
```

#### 任务 2：学会基本绘图
- `plt.plot()` - 绘制折线图
- `plt.scatter()` - 绘制散点图

### 📝 代码练习

```python
import matplotlib.pyplot as plt
import numpy as np

# 生成数据
x = np.linspace(0, 10, 100)
y = np.sin(x)

# 绘制折线图
plt.plot(x, y, label='sin(x)', color='blue', linewidth=2)
plt.xlabel('x')
plt.ylabel('y')
plt.title('正弦函数曲线')
plt.legend()
plt.grid(True)
plt.show()
```

#### 进阶：散点图
```python
# 散点图示例
x = np.random.rand(50)
y = np.random.rand(50)

plt.scatter(x, y, alpha=0.6, s=100, color='red')
plt.xlabel('X 轴')
plt.ylabel('Y 轴')
plt.title('随机散点图')
plt.show()
```

---

## 🎓 学习总结

| 库 | 主要用途 | 核心概念 |
|---|--------|--------|
| **NumPy** | 数值计算和矩阵操作 | ndarray、矩阵运算 |
| **Pandas** | 数据处理和分析 | DataFrame、数据读取和清洗 |
| **Matplotlib** | 数据可视化 | 折线图、散点图等 |

---

## ��� 下一步学习方向
- [ ] 深入学习 NumPy 的广播机制和索引
- [ ] Pandas 数据清洗和透视表
- [ ] Matplotlib 多子图和高级可视化
- [ ] 将三个库结合做实际项目

---

**学习进度记录：** 虚拟环境 ✅ | NumPy ✅ | Pandas ✅ | Matplotlib ✅