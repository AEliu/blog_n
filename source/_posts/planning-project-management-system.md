---
title: 规划项目管理系统
urlname: planning-project-management-system
date: 2020-04-27 21:40:27
tags:
- IT
- 工作
- Django
- Web-development
---

每次写总结都很苦恼，需要统计做过的规划项目进行统计，但一时间不能很快的得到统计数据，这件事变成了一件难事，每次都非常繁琐。平时对项目的进度管理、档案管理也都存在问题：虽然数量不多，但混乱的文件夹让人不愿意再回头翻看一遍。一直想用计算机来管理，正好遇见了 Django，不如照猫画虎，自己攒一个「规划项目管理系统」，在此记录制作系统的想法、问题以及学习的过程。

<!-- more -->

## 需求

规划项目的大致流程为：申报 -> 受理 -> 专家评审会 -> 规划委员会 -> 审定 -> 归档，这仅是前期审查所涉及的部分内容，围绕上面的步骤对整个项目进行线上的管理，详细分析如下：

1. 项目初始化，信息登记，项目名称、类型、建设单位、设计单位、位置等，由我们内部管理人员进行登记；
2. 专家名单的维护，专家评审会时向参会专家发送会议通知；
3. 参会部门及人员的维护，专家评审会时向部门的参会人员发送会议通知；
4. 专家评审会信息，时间、地点、人员、纪要、是否通过等，涉及多个项目属于同一个评审会；
5. 根据不同的项目类型选择规委会，涉及规委会时间、纪要、会议意见等；
6. 规委会的审定过程，记录审定表及最终审定方案或文本；
7. 人员权限、登录管理；
8. 固定时间段内项目数量、名称、分布等情况，指定人员或专家参会的情况。