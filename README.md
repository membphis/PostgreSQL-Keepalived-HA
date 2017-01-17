﻿Keepalived + PostgreSQL 流复制方式实现高可用 HA
====================
ddddddddddddddddddddddddd
一 项目简介
---

  HA 是数据库领域一个永恒的议题，同时也是最复杂的方案之一，PostgreSQL 本身并不提供任何高可用方案， 本文通过 Keepalived + PostgreSQL 流复制方式实现高可用 HA，故障切换逻辑和部分脚本参考德哥 sky_postgresql_cluster (https://github.com/digoal/sky_postgresql_cluster) 的 HA 项目，本文仅分享一种 PostgreSQL的高可用方案，脚本的切换逻辑可根据实际情况调整，如果您对此方案有更好的建议或补充，欢迎探讨。

Email: francs3@163.com

二 需求
---

- PostgreSQL 9.4 版本：其它版本脚本需做相应调整
- 硬件：2 台带远程管理卡的物理主机：在数据库发生切换时需要用到远程管理卡
- 两台物理主机安装 Keepalived 程序
