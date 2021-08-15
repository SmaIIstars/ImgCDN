[toc]

# STA (System of Technology Achievement) 需求分析

## 1. 引言

---

### 1.1. 编写目的

明确 STA 系统项目需求，构建流程，进行高质量、高效率地程序开发。

### 1.2. 项目背景

科研成果逐年增加，查询效率太低。现开发一个 Web 应用，实现科研成果管理系统，将数据可视化，方便管理。

### 1.3. 术语定义

|               术语               |       含义       | 缩写 |
| :------------------------------: | :--------------: | :--: |
| System of Technology Achievement | 科研技术成果系统 | STA  |

## 2. 项目概述

---

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

---

### 3.1. 成就展示页面

- 人员信息展示

  1. 对人员信息进行检索，表格罗列符合条件人员

  2. 个人详情页先展示人员基础信息，后罗列相应成就

- 项目展示

  1. 对项目信息进行检索，表格罗列符合条件项目信息

  2. 项目详情页展示项目详情信息

- 论文展示

  1. 对论文信息进行检索，表格罗列符合条件论文信息

  2. 论文详情页展示论文详细信息

- 专利展示

  1. 对专利信息进行检索，表格罗列符合条件专利信息

  2. 专利详情页展示专利详情信息

- 专著展示

  1. 对专著信息进行检索，表格罗列符合条件专著信息

  2. 专著详情页展示专著详细信息

- 科研/教学获奖展示

  1. 对获奖信息进行检索，表格罗列符合条件获奖信息

  2. 获奖详情页展示获奖详细信息

- 会议记录展示

  1. 对会议信息进行检索，表格罗列符合条件会议信息

  2. 会议详情页展示会议详细信息

### 3.2. 条目搜索

- 人员搜索

  编号，姓名，职称，学历作为条件的搜索

- 各个条目搜索

  编号，名称，类型作为条件的搜索

### 3.3. 数据管理

- 数据导入

  支持模板 Excel 表格导入信息

- 数据删除

  支持对单项或多项数据进行删除操作

- 数据更改

  支持对数据信息的更改操作

## 4. 功能需求

---

### 4.1. 查询

数据查询

### 4.2. 修改

数据修改

### 4.3. 导入

数据导入

### 4.4. 删除

数据删除

### 4.5. 权限管理

- 权限等级
  1. 普通：查
  2. 管理：增删改查
  3. 超级管理：控制更改管理权限

## 5. 运行需求

---

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

- User

  |   字段名   | 数据类型 | 长度 |     说明     |   描述   |
  | :--------: | :------: | :--: | :----------: | :------: |
  |    uId     | varchar  | 255  |     主键     |  用户ID  |
  |   uName    | varchar  | 255  |              | 用户名称 |
  | uPassword  | varchar  | 255  | Hash加密存储 | 用户密码 |
  | uAuthority |   Int    |  20  |              | 用户权限 |
  
- Personnel

  |  字段名   | 数据类型 | 长度 | 说明 |  描述  |
  | :-------: | :------: | :--: | :--: | :----: |
  |   perId   | varchar  | 255  | 主键 | 人员ID |
  |  perName  | varchar  | 255  |      |  名称  |
  | perDegree | varchar  | 255  |      |  学位  |
  |   perEB   | varchar  | 255  |      |  学历  |
  | perTitle  | varchar  | 255  |      |  职称  |

- Project

  |   字段名    | 数据类型 | 长度 | 说明 |    描述    |
  | :---------: | :------: | :--: | :--: | :--------: |
  |    proId    | varchar  | 255  | 主键 |   项目ID   |
  |   proName   | varchar  | 255  |      |    名称    |
  |   proYear   |   date   | 255  |      |  项目年度  |
  | proCategory | varchar  | 255  |      |    类别    |
  |  proHeader  | varchar  | 255  |      | 项目负责人 |
  |  proMember  | varchar  | 255  |      |  项目成员  |
  |    proST    |   date   | 255  |      |  开始时间  |
  |    proET    |   date   | 255  |      |  结束时间  |
  |    proUU    | varchar  | 255  |      |  承担单位  |
  |    proPF    | varchar  | 255  |      |    资金    |
  |    proGU    | varchar  | 255  |      |  拨款单位  |

- Paper

  |  字段名   | 数据类型 | 长度 | 说明 |     描述     |
  | :-------: | :------: | :--: | :--: | :----------: |
  |  paperId  | varchar  | 255  | 主键 |    论文ID    |
  | paperName | varchar  | 255  |      |   论文名称   |
  |  paperFA  | varchar  | 255  |      |   第一作者   |
  |  paperCA  | varchar  | 255  |      |   通讯作者   |
  |  paperPT  |   date   | 255  |      |   发表时间   |
  |  paperPN  | varchar  | 255  |      | 发表刊物名称 |
  |  paperVP  | varchar  | 255  |      | 卷号/期刊号  |
  |  paperSP  |   Int    |  20  |      |   开始页数   |
  |  paperEP  |   Int    |  20  |      |   结束页数   |
  |  paperCT  | varchar  | 255  |      |     类型     |

- Patent

  |   字段名    | 数据类型 | 长度 | 说明 |    描述    |
  | :---------: | :------: | :--: | :--: | :--------: |
  |    paId     | varchar  | 255  | 主键 |   专利ID   |
  |   paName    | varchar  | 255  |      |  专利名称  |
  | paApplicant | varchar  | 255  |      |   申请人   |
  |    paDA     |   date   | 255  |      |  授权日期  |
  |   paType    | varchar  | 255  |      |    类型    |
  |    paIE     |   Int    |  20  |      | 是否新申请 |
  |    paApC    | varchar  | 255  |      |  申请国家  |
  |    paAuC    | varchar  | 255  |      |  授权国家  |

- Monograph

  |  字段名  | 数据类型 | 长度 | 说明 |    描述    |
  | :------: | :------: | :--: | :--: | :--------: |
  |  moISSN  | varchar  | 255  | 主键 | 专著ISSN码 |
  |  moName  | varchar  | 255  |      |  专著名称  |
  | moAuthor | varchar  | 255  |      |   著作者   |
  | moPress  | varchar  | 255  |      | 出版社名称 |
  |   moDP   |   date   | 255  |      |  出版日期  |

- Scientific Research & Teaching Award

  |  字段名   | 数据类型 | 长度 | 说明 |      描述       |
  | :-------: | :------: | :--: | :--: | :-------------: |
  |   staId   | varchar  | 255  | 主键 | 科研/教学获奖ID |
  |  staName  | varchar  | 255  |      |    获奖名称     |
  |  staType  | varchar  | 255  |      |   科研或教学    |
  | staWinner | varchar  | 255  |      |     获奖者      |
  |   staRT   | varchar  | 255  |      |    奖励类别     |
  |  staTime  |   date   | 255  |      |    获奖日期     |
  |   staIT   | varchar  | 255  |      |   老师或学生    |
  |  staNote  | varchar  | 255  |      |      备注       |

- Meeting

  |  字段名  | 数据类型 | 长度 | 说明 |   描述   |
  | :------: | :------: | :--: | :--: | :------: |
  |   mId    | varchar  | 255  | 主键 |  会议ID  |
  |  mName   | varchar  | 255  |      | 会议名称 |
  | mMember  | varchar  | 255  |      |   成员   |
  |  mTime   |   date   | 255  |      |   时间   |
  | mAddress | varchar  | 255  |      |   地址   |
  |  mType   | varchar  | 255  |      |   类型   |
  |  mNote   | varchar  | 255  |      |   备注   |

### 5.2. 后端

- 整体环境: Python + Flask
- 数据库: MySQL + Flask-SQLalchemy
- 数据处理: Flask-RESTful
- 端口部署: Flask

### 5.3. 前端

- 前端环境: Nodejs
- 前端框架: React
- 样式框架: AntD + Bizcharts

## 6. 其他需求

---

### 6.1. 可维护性

- 各个功能独立，协同工作。不修改关联数据，各个模块不会影响其他模块
- 各模块耦合度低，扩展性强
- 文档齐全，规范

### 6.2. 可移植性

- 前端打包 dist 文件可在任何有 node 环境下运行
- 后端 Python 文件可在人后有 Python 环境下运行
