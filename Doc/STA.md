[toc]

# STA (System of Technology Achievement) 需求分析

## 1. 引言

****

### 1.1. 编写目的

### 1.2. 项目背景 

### 1.3. 术语定义

| 术语 | 含义 | 缩写 |
| ---- | ---- | ---- |
|      |      |      |



## 2. 项目概述

****

### 2.1. 目标

### 2.2. 运行环境

### 2.3. 条件限制



## 3. 项目需求

****

### 3.1. 成果展示

### 3.2. 条目搜索

### 3.3. 数据管理



## 4. 功能需求

****

### 4.1. 查询

### 4.2. 修改

### 4.3. 导入

### 4.4. 删除





# E-R

## Personnel

- perId

- perName

- perDegree

- perEB: Education Background

- perTitle

## Project

- proId

- proName

- proCategory

- proHeader

- proMember

- proST

- proET

- proUU: Undertaking Unit

- proPF: Project Fund

- proGU: Grant Unit

## Paper

- paperId
- paperName
- paperFA: First Author
- paperCA: Corresponding Author
- paperPT: Published Time
- paperVP: Volume and Periodical
- paperNP: Number of pages
- paperCT: Collection Types {SCI, EI, CC(Chinese Core), Other}

## Patent

- paId
- paApplicant
- paName
- paNumber
- paAN: Application Number
- paDA: Date of Authorization
- paType: {International, Country, UM(Utility Model), Appearance, SC(Software CopyRight)}
- paIE: Is End
- palApC: Applicant Country
- palAuC: Authorized Country

## Monograph

- moId
- moName
- moAuthor
- moPress.
- moDP: Date of publication
- moISBN

## Scientific Research & Teaching Award

- staId
- staType: {SR, T}
- staWinner
- staName
- staRT: reword Type
- staTime
- staIT: Is Teacher
- staNote

## Meeting

- mId
- mName
- mMember
- mTime
- mAddress
- mType
- mNote

