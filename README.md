## 本项目实现的最终作用是基于SSH公司内部办公自动化管理系统
## 分为3个角色
### 第1个角色为员工角色，实现了如下功能：
 - 公司信息查询
 - 员工登录
 - 工作任务管理
 - 工作日志管理
 - 收发邮件管理
 - 考勤管理
 - 部门共享文档
### 第2个角色为管总经理角色，实现了如下功能：
 - 人事管理
 - 信息发布管理
 - 共享文档管理
 - 发送邮件
 - 密码修改
 - 总经理登录
 - 接受邮件
 - 部门管理
### 第3个角色为部门经理角色，实现了如下功能：
 - 工作任务管理
 - 收发邮件
 - 部门人事管理
 - 部门信息发布管理
 - 部门文档管理
 - 部门经理登录
 - 部门考勤管理
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssh_gongsi_sys

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [t_bumen](#t_bumen) |  |
| [t_gongzuorizhi](#t_gongzuorizhi) |  |
| [t_info](#t_info) |  |
| [t_kaoqin](#t_kaoqin) |  |
| [t_renwu](#t_renwu) |  |
| [t_tongxunlu](#t_tongxunlu) |  |
| [t_user](#t_user) | 用户表 |
| [t_wendang](#t_wendang) |  |
| [t_youjian](#t_youjian) |  |

**表名：** <a id="t_bumen">t_bumen</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | bumenlock |   int   | 10 |   0    |    N     |  N   |       |   |
|  3   | bumenming |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | dianhua |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 电话  |
|  5   | jianjie |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_gongzuorizhi">t_gongzuorizhi</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | content |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  3   | gongzuorizhilock |   int   | 10 |   0    |    N     |  N   |       |   |
|  4   | shijian |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  5   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  6   | userid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_info">t_info</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | content |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  3   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  4   | infolock |   int   | 10 |   0    |    N     |  N   |       |   |
|  5   | leixing |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  7   | bumenid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |
|  8   | userid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_kaoqin">t_kaoqin</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | beizhu |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 备注  |
|  3   | createtime |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  4   | kaoqinlock |   int   | 10 |   0    |    N     |  N   |       |   |
|  5   | leixing |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | shenhejieguo |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | shenhezhuangtai |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | userid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_renwu">t_renwu</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | content |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  3   | renwulock |   int   | 10 |   0    |    N     |  N   |       |   |
|  4   | shijian |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  5   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  6   | wanchenghuibao |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | wanchengpingggu |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | wanchengqingkuang |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  9   | fromuserid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |
|  10   | touserid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_tongxunlu">t_tongxunlu</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | lianxidianhua |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 联系电话  |
|  3   | truename |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | zhuzhi |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | userid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_user">t_user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  3   | jianjie |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | lianxidianhua |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 联系电话  |
|  5   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  6   | role |   int   | 10 |   0    |    N     |  N   |       | 角色  |
|  7   | ruzhishijian |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | sfz |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  9   | truename |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  10   | userlock |   int   | 10 |   0    |    N     |  N   |       |   |
|  11   | username |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 用户名  |
|  12   | xingbie |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 性别  |
|  13   | zhuzhi |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  14   | bumenid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |
|  15   | bumenid2 |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_wendang">t_wendang</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | content |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  3   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  4   | path |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 路径  |
|  5   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  6   | wendanglock |   int   | 10 |   0    |    N     |  N   |       |   |
|  7   | bumenid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |
|  8   | userid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_youjian">t_youjian</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | content |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  3   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  4   | readzhuangtai |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  6   | youjianlock |   int   | 10 |   0    |    N     |  N   |       |   |
|  7   | fromuserid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |
|  8   | touserid |   bigint   | 20 |   0    |    Y     |  N   |   NULL    |   |

