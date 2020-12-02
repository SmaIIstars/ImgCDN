# STA (System of Technology Achievement) 需求分析

## 1. 引言

****

### 1.1. 编写目的

明确 STA 系统项目需求，构建流程，进行高质量、高效率地程序开发。

### 1.2. 项目背景 

科研成果逐年增加，查询效率太低。现开发一个 Web 应用，实现科研成果管理系统，将数据可视化，方便管理。

### 1.3. 术语定义

|               术语               |       含义       | 缩写 |
| :------------------------------: | :--------------: | :--: |
| System of Technology Achievement | 科研技术成果系统 | STA  |



## 2. 项目概述

****

### 2.1. 目标

- 请求数据， 能够实现网页内容分类
- 可进行重复或冗余网页的去重过滤
- 对经去冗以后的内容建立索引
- 支持自然语言的模糊检索
- 可实现搜索结果的可视化呈现

### 2.2. 运行环境

- 全平台: Windows、Mac、Linux
- 浏览器: Web 浏览器（推荐 Chrome，不支持 IE）

### 2.3. 条件限制

- 可运行 Web 浏览器的硬件条件及其以上运行程序
- 开发时间 4 周内

## 3. 项目需求

****

### 3.1. 成果展示

- 人员信息展示
- 项目展示
- 论文展示
- 专利展示
- 专著展示
- 科研/教学获奖展示
- 会议记录展示

### 3.2. 条目搜索

- 人员搜索
- 各个条目搜索
- 多条件搜索

### 3.3. 数据管理

- 数据查询
- 数据导入
- 数据删除
- 数据更改

## 4. 功能需求

****

### 4.1. 查询

### 4.2. 修改

### 4.3. 导入

### 4.4. 删除



## 5. 运行需求

****

### 5.1. 数据库

#### 5.1.1. 数据库选择

1. MySQL

   - 优点
     - 使用成本低
     - 适用所有平台
     - 体积小，性能好
     - 源码开放
     - 支持多操作系统

   - 缺点
     - 不支持热备份
     - 没有存储过程语言

2. SQL Server

   - 优点
     - 图形化界面，管理方便
     - 编程接口工具丰富

   - 缺点
     - 中等贵
     - 只能在 Windows 直接运行，其他操作系统需要另外配置

3. Oracle

   - 优点
     - 十分安全
     - 性能高，稳定性好

   - 缺点
     - 贵
     - 硬件要求高
     - 管理麻烦，使用成本高

STA 最终选择 MySQL 作 DBMS

#### 5.1.2. E-R 图

- 人员

  ![Personnel](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-Personnel.png)

- 项目

  ![Project](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-Project.png)

- 论文

  ![Paper](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-Paper.png)

- 专利

  ![Patent](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-Patent.png)

- 专著

  ![Monograph](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-Monograph.png)

- 科研&教学获奖

  ![ScientificResearch&TeachingAward](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-ScientificResearch&TeachingAward.png)

- 会议

  ![Meeting](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-Meeting.png)

- 实体与实体之间的关系 E-R 图

  ![All](https://cdn.jsdelivr.net/gh/SmaIIstars/imgCDN/STA/ER-All.png)

#### 5.1.3. 数据库表结构设计

- Personnel

  |  字段名   | 数据类型 | 长度 | 说明 |         描述         |
  | :-------: | :------: | :--: | :--: | :------------------: |
  |   perId   |          |      |      |                      |
  |  perName  |          |      |      |                      |
  | perDegree |          |      |      |                      |
  |   perEB   |          |      |      | Education Background |
  | perTitle  |          |      |      |                      |

- Project

  | 字段名 | 数据类型 | 长度 | 说明 | 描述 |
  | :-------: | :------: | :--: | :--: | :------------------: |
  | proId |          |      |      |      |
| proName | | | | |
  | proCategory | | | | |
  | proHeader | | | | |
  | proMember | | | | |
  | proST | | | | |
  | proET | | | | |
  | proUU | | | | Undertaking Unit |
  | proPF | | | | Project Fund |
  | proGU | | | | Grant Unit |
  
- Paper

  |  字段名   | 数据类型 | 长度 | 说明 |                        描述                         |
  | :-------: | :------: | :--: | :--: | :-------------------------------------------------: |
  |  paperId  |          |      |      |                                                     |
  | paperName |          |      |      |                                                     |
  |  paperFA  |          |      |      |                    First Author                     |
  |  paperCA  |          |      |      |                Corresponding Author                 |
  |  paperPT  |          |      |      |                   Published Time                    |
  |  paperVP  |          |      |      |                Volume and Periodical                |
  |  paperNP  |          |      |      |                   Number of pages                   |
  |  paperCT  |          |      |      | Collection Types {SCI, EI, CC(Chinese Core), Other} |

- Patent

  |   字段名    | 数据类型 | 长度 | 说明 |                             描述                             |
  | :---------: | :------: | :--: | :--: | :----------------------------------------------------------: |
  |    paId     |          |      |      |                                                              |
  |   paName    |          |      |      |                                                              |
  | paApplicant |          |      |      |                                                              |
  |  paNumber   |          |      |      |                                                              |
  |    paAN     |          |      |      |                      Application Number                      |
  |    paDA     |          |      |      |                    Date of Authorization                     |
  |   paType    |          |      |      | {International, Country, UM(Utility Model), Appearance, SC(Software CopyRight)} |
  |    paIE     |          |      |      |                            Is End                            |
  |   palApC    |          |      |      |                      Applicant Country                       |
  |   palAuC    |          |      |      |                      Authorized Country                      |

- Monograph

  |  字段名  | 数据类型 | 长度 | 说明 |        描述         |
  | :------: | :------: | :--: | :--: | :-----------------: |
  |   moId   |          |      |      |                     |
  |  moName  |          |      |      |                     |
  | moAuthor |          |      |      |                     |
  | moPress. |          |      |      |                     |
  |   moDP   |          |      |      | Date of publication |
  |  moISBN  |          |      |      |                     |

- Scientific Research & Teaching Award

  |  字段名   | 数据类型 | 长度 | 说明 |    描述     |
  | :-------: | :------: | :--: | :--: | :---------: |
  |   staId   |          |      |      |             |
  |  staName  |          |      |      |             |
  |  staType  |          |      |      |   {SR, T}   |
  | staWinner |          |      |      |             |
  |   staRT   |          |      |      | reword Type |
  |  staTime  |          |      |      |             |
  |   staIT   |          |      |      | Is Teacher  |
  |  staNote  |          |      |      |             |

- Meeting

  |  字段名  | 数据类型 | 长度 | 说明 | 描述 |
  | :------: | :------: | :--: | :--: | :--: |
  |   mId    |          |      |      |      |
  |  mName   |          |      |      |      |
  | mMember  |          |      |      |      |
  |  mTime   |          |      |      |      |
  | mAddress |          |      |      |      |
  |  mType   |          |      |      |      |
  |  mNote   |          |      |      |      |

### 5.2. 后端



### 5.3. 前端



## 6. 其他需求

****

### 6.1. 可维护性

### 6.2. 可移植性

### 6.3. 数据完整性


