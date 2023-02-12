# 基础信息
这里的资料是我学习[bilibili 捻叶成剑](https://space.bilibili.com/416296286/video) UP主的笔记

# [[小白也能看懂]信号质量评估RSRP和sinr，含大尺度衰落和小尺度衰落，路径损耗，多径效应等](https://www.bilibili.com/video/BV1ca4y1v78n/)

## Sinr
信号与干扰加噪声比
Sinr = Signal / (Interference + Noise) 约等于 服务小区RSRP/(邻接小区RSRP和+噪声). 大部分情况也不考虑噪声 所以Sinr = Signal / 邻区小区RSRP和
一般在-10~30之间 一般认为30~20是干扰小, 0~20干扰一般. `<0`认为干扰很大

# MIMO
实现分类:
    * 空间分集: 加强信号
    * 空间复用: 多路传输
    * 波束赋形

# 传输模式
* TM3: 开环空间复用, UE不反馈PMI, UE高速移动
* TM4: 闭环空间复用, UE反馈PMI, UE低速移动
* Rank: 信道相关性
如果RANK=1, 代表手机无法区分两路信道, 只能发挥空间分集的效果.  
RANK=2, 才能发挥空间复用效果
* 码字: 代表一路独立的数据流. 被层映射后变成层1, 层2, 层3, 层4. 经过预编码后会映射道不同的天线端口
* 天线端口:
逻辑通道, 可以分为1, 2, 4. 一个天线端口可能对应4根天线(4个物理端口). 每根天线都发一样的数据或者不同的数据
* TM3, TM4, TM8可以实现发双流
* Rank2代表手机能够区分两路信道
* Rank2 + TM3, TM4, TM8 == 双流

# NOMA
免调度, 直接传数据. 
* PDM-NOMA: 功率域复用 功率区分用户
* CDM-NOMA: 码域复用 码区分用户
* 中兴MUSA Multi-User Shared Access: 多用户共享接入
用复数三元短序列扩频码, SIC串行干扰删除.
发送数据时, N个每个用户都在同样的4个RE上发送数据.
然后基站依次解析码最大的用户并去除这个用户的数据. 
    * 复数 z=a+bj, b是频率变化幅度.z的长度是幅度变化程度
    * 三元: {-1, 0, 1}
    * 短序列: 一般选择4个三元复数. 所以一共有最多 (3*3*3)**4 = 6561个用户码

# [5G参数CQI与MCS/TBS](https://www.bilibili.com/video/BV1684y1B7pU/)
CQI属于CSI
* CSI: Channel Status Information 信道状态信息
    * CQI: Channel Quality Information 越大代表下行信号质量越好
    0 代表手机完全收不到基站的信号
    * 其他 PMI, CRI, SSBRI, LI, RI
