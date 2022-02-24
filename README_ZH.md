# PersonQuery

![ExamplePic](https://github.com/ninthseason/PersonQuery/blob/main/src/assets/PersonQueryExample.png)

用于显示存于你数据库中的人员信息。

这只是项目的前端部分. 如果你想去使用它，需要自己编写与之匹配的后端.

[English](https://github.com/ninthseason/PersonQuery/blob/main/README.md) | 中文

## Guide

这是一个展示高校学生信息的例子。

你需要去实现一个支持 GET 方法的 api。

这个 api 可以接收五个参数如下: id, name, college, major, QQ. (id 指学生的学号, QQ 指学生的 QQ 号)

这个 api 会返回一个列表，其包含所有符合传入参数条件的学生。

响应看起来是这样的:

```json
[
  {
    "Id": "123456789",
    "Name": "张三",
    "College": "计算机学院",
    "Major": "计算机科学与技术",
    "QQ": "1234567890"
  },
  {
    "Id": "123456780",
    "Name": "李四",
    "College": "计算机学院",
    "Major": "软件工程",
    "QQ": "1234567891"
  }
]
```

前端部分的职责就是将后端返回的信息展示在网页上。

你可以修改 Vue 模板的代码，使之适配你的项目.
