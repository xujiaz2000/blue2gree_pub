# 最近一个月 Qwen3-30B-A3B BF16 A2 输出吞吐

![折线图](throughput-trend.png)

统计区间：北京时间2026-09-08 00:00至2026-10-08采集时。只统计Nightly-A2 (scheduled) workflow、main分支、qwen3-30b-a3b-bf16-a2-performance；包含定时与手动触发，以及各次job重跑。

查询到 176 个workflow run，其中 158 个目标job attempt、53 个有有效吞吐结果；105 个没有吞吐结果，不计为0。

均值 761.0501、中位数 772.8905、最低 177.5466、最高 806.9539 token/s。

指标按日志Common Metric中的`Output Token Throughput │ total`读取；有多个结果表时取最后一张。不是单请求`OutputTokenThroughput`均值，也不是vLLM服务日志的瞬时速率。job失败但有性能表时仍计入。

不同日期的代码、CANN、vLLM、runner及配置可能变化。此图是CI观测趋势，不是仅改变CANN版本的受控实验。

示例job核验：[107397194489](https://github.com/vllm-project/vllm-ascend/actions/runs/35913876951/job/107397194489) = **780.0526 token/s**。

交互图：[throughput-trend.html](throughput-trend.html)，可悬停查看commit，点击跳转job。CSV：[valid-throughput.csv](valid-throughput.csv)、[完整目标job记录](measurements.csv)。

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

## 无吞吐结果的job

| 北京时间 | 状态 | run | job | 原因 |
| --- | --- | --- | --- | --- |
| 2026-09-10 18:55:15 | skipped | 34460423677 | [102842816049](https://github.com/vllm-project/vllm-ascend/actions/runs/34460423677/job/102842816049) | Skipped: benchmark was not run |
| 2026-09-10 22:30:40 | skipped | 34481161897 | [102912343547](https://github.com/vllm-project/vllm-ascend/actions/runs/34481161897/job/102912343547) | Skipped: benchmark was not run |
| 2026-09-11 08:13:18 | skipped | 34540786304 | [103097264208](https://github.com/vllm-project/vllm-ascend/actions/runs/34540786304/job/103097264208) | Skipped: benchmark was not run |
| 2026-09-11 11:15:13 | skipped | 34552886493 | [103133889505](https://github.com/vllm-project/vllm-ascend/actions/runs/34552886493/job/103133889505) | Skipped: benchmark was not run |
| 2026-09-11 13:00:44 | skipped | 34561322648 | [103153195780](https://github.com/vllm-project/vllm-ascend/actions/runs/34561322648/job/103153195780) | Skipped: benchmark was not run |
| 2026-09-11 16:53:35 | skipped | 34575037565 | [103205611189](https://github.com/vllm-project/vllm-ascend/actions/runs/34575037565/job/103205611189) | Skipped: benchmark was not run |
| 2026-09-12 14:24:13 | skipped | 34671546210 | [103511312477](https://github.com/vllm-project/vllm-ascend/actions/runs/34671546210/job/103511312477) | Skipped: benchmark was not run |
| 2026-09-12 14:45:18 | skipped | 34675865431 | [103513816295](https://github.com/vllm-project/vllm-ascend/actions/runs/34675865431/job/103513816295) | Skipped: benchmark was not run |
| 2026-09-12 16:16:20 | skipped | 34679630237 | [103524536102](https://github.com/vllm-project/vllm-ascend/actions/runs/34679630237/job/103524536102) | Skipped: benchmark was not run |
| 2026-09-12 20:54:15 | skipped | 34691727028 | [103556706888](https://github.com/vllm-project/vllm-ascend/actions/runs/34691727028/job/103556706888) | Skipped: benchmark was not run |
| 2026-09-14 16:08:35 | skipped | 34820669744 | [103902933735](https://github.com/vllm-project/vllm-ascend/actions/runs/34820669744/job/103902933735) | Skipped: benchmark was not run |
| 2026-09-15 17:40:48 | skipped | 34951358020 | [104330968143](https://github.com/vllm-project/vllm-ascend/actions/runs/34951358020/job/104330968143) | Skipped: benchmark was not run |
| 2026-09-15 17:43:11 | skipped | 34951626639 | [104331692546](https://github.com/vllm-project/vllm-ascend/actions/runs/34951626639/job/104331692546) | Skipped: benchmark was not run |
| 2026-09-15 18:21:47 | skipped | 34950304371 | [104343090958](https://github.com/vllm-project/vllm-ascend/actions/runs/34950304371/job/104343090958) | Skipped: benchmark was not run |
| 2026-09-15 18:54:32 | skipped | 34957981292 | [104352513244](https://github.com/vllm-project/vllm-ascend/actions/runs/34957981292/job/104352513244) | Skipped: benchmark was not run |
| 2026-09-15 19:36:05 | skipped | 34957715415 | [104364550478](https://github.com/vllm-project/vllm-ascend/actions/runs/34957715415/job/104364550478) | Skipped: benchmark was not run |
| 2026-09-15 19:38:39 | skipped | 34961862799 | [104365296712](https://github.com/vllm-project/vllm-ascend/actions/runs/34961862799/job/104365296712) | Skipped: benchmark was not run |
| 2026-09-15 20:58:09 | skipped | 34969253618 | [104390407865](https://github.com/vllm-project/vllm-ascend/actions/runs/34969253618/job/104390407865) | Skipped: benchmark was not run |
| 2026-09-15 21:03:05 | skipped | 34969824585 | [104392106660](https://github.com/vllm-project/vllm-ascend/actions/runs/34969824585/job/104392106660) | Skipped: benchmark was not run |
| 2026-09-16 12:25:14 | skipped | 35050830365 | [104664779748](https://github.com/vllm-project/vllm-ascend/actions/runs/35050830365/job/104664779748) | Skipped: benchmark was not run |
| 2026-09-16 14:54:11 | skipped | 35065313137 | [104695880246](https://github.com/vllm-project/vllm-ascend/actions/runs/35065313137/job/104695880246) | Skipped: benchmark was not run |
| 2026-09-16 17:35:19 | skipped | 35065198772 | [104742309173](https://github.com/vllm-project/vllm-ascend/actions/runs/35065198772/job/104742309173) | Skipped: benchmark was not run |
| 2026-09-17 11:31:54 | skipped | 35176652097 | [105065431604](https://github.com/vllm-project/vllm-ascend/actions/runs/35176652097/job/105065431604) | Skipped: benchmark was not run |
| 2026-09-17 12:09:22 | skipped | 35172777243 | [105072424132](https://github.com/vllm-project/vllm-ascend/actions/runs/35172777243/job/105072424132) | Skipped: benchmark was not run |
| 2026-09-17 13:10:42 | skipped | 35179457224 | [105084182917](https://github.com/vllm-project/vllm-ascend/actions/runs/35179457224/job/105084182917) | Skipped: benchmark was not run |
| 2026-09-17 13:26:04 | skipped | 35175111205 | [105087231432](https://github.com/vllm-project/vllm-ascend/actions/runs/35175111205/job/105087231432) | Skipped: benchmark was not run |
| 2026-09-17 14:13:50 | skipped | 35188589411 | [105096944250](https://github.com/vllm-project/vllm-ascend/actions/runs/35188589411/job/105096944250) | Skipped: benchmark was not run |
| 2026-09-17 14:24:25 | skipped | 35189336167 | [105099278426](https://github.com/vllm-project/vllm-ascend/actions/runs/35189336167/job/105099278426) | Skipped: benchmark was not run |
| 2026-09-17 16:01:45 | skipped | 35189931528 | [105124104150](https://github.com/vllm-project/vllm-ascend/actions/runs/35189931528/job/105124104150) | Skipped: benchmark was not run |
| 2026-09-17 17:16:28 | skipped | 35196537677 | [105145941131](https://github.com/vllm-project/vllm-ascend/actions/runs/35196537677/job/105145941131) | Skipped: benchmark was not run |
| 2026-09-17 19:07:07 | skipped | 35207821866 | [105178012363](https://github.com/vllm-project/vllm-ascend/actions/runs/35207821866/job/105178012363) | Skipped: benchmark was not run |
| 2026-09-17 20:02:39 | skipped | 35212527226 | [105193944616](https://github.com/vllm-project/vllm-ascend/actions/runs/35212527226/job/105193944616) | Skipped: benchmark was not run |
| 2026-09-18 09:49:14 | skipped | 35293315295 | [105451086067](https://github.com/vllm-project/vllm-ascend/actions/runs/35293315295/job/105451086067) | Skipped: benchmark was not run |
| 2026-09-18 13:03:52 | skipped | 35304848368 | [105487936433](https://github.com/vllm-project/vllm-ascend/actions/runs/35304848368/job/105487936433) | Skipped: benchmark was not run |
| 2026-09-18 17:24:44 | failure | 35328765771 | [105549853185](https://github.com/vllm-project/vllm-ascend/actions/runs/35328765771/job/105549853185) | No throughput row in job log |
| 2026-09-18 19:04:43 | skipped | 35333452541 | [105576691568](https://github.com/vllm-project/vllm-ascend/actions/runs/35333452541/job/105576691568) | Skipped: benchmark was not run |
| 2026-09-19 12:37:59 | skipped | 35421545671 | [105840786864](https://github.com/vllm-project/vllm-ascend/actions/runs/35421545671/job/105840786864) | Skipped: benchmark was not run |
| 2026-09-20 00:02:23 | failure | 35452779632 | [105924745914](https://github.com/vllm-project/vllm-ascend/actions/runs/35452779632/job/105924745914) | No throughput row in job log |
| 2026-09-20 14:46:00 | skipped | 35494393918 | [106036497784](https://github.com/vllm-project/vllm-ascend/actions/runs/35494393918/job/106036497784) | Skipped: benchmark was not run |
| 2026-09-20 14:55:50 | skipped | 35495231163 | [106037609266](https://github.com/vllm-project/vllm-ascend/actions/runs/35495231163/job/106037609266) | Skipped: benchmark was not run |
| 2026-09-20 16:06:55 | skipped | 35496303545 | [106046330290](https://github.com/vllm-project/vllm-ascend/actions/runs/35496303545/job/106046330290) | Skipped: benchmark was not run |
| 2026-09-20 16:14:28 | skipped | 35498721726 | [106047281196](https://github.com/vllm-project/vllm-ascend/actions/runs/35498721726/job/106047281196) | Skipped: benchmark was not run |
| 2026-09-20 16:39:57 | skipped | 35499951041 | [106050443013](https://github.com/vllm-project/vllm-ascend/actions/runs/35499951041/job/106050443013) | Skipped: benchmark was not run |
| 2026-09-20 16:53:14 | skipped | 35500471626 | [106052071567](https://github.com/vllm-project/vllm-ascend/actions/runs/35500471626/job/106052071567) | Skipped: benchmark was not run |
| 2026-09-21 07:53:10 | skipped | 35545736131 | [106171731097](https://github.com/vllm-project/vllm-ascend/actions/runs/35545736131/job/106171731097) | Skipped: benchmark was not run |
| 2026-09-21 08:44:13 | skipped | 35548406902 | [106179107001](https://github.com/vllm-project/vllm-ascend/actions/runs/35548406902/job/106179107001) | Skipped: benchmark was not run |
| 2026-09-21 09:32:21 | skipped | 35550977698 | [106186198975](https://github.com/vllm-project/vllm-ascend/actions/runs/35550977698/job/106186198975) | Skipped: benchmark was not run |
| 2026-09-21 12:27:42 | skipped | 35560768263 | [106213902489](https://github.com/vllm-project/vllm-ascend/actions/runs/35560768263/job/106213902489) | Skipped: benchmark was not run |
| 2026-09-21 15:09:37 | skipped | 35571256527 | [106244285432](https://github.com/vllm-project/vllm-ascend/actions/runs/35571256527/job/106244285432) | Skipped: benchmark was not run |
| 2026-09-21 15:10:32 | skipped | 35571330962 | [106244508803](https://github.com/vllm-project/vllm-ascend/actions/runs/35571330962/job/106244508803) | Skipped: benchmark was not run |
| 2026-09-21 15:37:03 | skipped | 35573454894 | [106250990004](https://github.com/vllm-project/vllm-ascend/actions/runs/35573454894/job/106250990004) | Skipped: benchmark was not run |
| 2026-09-21 15:39:52 | skipped | 35573664370 | [106251693578](https://github.com/vllm-project/vllm-ascend/actions/runs/35573664370/job/106251693578) | Skipped: benchmark was not run |
| 2026-09-21 15:53:14 | skipped | 35574724049 | [106255015174](https://github.com/vllm-project/vllm-ascend/actions/runs/35574724049/job/106255015174) | Skipped: benchmark was not run |
| 2026-09-21 16:15:23 | skipped | 35576498167 | [106260804514](https://github.com/vllm-project/vllm-ascend/actions/runs/35576498167/job/106260804514) | Skipped: benchmark was not run |
| 2026-09-21 16:39:55 | skipped | 35578674990 | [106267511019](https://github.com/vllm-project/vllm-ascend/actions/runs/35578674990/job/106267511019) | Skipped: benchmark was not run |
| 2026-09-21 16:44:20 | skipped | 35579039850 | [106268728248](https://github.com/vllm-project/vllm-ascend/actions/runs/35579039850/job/106268728248) | Skipped: benchmark was not run |
| 2026-09-21 16:58:54 | skipped | 35580295526 | [106272762780](https://github.com/vllm-project/vllm-ascend/actions/runs/35580295526/job/106272762780) | Skipped: benchmark was not run |
| 2026-09-21 17:03:47 | skipped | 35580733048 | [106274160549](https://github.com/vllm-project/vllm-ascend/actions/runs/35580733048/job/106274160549) | Skipped: benchmark was not run |
| 2026-09-21 17:20:34 | skipped | 35582185607 | [106279019927](https://github.com/vllm-project/vllm-ascend/actions/runs/35582185607/job/106279019927) | Skipped: benchmark was not run |
| 2026-09-21 18:40:33 | skipped | 35584252254 | [106301992885](https://github.com/vllm-project/vllm-ascend/actions/runs/35584252254/job/106301992885) | Skipped: benchmark was not run |
| 2026-09-22 11:48:04 | skipped | 35684201527 | [106608276435](https://github.com/vllm-project/vllm-ascend/actions/runs/35684201527/job/106608276435) | Skipped: benchmark was not run |
| 2026-09-22 16:48:07 | failure | 35706162260 | [106677313954](https://github.com/vllm-project/vllm-ascend/actions/runs/35706162260/job/106677313954) | No throughput row in job log |
| 2026-09-22 23:41:27 | failure | 35745271509 | [106818086384](https://github.com/vllm-project/vllm-ascend/actions/runs/35745271509/job/106818086384) | No throughput row in job log |
| 2026-09-23 11:36:02 | skipped | 35806699265 | [107034438971](https://github.com/vllm-project/vllm-ascend/actions/runs/35806699265/job/107034438971) | Skipped: benchmark was not run |
| 2026-09-23 17:36:20 | skipped | 35843438068 | [107125345103](https://github.com/vllm-project/vllm-ascend/actions/runs/35843438068/job/107125345103) | Skipped: benchmark was not run |
| 2026-09-23 18:13:20 | skipped | 35846140918 | [107137186505](https://github.com/vllm-project/vllm-ascend/actions/runs/35846140918/job/107137186505) | Skipped: benchmark was not run |
| 2026-09-23 20:18:27 | skipped | 35859176853 | [107176447101](https://github.com/vllm-project/vllm-ascend/actions/runs/35859176853/job/107176447101) | Skipped: benchmark was not run |
| 2026-09-23 22:27:07 | skipped | 35873703524 | [107225982051](https://github.com/vllm-project/vllm-ascend/actions/runs/35873703524/job/107225982051) | Skipped: benchmark was not run |
| 2026-09-24 11:12:43 | skipped | 35950129704 | [107477784670](https://github.com/vllm-project/vllm-ascend/actions/runs/35950129704/job/107477784670) | Skipped: benchmark was not run |
| 2026-09-24 12:45:02 | skipped | 35956647362 | [107497229302](https://github.com/vllm-project/vllm-ascend/actions/runs/35956647362/job/107497229302) | Skipped: benchmark was not run |
| 2026-09-24 15:58:57 | skipped | 35972148898 | [107545521977](https://github.com/vllm-project/vllm-ascend/actions/runs/35972148898/job/107545521977) | Skipped: benchmark was not run |
| 2026-09-24 19:45:18 | skipped | 35994397246 | [107617291299](https://github.com/vllm-project/vllm-ascend/actions/runs/35994397246/job/107617291299) | Skipped: benchmark was not run |
| 2026-09-25 23:52:18 | skipped | 36143711596 | [108144110514](https://github.com/vllm-project/vllm-ascend/actions/runs/36143711596/job/108144110514) | Skipped: benchmark was not run |
| 2026-09-27 15:35:50 | skipped | 36303363949 | [108575768110](https://github.com/vllm-project/vllm-ascend/actions/runs/36303363949/job/108575768110) | Skipped: benchmark was not run |
| 2026-09-27 16:17:33 | skipped | 36303939512 | [108581908602](https://github.com/vllm-project/vllm-ascend/actions/runs/36303939512/job/108581908602) | Skipped: benchmark was not run |
| 2026-09-27 18:01:08 | skipped | 36309337399 | [108597292356](https://github.com/vllm-project/vllm-ascend/actions/runs/36309337399/job/108597292356) | Skipped: benchmark was not run |
| 2026-09-27 20:26:29 | skipped | 36317275896 | [108619035484](https://github.com/vllm-project/vllm-ascend/actions/runs/36317275896/job/108619035484) | Skipped: benchmark was not run |
| 2026-09-28 01:06:55 | skipped | 36333662989 | [108666072186](https://github.com/vllm-project/vllm-ascend/actions/runs/36333662989/job/108666072186) | Skipped: benchmark was not run |
| 2026-09-28 09:58:49 | skipped | 36367714179 | [108758249330](https://github.com/vllm-project/vllm-ascend/actions/runs/36367714179/job/108758249330) | Skipped: benchmark was not run |
| 2026-09-28 10:21:51 | skipped | 36367499247 | [108762701109](https://github.com/vllm-project/vllm-ascend/actions/runs/36367499247/job/108762701109) | Skipped: benchmark was not run |
| 2026-09-28 12:34:37 | skipped | 36377949943 | [108788556020](https://github.com/vllm-project/vllm-ascend/actions/runs/36377949943/job/108788556020) | Skipped: benchmark was not run |
| 2026-09-28 13:57:43 | skipped | 36383829881 | [108805965553](https://github.com/vllm-project/vllm-ascend/actions/runs/36383829881/job/108805965553) | Skipped: benchmark was not run |
| 2026-09-28 14:24:17 | skipped | 36383793595 | [108812253808](https://github.com/vllm-project/vllm-ascend/actions/runs/36383793595/job/108812253808) | Skipped: benchmark was not run |
| 2026-09-28 15:10:45 | skipped | 36389778699 | [108824226112](https://github.com/vllm-project/vllm-ascend/actions/runs/36389778699/job/108824226112) | Skipped: benchmark was not run |
| 2026-09-28 15:54:32 | skipped | 36393807004 | [108836757703](https://github.com/vllm-project/vllm-ascend/actions/runs/36393807004/job/108836757703) | Skipped: benchmark was not run |
| 2026-09-28 16:41:49 | skipped | 36398406912 | [108851789819](https://github.com/vllm-project/vllm-ascend/actions/runs/36398406912/job/108851789819) | Skipped: benchmark was not run |
| 2026-09-28 17:37:47 | skipped | 36401530561 | [108870582613](https://github.com/vllm-project/vllm-ascend/actions/runs/36401530561/job/108870582613) | Skipped: benchmark was not run |
| 2026-09-28 18:06:05 | skipped | 36407056544 | [108880065609](https://github.com/vllm-project/vllm-ascend/actions/runs/36407056544/job/108880065609) | Skipped: benchmark was not run |
| 2026-09-28 21:03:25 | skipped | 36409554688 | [108939641930](https://github.com/vllm-project/vllm-ascend/actions/runs/36409554688/job/108939641930) | Skipped: benchmark was not run |
| 2026-09-29 11:47:33 | skipped | 36508186139 | [109246661909](https://github.com/vllm-project/vllm-ascend/actions/runs/36508186139/job/109246661909) | Skipped: benchmark was not run |
| 2026-09-29 13:59:09 | skipped | 36519229608 | [109277505423](https://github.com/vllm-project/vllm-ascend/actions/runs/36519229608/job/109277505423) | Skipped: benchmark was not run |
| 2026-09-29 16:30:19 | skipped | 36530370555 | [109323064678](https://github.com/vllm-project/vllm-ascend/actions/runs/36530370555/job/109323064678) | Skipped: benchmark was not run |
| 2026-09-29 17:39:17 | skipped | 36536567193 | [109347390770](https://github.com/vllm-project/vllm-ascend/actions/runs/36536567193/job/109347390770) | Skipped: benchmark was not run |
| 2026-09-29 19:31:57 | skipped | 36555072860 | [109385881051](https://github.com/vllm-project/vllm-ascend/actions/runs/36555072860/job/109385881051) | Skipped: benchmark was not run |
| 2026-09-29 22:13:53 | skipped | 36568604025 | [109449160882](https://github.com/vllm-project/vllm-ascend/actions/runs/36568604025/job/109449160882) | Skipped: benchmark was not run |
| 2026-09-29 22:40:58 | skipped | 36565522448 | [109461022381](https://github.com/vllm-project/vllm-ascend/actions/runs/36565522448/job/109461022381) | Skipped: benchmark was not run |
| 2026-09-30 01:05:44 | skipped | 36586487080 | [109523094921](https://github.com/vllm-project/vllm-ascend/actions/runs/36586487080/job/109523094921) | Skipped: benchmark was not run |
| 2026-09-30 04:09:39 | skipped | 36609362298 | [109597422353](https://github.com/vllm-project/vllm-ascend/actions/runs/36609362298/job/109597422353) | Skipped: benchmark was not run |
| 2026-09-30 11:20:31 | skipped | 36654343220 | [109724512025](https://github.com/vllm-project/vllm-ascend/actions/runs/36654343220/job/109724512025) | Skipped: benchmark was not run |
| 2026-09-30 11:42:22 | skipped | 36665193676 | [109729477875](https://github.com/vllm-project/vllm-ascend/actions/runs/36665193676/job/109729477875) | Skipped: benchmark was not run |
| 2026-10-02 23:59:12 | skipped | 37030286885 | [110916815766](https://github.com/vllm-project/vllm-ascend/actions/runs/37030286885/job/110916815766) | Skipped: benchmark was not run |
| 2026-10-06 22:28:39 | skipped | 37468409449 | [112322850709](https://github.com/vllm-project/vllm-ascend/actions/runs/37468409449/job/112322850709) | Skipped: benchmark was not run |
| 2026-10-07 10:58:39 | skipped | 37564205558 | [112609196614](https://github.com/vllm-project/vllm-ascend/actions/runs/37564205558/job/112609196614) | Skipped: benchmark was not run |
| 2026-10-08 13:05:34 | skipped | 37720678582 | [113158729908](https://github.com/vllm-project/vllm-ascend/actions/runs/37720678582/job/113158729908) | Skipped: benchmark was not run |
| 2026-10-08 16:16:02 | skipped | 37748018156 | [113216316822](https://github.com/vllm-project/vllm-ascend/actions/runs/37748018156/job/113216316822) | Skipped: benchmark was not run |
