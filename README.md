# Whale-Pkg

## Intro

Whale's playground 随便写写

## Package

### Covid-19 Report & Visualization



#### Installation


~~pip install my-covid-report==1.2~~

```diff
- 由于会出现负增长情况（累计确诊数、死亡数降低，或者说新增确诊数、死亡数为负数！）
- 在画图时无法做面积图，加以修正！
+ 在data_processing中增加clip参数
```

```diff
- 自2022年4月8日起，由于未知原因，上海新增确诊数据未更新，所以通过爬取上海卫健委数据，进行补充。
```

```
pip install my-covid-report==1.4
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
    - GET_csse_covid_19_time_series()    # 获取时序数据
    - GET_csse_covid_19_daily_reports()  # 获取横截面数据（最新和之前一天）
    - GET_shanghai_data()                # 获取并处理【上海】数据（数据来自上海卫健委）
```

```diff
- data_processing
    - ts_process_CHINA(ts_data,clip = False)                   # 中国时序数据处理
    - ts_process_US(ts_data, death = False,clip = False)       # 美国时序数据处理（他们的字段有区别）
    - daily_process(daily_data, country = 'China')             # 横截面数据处理
```

```diff
- covid_visualization
    - Decompose_CHINA(ts_data_processed,    # 时间序列数据（中国）
              latest_data_processed,  # 最新横截面数据（中国）
              prev_data_processed,    # 前一天横截面数据（中国）
              start=None,             # 统计开始日期
              end=None,               # 统计结束日期
              ma = [7,30],            # 移动平均线
              method = '新增',        # 新增 或者 累计
              specify = None,         # 具体的省，或者输入'All'获取全国信息，如不设置此参数，绘制各省/州的对比图
              verbose = 1,            # 可选0或者1，输出详情
              kind = '确诊')          # 确诊 / 死亡 / 恢复，这取决于ts_data_processed使用的是什么类型的数据    


    - Decompose_US(ts_data_processed,    # 时间序列数据（美国）
              latest_data_processed,  # 最新横截面数据（美国）
              prev_data_processed,    # 前一天横截面数据（美国）
              start=None,             # 统计开始日期
              end=None,               # 统计结束日期
              ma = [7,30],            # 移动平均线
              method = '新增',        # 新增 或者 累计
              specify = None,         # 具体的州，或者输入'All'获取全国信息，如不设置此参数，绘制各省/州的对比图
              verbose = 1,            # 可选0或者1，输出详情
              kind = '确诊')          # 确诊 / 死亡 / 恢复，这取决于ts_data_processed使用的是什么类型的数据  
```

#### Examples

代码片段：https://gist.github.com/datoujinggzj/377f08e96056ddec3333a74cba2467e2



