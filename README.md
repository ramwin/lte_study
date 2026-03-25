# lte_study


# 5G/NR

## 空口协议
### SSB
每20ms发送一次

* PSS Primary Synchronization Signal，主同步信号
第一个符号发送, 占用127个子载波/10.6个RB, 占用1个符号. 一共发送127比特. 这127比特只有3种状态,根据小区的ID(PCI)对3取模.   
5G一共1008个PCI

```
N_cell_ID = 3 x N(1)_ID + N(2)_ID
N(1)_ID {0,1,..,335}, N(2)_ID {0, 1, 2}
```
