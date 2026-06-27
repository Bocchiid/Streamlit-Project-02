# 2024年电商平台在线销售可视化分析系统

## 运行方式

进入 `streamlit_app` 文件夹后创建虚拟环境并激活虚拟环境，然后安装依赖：

```powershell
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

然后运行：

```powershell
streamlit run app.py
```

启动后访问：

```text
http://127.0.0.1:8501
```

## 数据文件

系统读取的主数据文件为：

```text
data/online_sales_data.csv
```

该文件来自 Kaggle 数据集 `Online Sales Dataset - Popular Marketplace Data`，当前样本覆盖 2024-01-01 至 2024-08-27，包含交易日期、商品类别、商品名称、销售数量、商品单价、销售额、地区和支付方式等字段。

## 页面模块

- 总览看板：展示交易量、销量、销售额、平均单笔销售额、销售结构和品类贡献瀑布图。
- 时间趋势：展示月度销售走势、星期分布、日度销售额变化和月度品类结构面积图。
- 品类偏好：展示商品类别销售贡献、品类销量与销售额关系、品类地区热力图、商品树图以及商品销售排行。
- 价格带分析：展示不同价格带的销售额、销量、收入占比和地区价格带销售热力图。
- 地区与支付方式：展示地区销售额、支付方式占比、地区支付方式旭日图及二者的交叉分布。
- AI洞察：基于当前筛选后的聚合数据，调用 `.env` 中配置的 AI Key 生成经营洞察、风险提醒和行动建议。
- 数据管理：展示数据集摘要、字段说明和筛选后的交易明细预览。

## AI 配置

复制 `.env.example` 为 `.env`，然后在 `.env` 中配置：

```text
DEEPSEEK_API_KEY=你的API_KEY
```

可选配置：

```text
DEEPSEEK_API_BASE=https://api.deepseek.com/chat/completions
DEEPSEEK_MODEL=deepseek-v4-flash
```
