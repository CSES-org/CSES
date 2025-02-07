
<div align="center">

<image src="http://m.qpic.cn/psc?/V51UyG6T2hLdbN0oEgHl3fEkH73KqJt7/TmEUgtj9EK6.7V8ajmQrEEsEylM*52lTktZHLze*PTbMCd2wg4o5kkEyKNVsVL9UM5xK4GLClF.TOL*ty*FnqAuxBQmobbAoJ.gYMo62EQY!/mnull&bo=wADAAAAAAAADByI!&rf=photolist&t=5" height="64"/>

# CSES

通用的课程表交换格式

[**English**](../../README.md) | **中文简体**

</div>

## 简介

CSES 是一种通用的课程表交换格式，用于在不同软件之间交换课程表。它被设计为简单易用，可以轻松转换为其他格式，如 ClassIsland 格式。我们提供 [CSES Editor](https://edit.cses-org.cn/) 便于您创建和编辑课表并导出为 CSES 格式。

## 特点

- **简单**: CSES 被设计为简单易用。
- **通用**: CSES 是一种通用格式，可以轻松转换为其他格式。
- **易用**: CSES 易于使用，可以轻松被人类理解。

## 语法规则

### 文件层面

CSES 要求文件扩展名为 `.yml` 或 `.yaml` 的格式，也就是使用 Yaml 语法。同时，文件编码**必须**是 UTF-8。

### 声明版本

```yaml
version: 1
```

### 定义科目

```yaml
subjects:
  - name: 数学 # 科目名称
    simplified_name: 数 # 可选，科目简称，适合中文科目名，ClassIsland 等紧凑课程表软件一般需要
    teacher: 李梅 # 可选，任课教师
    room: 101 # 可选，上课地点
```

### 定义课表

```yaml
schedules:
  - name: 星期一 # 课表名称
    enable_day: 1 # 星期，范围1-7
    weeks: all # 所有周都启用，字段可选值为 [ "all" | "odd" | "even" ]，分别对应所有、单周、双周
    classes:
      - subject: 数学 # 上面定义的科目名称（注意不是简称）
        start_time: "08:00:00" # 上课时间，格式 "HH:MM:SS"
        end_time: "09:00;00" # 下课时间，格式同上课时间
```

## 示例

文件名: xxx.yml/xxx.yaml
编码: UTF-8

```yaml
version: 1
subjects:
  - name: 数学
    simplified_name: 数 # 可选，适合中文科目名，ClassIsland 等紧凑课程表软件一般需要
    teacher: 李梅 # 可选
    room: 101 # 可选
  - name: 语文
    simplified_name: 语
    teacher: 王芳
    room: 102
  - name: 英语
    simplified_name: 英
    teacher: 张伟
    room: 103
  - name: 物理
    simplified_name: 物
    teacher: 赵军
    room: 104

schedules:
  - name: 星期一
    enable_day: 1
    weeks: all
    classes:
      - subject: 数学
        start_time: "08:00:00"
        end_time: "09:00:00"
      - subject: 语文
        start_time: "09:00:00"
        end_time: "10:00:00"
  - name: 星期二-单周
    enable_day: 2
    weeks: odd
    classes:
      - subject: 物理
        start_time: "08:00:00"
        end_time: "09:00:00"
      - subject: 英语
        start_time: "09:00:00"
        end_time: "10:00:00"
  - name: 星期二-双周
    enable_day: 2
    weeks: even
    classes:
      - subject: 物理
        start_time: "08:00:00"
        end_time: "09:00:00"
      - subject: 英语
        start_time: "09:00:00"
        end_time: "10:00:00"
```

## 协议

[MIT](./LICENSE)

