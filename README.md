<div align="center">

<image src="http://m.qpic.cn/psc?/V51UyG6T2hLdbN0oEgHl3fEkH73KqJt7/TmEUgtj9EK6.7V8ajmQrEEsEylM*52lTktZHLze*PTbMCd2wg4o5kkEyKNVsVL9UM5xK4GLClF.TOL*ty*FnqAuxBQmobbAoJ.gYMo62EQY!/mnull&bo=wADAAAAAAAADByI!&rf=photolist&t=5" height="64"/>

# UCSF

The Universal Class Schedule Format

**English** | [**中文简体**](./docs/cn/README.md)

</div>

## Introduction

UCSF is a universal class schedule format that can be used to describe the class schedule. It is designed to be simple and easy to use, and can be easily converted to other formats such as ClassIsland format.

## Features

- **Simple**: UCSF is designed to be simple and easy to use.
- **Universal**: UCSF is a universal format that can be easily converted to other formats.
- **Easy to use**: UCSF is easy to use and can be easily understood by humans.

## Example

```yaml
subjects:
  - name: Math
    simplified_name: M # Better for Chinese subject name
    teacher: Mr. A
    room: 101
  - name: English
    simplified_name: E
    teacher: Mr. B
    room: 102
  - name: Physics
    simplified_name: P
    teacher: Mr. C
    room: 103
  - name: Chemistry
    simplified_name: C
    teacher: Mr. D
    room: 104

schedules:
  - name: Monday
    enable_day: mon
    weeks: all
    classes:
      - subject: Math
        start_time: 8:00
        end_time: 9:00
      - subject: English
        start_time: 9:00
        end_time: 10:00
  - name: Tuesday-Odd
    enable_day: tue
    weeks: odd
    classes:
      - subject: Physics
        start_time: 8:00
        end_time: 9:00
      - subject: English
        start_time: 9:00
        end_time: 10:00
  - name: Tuesday-Even
    enable_day: tue
    weeks: even
    classes:
      - subject: Chemistry
        start_time: 8:00
        end_time: 9:00
      - subject: English
        start_time: 9:00
        end_time: 10:00
```

## License

[MIT](./LICENSE)

