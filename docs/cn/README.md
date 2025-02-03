
<div align="center">

<image src="http://m.qpic.cn/psc?/V51UyG6T2hLdbN0oEgHl3fEkH73KqJt7/TmEUgtj9EK6.7V8ajmQrEEsEylM*52lTktZHLze*PTbMCd2wg4o5kkEyKNVsVL9UM5xK4GLClF.TOL*ty*FnqAuxBQmobbAoJ.gYMo62EQY!/mnull&bo=wADAAAAAAAADByI!&rf=photolist&t=5" height="64"/>

# CSES

通用的课程表交换格式

[**English**](../../README.md) | **中文简体**

</div>

## 简介

CSES 是一种通用的课程表交换格式，用于在不同软件之间交换课程表。它被设计为简单易用，可以轻松转换为其他格式，如 ClassIsland 格式。

## 特点

- **简单**: CSES 被设计为简单易用。
- **通用**: CSES 是一种通用格式，可以轻松转换为其他格式。
- **易用**: CSES 易于使用，可以轻松被人类理解。

## 规范

### 先决条件
- 必须采用 UTF-8 编码
- 只能采用空格缩进，不允许使用制表符
- 文件开头要有标识符

### 标识符

```yaml
!Data
Name: # 课表名称
Type: CSES
Version: # 采用的 CSES 版本
```

### 课程声明

```yaml
Subjects:
    - Name: 语文
      SimplifiedName: 语 # Optional
      Teacher: Mr. A # Optional
      Room: 101 # Optional
      IsOutDoorClass: false # Optional, default. false
    - Name: 数学
```

### 时间线声明

```yaml
TimeTable:
    - Id: # 编号，非可选
    - Name: 
    - TimeZone: # Optional, default. UTC+08:00
    - WeekDiv: # int, Optional，舍弃WeekTotal，根据WeekDiv自动读取，要求WeekDiv必须连续
    - TimeSlot:
        - Name: 
          Id: # 非可选
          Type: # 待定，如早读、晚自习之类的玩意，非可选
          StartTime: "hh:mm:ss"
          EndTime: "hh:mm:ss"
    - TimeSlot: 
        # ...
```

### 课表安排
```yaml
Schedule:
    - Name: "Monday" # string
      TimeTable: # int
      EnableDay: 1
      Classes:
        - Subject:
          TimeSlot: #int
        - Subject:
          TimeSlot:
    - Name: "Tuesday"
```
## 协议

[MIT](./LICENSE)

