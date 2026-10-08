# 最近一个月 Qwen3-30B-A3B W8A8 A2 输出吞吐

![折线图](throughput-trend.png)

统计区间：北京时间2026-09-08 00:00至2026-10-08采集时。统计Nightly-A2 (scheduled) workflow运行于main分支的qwen3-30b-a3b-w8a8-a2-performance；包含定时与手动触发，以及各次job重跑。

只统计日志中有吞吐的 47 条job结果，无吞吐结果的job不统计。

均值 769.5908、中位数 787.1650、最低 154.9978、最高 822.4807 token/s。

指标按日志Common Metric中的`Output Token Throughput │ total`读取；有多个结果表时取最后一张。不是单请求`OutputTokenThroughput`均值，也不是vLLM服务日志的瞬时速率。job失败但有性能表时仍计入。

包含main常规测试及PR评论触发的测试；workflow运行于main不代表测试代码来自main。CSV的tested_head_sha为日志核验的实际测试代码，head_sha为workflow控制节点。不同日期的代码、CANN、vLLM、runner及配置可能变化。此图是CI观测趋势，不是仅改变CANN版本的受控实验。

示例job核验：[109085395854](https://github.com/vllm-project/vllm-ascend/actions/runs/36456246861/job/109085395854) = **789.1202 token/s**。

交互图：[throughput-trend.html](throughput-trend.html)，可悬停查看commit，点击跳转job。CSV：[valid-throughput.csv](valid-throughput.csv)、[完整目标job记录](measurements.csv)。

## 去掉最低异常点的版本

![去掉最低异常点](throughput-trend-without-min.png)

仅排除 job 111247072312 的 154.9978 token/s，保留46条有效结果。均值782.9515、中位数787.1919 token/s；纵轴700–830 token/s。完整图和原始有效结果仍保留。

## 有效结果明细

| 北京时间 | 吞吐 token/s | job状态 | commit | run / attempt | job |
| --- | ---: | --- | --- | --- | --- |
| 2026-09-08 20:18:58 | 803.4938 | success | `17a2b63e3` | 34224770167 / 1 | [102057924869](https://github.com/vllm-project/vllm-ascend/actions/runs/34224770167/job/102057924869) |
| 2026-09-09 10:33:48 | 800.7120 | success | `7f2dfddf5` | 34303330149 / 1 | [102315760633](https://github.com/vllm-project/vllm-ascend/actions/runs/34303330149/job/102315760633) |
| 2026-09-09 10:35:34 | 796.4301 | success | `7f2dfddf5` | 34303456698 / 1 | [102316151466](https://github.com/vllm-project/vllm-ascend/actions/runs/34303456698/job/102316151466) |
| 2026-09-11 01:48:59 | 793.2474 | success | `7e0ad39fd` | 34497670513 / 1 | [102981142060](https://github.com/vllm-project/vllm-ascend/actions/runs/34497670513/job/102981142060) |
| 2026-09-11 23:54:59 | 789.0287 | success | `c843f75af` | 34617970118 / 1 | [103327196848](https://github.com/vllm-project/vllm-ascend/actions/runs/34617970118/job/103327196848) |
| 2026-09-13 01:59:38 | 793.5549 | success | `d4d2957e5` | 34703784818 / 1 | [103596224682](https://github.com/vllm-project/vllm-ascend/actions/runs/34703784818/job/103596224682) |
| 2026-09-14 01:47:35 | 799.7720 | success | `660c4582a` | 34766526376 / 1 | [103764867970](https://github.com/vllm-project/vllm-ascend/actions/runs/34766526376/job/103764867970) |
| 2026-09-15 02:20:50 | 798.7114 | success | `b88c38c93` | 34867800936 / 1 | [104097055078](https://github.com/vllm-project/vllm-ascend/actions/runs/34867800936/job/104097055078) |
| 2026-09-16 02:44:54 | 795.3345 | success | `714dd1d1b` | 34990518481 / 1 | [104472775829](https://github.com/vllm-project/vllm-ascend/actions/runs/34990518481/job/104472775829) |
| 2026-09-17 04:22:47 | 793.8553 | success | `bdab8bde8` | 35140915567 / 1 | [104962193940](https://github.com/vllm-project/vllm-ascend/actions/runs/35140915567/job/104962193940) |
| 2026-09-18 03:24:35 | 811.7645 | success | `c7ca0b676` | 35253853308 / 1 | [105348688354](https://github.com/vllm-project/vllm-ascend/actions/runs/35253853308/job/105348688354) |
| 2026-09-19 03:33:20 | 793.7787 | success | `c8addbb24` | 35376644941 / 1 | [105734114354](https://github.com/vllm-project/vllm-ascend/actions/runs/35376644941/job/105734114354) |
| 2026-09-20 13:19:20 | 792.5433 | success | `15d85da2c` | 35485902740 / 1 | [106026667233](https://github.com/vllm-project/vllm-ascend/actions/runs/35485902740/job/106026667233) |
| 2026-09-21 06:17:50 | 776.6258 | failure | `c173a64a4` | 35535887772 / 1 | [106158819969](https://github.com/vllm-project/vllm-ascend/actions/runs/35535887772/job/106158819969) |
| 2026-09-21 07:53:31 | 782.4173 | success | `5eccffd00` | 35545736131 / 1 | [106171730326](https://github.com/vllm-project/vllm-ascend/actions/runs/35545736131/job/106171730326) |
| 2026-09-21 08:44:39 | 778.4115 | failure | `5eccffd00` | 35548406902 / 1 | [106179106439](https://github.com/vllm-project/vllm-ascend/actions/runs/35548406902/job/106179106439) |
| 2026-09-21 09:32:47 | 784.8658 | success | `5eccffd00` | 35550977698 / 1 | [106186198193](https://github.com/vllm-project/vllm-ascend/actions/runs/35550977698/job/106186198193) |
| 2026-09-21 12:28:19 | 782.7378 | success | `b2c362207` | 35560768263 / 1 | [106213901721](https://github.com/vllm-project/vllm-ascend/actions/runs/35560768263/job/106213901721) |
| 2026-09-21 15:37:22 | 788.2960 | success | `b2c362207` | 35573454894 / 1 | [106250988864](https://github.com/vllm-project/vllm-ascend/actions/runs/35573454894/job/106250988864) |
| 2026-09-21 16:59:28 | 803.3617 | success | `1e1dbd604` | 35580295526 / 1 | [106272761704](https://github.com/vllm-project/vllm-ascend/actions/runs/35580295526/job/106272761704) |
| 2026-09-21 17:04:07 | 792.0472 | success | `914bba50b` | 35580733048 / 1 | [106274159404](https://github.com/vllm-project/vllm-ascend/actions/runs/35580733048/job/106274159404) |
| 2026-09-21 18:40:53 | 792.4597 | success | `00289eaf1` | 35584252254 / 1 | [106301990974](https://github.com/vllm-project/vllm-ascend/actions/runs/35584252254/job/106301990974) |
| 2026-09-22 00:47:15 | 806.0405 | success | `731afcbb2` | 35606823861 / 1 | [106406312638](https://github.com/vllm-project/vllm-ascend/actions/runs/35606823861/job/106406312638) |
| 2026-09-22 02:30:34 | 783.7664 | success | `baa023ada` | 35624826824 / 1 | [106451328520](https://github.com/vllm-project/vllm-ascend/actions/runs/35624826824/job/106451328520) |
| 2026-09-22 11:54:32 | 822.4807 | success | `0afb90113` | 35676345606 / 1 | [106606621833](https://github.com/vllm-project/vllm-ascend/actions/runs/35676345606/job/106606621833) |
| 2026-09-23 01:00:40 | 733.4899 | failure | `baa023ada` | 35745271509 / 2 | [106847569750](https://github.com/vllm-project/vllm-ascend/actions/runs/35745271509/job/106847569750) |
| 2026-09-23 04:00:19 | 792.6278 | success | `a71b766ce` | 35765724272 / 1 | [106913454027](https://github.com/vllm-project/vllm-ascend/actions/runs/35765724272/job/106913454027) |
| 2026-09-24 03:05:02 | 790.0360 | success | `ad7a731b9` | 35894457906 / 1 | [107336621285](https://github.com/vllm-project/vllm-ascend/actions/runs/35894457906/job/107336621285) |
| 2026-09-24 05:50:26 | 787.1650 | success | `39fef3f8f` | 35913876951 / 1 | [107397194238](https://github.com/vllm-project/vllm-ascend/actions/runs/35913876951/job/107397194238) |
| 2026-09-26 02:37:15 | 770.9961 | failure | `baa023ada` | 36156268364 / 1 | [108201226790](https://github.com/vllm-project/vllm-ascend/actions/runs/36156268364/job/108201226790) |
| 2026-09-26 16:40:07 | 784.1192 | success | `bbb5672af` | 36225208422 / 1 | [108372470597](https://github.com/vllm-project/vllm-ascend/actions/runs/36225208422/job/108372470597) |
| 2026-09-27 17:09:43 | 785.8546 | success | `7e2c563f5` | 36302697268 / 1 | [108589310238](https://github.com/vllm-project/vllm-ascend/actions/runs/36302697268/job/108589310238) |
| 2026-09-28 00:47:39 | 785.4120 | success | `8d4409d62` | 36327816101 / 1 | [108662359368](https://github.com/vllm-project/vllm-ascend/actions/runs/36327816101/job/108662359368) |
| 2026-09-29 02:57:33 | 789.1202 | success | `b64b4d714` | 36456246861 / 1 | [109085395854](https://github.com/vllm-project/vllm-ascend/actions/runs/36456246861/job/109085395854) |
| 2026-09-30 02:39:41 | 755.6040 | failure | `b64b4d714` | 36592566744 / 2 | [109548396973](https://github.com/vllm-project/vllm-ascend/actions/runs/36592566744/job/109548396973) |
| 2026-10-01 01:54:41 | 757.2568 | failure | `a40b52df0` | 36740620800 / 1 | [110019706766](https://github.com/vllm-project/vllm-ascend/actions/runs/36740620800/job/110019706766) |
| 2026-10-02 01:31:57 | 770.0295 | failure | `a8fcedb03` | 36886694823 / 1 | [110496384097](https://github.com/vllm-project/vllm-ascend/actions/runs/36886694823/job/110496384097) |
| 2026-10-03 01:35:39 | 722.1660 | failure | `02615df12` | 37029162302 / 1 | [110952969797](https://github.com/vllm-project/vllm-ascend/actions/runs/37029162302/job/110952969797) |
| 2026-10-04 00:49:51 | 154.9978 | failure | `fb813d848` | 37129575273 / 1 | [111247072312](https://github.com/vllm-project/vllm-ascend/actions/runs/37129575273/job/111247072312) |
| 2026-10-04 15:07:01 | 762.1402 | failure | `4ebb3090f` | 37179121001 / 1 | [111383999192](https://github.com/vllm-project/vllm-ascend/actions/runs/37179121001/job/111383999192) |
| 2026-10-05 00:38:22 | 765.4462 | failure | `9b8fc5d72` | 37214166426 / 1 | [111480582321](https://github.com/vllm-project/vllm-ascend/actions/runs/37214166426/job/111480582321) |
| 2026-10-05 13:14:32 | 760.5895 | failure | `9b8fc5d72` | 37214166426 / 2 | [111625406120](https://github.com/vllm-project/vllm-ascend/actions/runs/37214166426/job/111625406120) |
| 2026-10-06 12:48:30 | 773.3767 | failure | `7c67bcce3` | 37335331287 / 3 | [112112680085](https://github.com/vllm-project/vllm-ascend/actions/runs/37335331287/job/112112680085) |
| 2026-10-07 01:53:38 | 764.0632 | failure | `acdd1baf9` | 37490119275 / 1 | [112407946995](https://github.com/vllm-project/vllm-ascend/actions/runs/37490119275/job/112407946995) |
| 2026-10-07 10:16:12 | 756.4232 | failure | `971743a46` | 37560774961 / 1 | [112598434056](https://github.com/vllm-project/vllm-ascend/actions/runs/37560774961/job/112598434056) |
| 2026-10-08 01:42:56 | 766.8981 | failure | `fe85f2bc4` | 37646474685 / 2 | [112928617938](https://github.com/vllm-project/vllm-ascend/actions/runs/37646474685/job/112928617938) |
| 2026-10-08 14:35:01 | 787.2188 | success | `09185ed8a` | 37717487442 / 1 | [113182290813](https://github.com/vllm-project/vllm-ascend/actions/runs/37717487442/job/113182290813) |
