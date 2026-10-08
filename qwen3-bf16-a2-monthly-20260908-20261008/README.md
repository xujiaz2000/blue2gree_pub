# 最近一个月 Qwen3-30B-A3B BF16 A2 输出吞吐

![折线图](throughput-trend.png)

统计区间：北京时间2026-09-08 00:00至2026-10-08采集时。只统计Nightly-A2 (scheduled) workflow、main分支、qwen3-30b-a3b-bf16-a2-performance；包含定时与手动触发，以及各次job重跑。

只统计有输出吞吐的53个job结果；无吞吐结果的job不计入统计数量、均值或图表。

均值 761.0501、中位数 772.8905、最低 177.5466、最高 806.9539 token/s。

指标按日志Common Metric中的`Output Token Throughput │ total`读取；有多个结果表时取最后一张。不是单请求`OutputTokenThroughput`均值，也不是vLLM服务日志的瞬时速率。job失败但有性能表时仍计入。

不同日期的代码、CANN、vLLM、runner及配置可能变化。此图是CI观测趋势，不是仅改变CANN版本的受控实验。

示例job核验：[107397194489](https://github.com/vllm-project/vllm-ascend/actions/runs/35913876951/job/107397194489) = **780.0526 token/s**。

交互图：[throughput-trend.html](throughput-trend.html)，可悬停查看commit，点击跳转job。CSV：[valid-throughput.csv](valid-throughput.csv)、[完整目标job记录](measurements.csv)。

## 去除最低异常点的版本

![去除最低异常点](throughput-trend-without-min.png)

仅去掉 job 111247072388 的 177.5466 token/s，保留52条有吞吐的结果。纵轴为700–830 token/s。原图及原始数据保留。

## 有效结果明细

| 北京时间 | 吞吐 token/s | job状态 | commit | run / attempt | job |
| --- | ---: | --- | --- | --- | --- |
| 2026-09-08 20:18:57 | 800.5221 | success | `8ac532e62` | 34224770167 / 1 | [102057924729](https://github.com/vllm-project/vllm-ascend/actions/runs/34224770167/job/102057924729) |
| 2026-09-09 10:33:47 | 787.0243 | success | `f8481287a` | 34303330149 / 1 | [102315760542](https://github.com/vllm-project/vllm-ascend/actions/runs/34303330149/job/102315760542) |
| 2026-09-09 10:35:41 | 791.6659 | success | `f8481287a` | 34303456698 / 1 | [102316151689](https://github.com/vllm-project/vllm-ascend/actions/runs/34303456698/job/102316151689) |
| 2026-09-11 01:52:10 | 794.4989 | success | `c5055c808` | 34497670513 / 1 | [102981142073](https://github.com/vllm-project/vllm-ascend/actions/runs/34497670513/job/102981142073) |
| 2026-09-11 23:53:52 | 777.0744 | failure | `c843f75af` | 34617970118 / 1 | [103327196895](https://github.com/vllm-project/vllm-ascend/actions/runs/34617970118/job/103327196895) |
| 2026-09-13 02:00:53 | 790.0201 | success | `d4d2957e5` | 34703784818 / 1 | [103596224725](https://github.com/vllm-project/vllm-ascend/actions/runs/34703784818/job/103596224725) |
| 2026-09-14 01:48:19 | 798.6856 | success | `660c4582a` | 34766526376 / 1 | [103764868035](https://github.com/vllm-project/vllm-ascend/actions/runs/34766526376/job/103764868035) |
| 2026-09-15 02:20:31 | 788.8191 | success | `26f1363f7` | 34867800936 / 1 | [104097054774](https://github.com/vllm-project/vllm-ascend/actions/runs/34867800936/job/104097054774) |
| 2026-09-16 02:17:37 | 788.7569 | success | `b49962987` | 34990518481 / 1 | [104472775960](https://github.com/vllm-project/vllm-ascend/actions/runs/34990518481/job/104472775960) |
| 2026-09-17 04:22:56 | 791.0792 | success | `e1d149031` | 35140915567 / 1 | [104962193793](https://github.com/vllm-project/vllm-ascend/actions/runs/35140915567/job/104962193793) |
| 2026-09-18 03:25:51 | 757.0391 | failure | `c7ca0b676` | 35253853308 / 1 | [105348688564](https://github.com/vllm-project/vllm-ascend/actions/runs/35253853308/job/105348688564) |
| 2026-09-18 11:57:28 | 787.7876 | success | `21bfcb10d` | 35304824742 / 1 | [105475587767](https://github.com/vllm-project/vllm-ascend/actions/runs/35304824742/job/105475587767) |
| 2026-09-18 19:04:00 | 740.0460 | failure | `628fac6d8` | 35337261535 / 1 | [105576419718](https://github.com/vllm-project/vllm-ascend/actions/runs/35337261535/job/105576419718) |
| 2026-09-18 20:26:00 | 795.0060 | success | `8af9dff3a` | 35344050737 / 1 | [105598117731](https://github.com/vllm-project/vllm-ascend/actions/runs/35344050737/job/105598117731) |
| 2026-09-19 03:33:51 | 792.6629 | success | `c8addbb24` | 35376644941 / 1 | [105734114580](https://github.com/vllm-project/vllm-ascend/actions/runs/35376644941/job/105734114580) |
| 2026-09-20 13:18:58 | 792.9211 | success | `182a7e496` | 35485902740 / 1 | [106026667217](https://github.com/vllm-project/vllm-ascend/actions/runs/35485902740/job/106026667217) |
| 2026-09-21 06:16:40 | 783.8601 | success | `c173a64a4` | 35535887772 / 1 | [106158819830](https://github.com/vllm-project/vllm-ascend/actions/runs/35535887772/job/106158819830) |
| 2026-09-21 10:26:50 | 802.4496 | success | `72bde513b` | 35553865991 / 1 | [106194289882](https://github.com/vllm-project/vllm-ascend/actions/runs/35553865991/job/106194289882) |
| 2026-09-22 00:45:50 | 762.9025 | failure | `b1bb54388` | 35606823861 / 1 | [106406312839](https://github.com/vllm-project/vllm-ascend/actions/runs/35606823861/job/106406312839) |
| 2026-09-22 02:37:59 | 779.3559 | success | `baa023ada` | 35624826824 / 1 | [106451328450](https://github.com/vllm-project/vllm-ascend/actions/runs/35624826824/job/106451328450) |
| 2026-09-22 11:59:51 | 720.2423 | failure | `baa023ada` | 35676345606 / 1 | [106606622015](https://github.com/vllm-project/vllm-ascend/actions/runs/35676345606/job/106606622015) |
| 2026-09-22 19:27:44 | 806.9539 | success | `5c0470d90` | 35720949164 / 1 | [106725244296](https://github.com/vllm-project/vllm-ascend/actions/runs/35720949164/job/106725244296) |
| 2026-09-23 01:00:20 | 735.4414 | failure | `5591facb3` | 35745271509 / 2 | [106847569569](https://github.com/vllm-project/vllm-ascend/actions/runs/35745271509/job/106847569569) |
| 2026-09-23 04:00:09 | 787.6478 | success | `a71b766ce` | 35765724272 / 1 | [106913453935](https://github.com/vllm-project/vllm-ascend/actions/runs/35765724272/job/106913453935) |
| 2026-09-24 03:06:19 | 788.5001 | success | `ad7a731b9` | 35894457906 / 1 | [107336621797](https://github.com/vllm-project/vllm-ascend/actions/runs/35894457906/job/107336621797) |
| 2026-09-24 05:51:55 | 780.0526 | success | `39fef3f8f` | 35913876951 / 1 | [107397194489](https://github.com/vllm-project/vllm-ascend/actions/runs/35913876951/job/107397194489) |
| 2026-09-26 02:35:36 | 760.5344 | failure | `2bb3f4471` | 36156268364 / 1 | [108201226829](https://github.com/vllm-project/vllm-ascend/actions/runs/36156268364/job/108201226829) |
| 2026-09-26 16:41:50 | 783.3198 | success | `eb31db4d7` | 36225208422 / 1 | [108372470704](https://github.com/vllm-project/vllm-ascend/actions/runs/36225208422/job/108372470704) |
| 2026-09-27 17:07:44 | 772.8905 | failure | `7e2c563f5` | 36302697268 / 1 | [108589310012](https://github.com/vllm-project/vllm-ascend/actions/runs/36302697268/job/108589310012) |
| 2026-09-28 00:45:44 | 769.6652 | failure | `8d4409d62` | 36327816101 / 1 | [108662359567](https://github.com/vllm-project/vllm-ascend/actions/runs/36327816101/job/108662359567) |
| 2026-09-28 02:56:59 | 747.2843 | failure | `8d4409d62` | 36340637637 / 1 | [108685222352](https://github.com/vllm-project/vllm-ascend/actions/runs/36340637637/job/108685222352) |
| 2026-09-28 03:54:47 | 753.1549 | failure | `8d4409d62` | 36345784830 / 1 | [108695295033](https://github.com/vllm-project/vllm-ascend/actions/runs/36345784830/job/108695295033) |
| 2026-09-28 05:00:54 | 754.5311 | failure | `8d4409d62` | 36349847575 / 1 | [108706991528](https://github.com/vllm-project/vllm-ascend/actions/runs/36349847575/job/108706991528) |
| 2026-09-28 06:13:24 | 763.6923 | failure | `8d4409d62` | 36354234703 / 1 | [108719413430](https://github.com/vllm-project/vllm-ascend/actions/runs/36354234703/job/108719413430) |
| 2026-09-28 06:19:34 | 779.2251 | success | `8d4409d62` | 36354586505 / 1 | [108720487234](https://github.com/vllm-project/vllm-ascend/actions/runs/36354586505/job/108720487234) |
| 2026-09-29 02:57:05 | 774.3915 | failure | `b64b4d714` | 36456246861 / 1 | [109085395373](https://github.com/vllm-project/vllm-ascend/actions/runs/36456246861/job/109085395373) |
| 2026-09-29 07:27:51 | 748.3362 | failure | `b64b4d714` | 36497700079 / 1 | [109182296591](https://github.com/vllm-project/vllm-ascend/actions/runs/36497700079/job/109182296591) |
| 2026-09-29 11:02:10 | 783.2062 | success | `b185282b4` | 36514841209 / 1 | [109236147230](https://github.com/vllm-project/vllm-ascend/actions/runs/36514841209/job/109236147230) |
| 2026-09-30 02:38:59 | 739.2790 | failure | `c39b31aab` | 36592566744 / 2 | [109548396956](https://github.com/vllm-project/vllm-ascend/actions/runs/36592566744/job/109548396956) |
| 2026-10-01 01:49:05 | 750.8766 | failure | `62e05feb3` | 36740620800 / 1 | [110019706294](https://github.com/vllm-project/vllm-ascend/actions/runs/36740620800/job/110019706294) |
| 2026-10-01 11:10:07 | 759.2211 | failure | `a8fcedb03` | 36808663716 / 1 | [110200286424](https://github.com/vllm-project/vllm-ascend/actions/runs/36808663716/job/110200286424) |
| 2026-10-02 01:32:01 | 752.3831 | failure | `02615df12` | 36886694823 / 1 | [110496384378](https://github.com/vllm-project/vllm-ascend/actions/runs/36886694823/job/110496384378) |
| 2026-10-03 01:35:07 | 737.0680 | failure | `4ebb3090f` | 37029162302 / 1 | [110952969576](https://github.com/vllm-project/vllm-ascend/actions/runs/37029162302/job/110952969576) |
| 2026-10-04 00:50:19 | 177.5466 | failure | `4ebb3090f` | 37129575273 / 1 | [111247072388](https://github.com/vllm-project/vllm-ascend/actions/runs/37129575273/job/111247072388) |
| 2026-10-04 15:06:51 | 764.2628 | failure | `f6992d8c4` | 37179121001 / 1 | [111383999096](https://github.com/vllm-project/vllm-ascend/actions/runs/37179121001/job/111383999096) |
| 2026-10-05 00:37:50 | 762.2176 | failure | `7df960487` | 37214166426 / 1 | [111480582426](https://github.com/vllm-project/vllm-ascend/actions/runs/37214166426/job/111480582426) |
| 2026-10-05 13:16:02 | 764.2751 | failure | `7df960487` | 37214166426 / 2 | [111625406144](https://github.com/vllm-project/vllm-ascend/actions/runs/37214166426/job/111625406144) |
| 2026-10-06 12:48:58 | 763.8790 | failure | `4e19cc765` | 37335331287 / 3 | [112112680131](https://github.com/vllm-project/vllm-ascend/actions/runs/37335331287/job/112112680131) |
| 2026-10-07 01:31:15 | 762.0028 | failure | `437c06e1c` | 37490119275 / 1 | [112407946056](https://github.com/vllm-project/vllm-ascend/actions/runs/37490119275/job/112407946056) |
| 2026-10-07 10:16:15 | 760.1381 | failure | `ec570818b` | 37560774961 / 1 | [112598434147](https://github.com/vllm-project/vllm-ascend/actions/runs/37560774961/job/112598434147) |
| 2026-10-08 01:42:48 | 762.8288 | failure | `0e181fc85` | 37646474685 / 2 | [112928617929](https://github.com/vllm-project/vllm-ascend/actions/runs/37646474685/job/112928617929) |
| 2026-10-08 15:09:16 | 765.6941 | failure | `ac850b5ef` | 37717487442 / 1 | [113182291062](https://github.com/vllm-project/vllm-ascend/actions/runs/37717487442/job/113182291062) |
| 2026-10-08 17:56:48 | 802.7341 | success | `cb9d5563a` | 37756272166 / 1 | [113252531808](https://github.com/vllm-project/vllm-ascend/actions/runs/37756272166/job/113252531808) |
