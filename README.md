# Whale-Pkg

## Intro

Whale's playground 随便写写

## Package

### Covid-19 Report & Visualization



#### Installation

```
pip install my-covid-report==1.0
```

#### Instruction

随着奥密克戎的爆发，中国上海沦陷。

此pkg根据JHU CSSE所提供的官方新冠数据对疫情情况生成数据报告并可视化。

```diff
+ ⚠️需要翻墙⚠️
```

#### Modules

- getdata
- data_processing
- covid_visualization

#### Functions

```diff
- getdata
    - GET_csse_covid_19_time_series()
    - GET_csse_covid_19_daily_reports()
```

```diff
- data_processing
    - ts_process_CHINA(ts_data)
    - ts_process_US(ts_data, death = False)
    - daily_process(daily_data, country = 'China')
```

```diff
- covid_visualization
    - Decompose(ts_data_processed,    # 时间序列数据（中国 / 美国）
              latest_data_processed,  # 最新横截面数据（中国 / 美国）
              prev_data_processed,    # 前一天横截面数据（中国 / 美国）
              start=None,             # 统计开始日期
              end=None,               # 统计结束日期
              ma = [7,30],            # 移动平均线
              method = '新增',        # 新增 或者 累计
              specify = None,         # 具体的省/州，或者输入'All'获取全国信息，如不设置此参数，绘制各省/州的对比图
              verbose = 1,            # 可选0或者1，输出详情
              kind = '确诊',           # 确诊 / 死亡 / 恢复，这取决于ts_data_processed使用的是什么类型的数据
              country = '中国')        # 中国 / 美国
```

#### Examples

代码片段：https://gist.github.com/datoujinggzj/377f08e96056ddec3333a74cba2467e2



