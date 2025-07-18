# 莘应用(自定义数据源指南)

这是制作莘应用自定义数据源的官方指导文档。

[莘应用下载官网](https://edsq.edsc.top/)

## 缘由
我们想打造一款支持高度自定义、强稳定性的手表应用商店！

客户端代码开放，你可以根据自定义数据源功能打造和定制你自己的应用商店：[客户端源码](https://github.com/Genouka/XinAppStore)！

自莘应用1.4起开始支持自定义数据源！

## 快速创建
我们现在缺少编辑前端，欢迎你来帮助我们依据如下数据格式标准制作一款编辑前端！

制作很简单，你可以结合参考本仓库的三个json文件，根据以下说明进行制作。

示例的话请看本仓库的3个文件。

## 使用示例

在莘应用1.4及以上版本客户端的自定义数据源功能中添加如下内容：

![Screenshot_2024-04-04-23-00-34-042_com genouka rarestoret](https://github.com/Genouka/xin_data/assets/142009020/a2a382c2-662f-46e6-9f62-f0d511501924)

这将使用本仓库的[test.json](test.json)文件作为索引。

索引是一个数据源最核心的东西，它是一个数据源的灵魂。

## 数据格式
### 概要
大致依赖关系如下：

```
索引文件(json)
-> 应用列表文件(json)
-> 分类文件(json)
```

分类不是必须的，如果你想让用户有更好的体验的话最好还是加上。没有分类时请给索引的categorylistUrl字符串留空（而不是没有该字段，尽管这样也可以被解析）。

### 索引json
命名随意，放在github上或者你的网站上或者别的什么地方。

[查看实例](test.json)

applistUrl填应用列表的json的url，categorylistUrl填分类的json的url

```json
{
  "source":{
    "applistUrl":"https:\/\/raw.githubusercontent.com\/Genouka\/xin_data\/main\/applist.json",
    "categorylistUrl":"https:\/\/raw.githubusercontent.com\/Genouka\/xin_data\/main\/category.json"
  }
}
```

### 分类表json
`category.json`

以下是示例数据，应该一看就懂，不解释了：
```json
{
  "categorylist": [
    {
      "name": "工具",
      "category": 1
    },
    {
      "name": "游戏",
      "category": 2
    }
  ]
}
```

### 应用列表json
`applist.json`

以下是示例数据格式，应该一看就懂，不解释了：
```json
{
  "applist": [
     {
      "name": "坚果天气",
      "url": "https://fel.forxhr.top:2022/down.php/b676a21d4d041b8b0e40ad1c9b767362.apk",
      "icon": "https://fel.forxhr.top:2022/view.php/ffc9bc9a46fa3d9a8d9df427463a153d.png",
      "version": "2.6",
      "author": "老豆荚团队",
      "description": "是由老豆荚应用分享团队开发的锤子天气第三方客户端原锤子天气官方外发版本现已停止服务为了让其他安卓用户能够继续体验到锤子天气我们开发了这款客户端",
      "cutphoto": "https://fel.forxhr.top:2022/view.php/aa05b2a24b189b469e107eb42e33cac3.png",
      "category": 6
    },
     {
      "name": "密匣",
      "url": "https://fel.forxhr.top:2022/down.php/0422180a72227a079b45cd1e1ffae54d.apk",
      "icon": "https://fel.forxhr.top:2022/view.php/ad58e5bcaea84a342bc784464ed8776c.jpg",
      "version": "1.0",
      "author": "小趣团队",
      "description": "通过悬浮窗权限覆盖手表UI退出锁定模式需要连续数次长按屏幕可用特定页面覆盖手表UI使手表无法进行操作从而应付各种场景",
      "cutphoto": "https://fel.forxhr.top:2022/view.php/2920ef46a7c8e4e4fcae0ed6f2772ed4.jpg",
      "category": 1
    },
    ...
  ]
}
```

## 高级指南
### 使用一个json囊括索引和分类表和应用列表
符合下列格式即可：
```json
{
  "source":{ ... },
  "categorylist": [ ... ],
  "applist": [ ... ]
}
```

很简单，对吧。这个特性有利于你方便的发布单文件数据源，避免一个文件放三份的烦恼！

