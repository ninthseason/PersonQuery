# PersonQuery

![ExamplePic](https://github.com/ninthseason/PersonQuery/blob/main/src/assets/PersonQueryExample.png)

To show the infotmation of people which is in your database.

This is only the front end. If you want to use it, you should create a backend which is matched with it by yourself.

[English]() | [中文]()

## Guide

The example is to display infomation of university students.

You need to achieve an api with 'GET' method.

The api can receive five parameters, as follows: id, name, college, major and QQ. (The 'id' is student's number and the 'QQ' is the number of a famous social software)

The api will respond with a list of students' infomation which is filtered by received parameters.

The response looks like:

```json
[
  {
    "Id": "123456789",
    "Name": "Mike",
    "College": "The college of Computer Science",
    "Major": "artificial intelligence",
    "QQ": "1234567890"
  },
  {
    "Id": "123456780",
    "Name": "Bob",
    "College": "The college of Computer Science",
    "Major": "software engineering",
    "QQ": "1234567891"
  }
]
```

The frontend's duty is to display the data returned by the backend.

You can modify the Vue template to make it adapted to your project.
